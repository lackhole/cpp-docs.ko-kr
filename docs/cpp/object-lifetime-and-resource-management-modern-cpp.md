---
title: 개체 수명 및 리소스 관리(모던 C++)
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 8aa0e1a1-e04d-46b1-acca-1d548490700f
ms.openlocfilehash: 5964078960a5b241cb5af369aeddba45a06e48ad
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62245025"
---
# <a name="object-lifetime-and-resource-management-modern-c"></a>개체 수명 및 리소스 관리(모던 C++)

관리 되는 언어와 달리 C++에는 프로그램이 실행 될 때 자동으로 아니요 긴-사용 되는 메모리 리소스를 릴리스 하는 가비지 수집 (GC)이 없습니다. C++에서는 리소스 관리 개체 수명을 직접 관련 되어 있습니다. 이 문서에서는 C++에서 개체 수명 및 관리 하는 방법에 영향을 주는 요인을 설명 합니다.

C++는 메모리 내 리소스를 처리 하지 않는 것 때문에 주로 GC 없습니다. 만 C++에서와 같이 결정적 소멸자 메모리 및 메모리 내 리소스를 균등 하 게 처리할 수 있습니다. GC에는 메모리 및 CPU 사용량 및 위치에 더 높은 오버 헤드와 같은 다른 문제가 있습니다. 하지만 보편성 clever 최적화를 통해 완화할 수 있는 기본적인 문제.

## <a name="concepts"></a>개념

개체 수명 관리에는 중요 한 것은 캡슐화-개체는 리소스의 소유를을 제거 하는 방법 또는 있는지 여부를 소유 하 고 모든 리소스 전혀 알 필요가 없는 개체를 사용 하는 누구 든 지 합니다. 방금 개체를 제거 해야 합니다. C++ 핵심 언어는 객체는 올바른 시간, 보장 되도록 설계 되었습니다 블록은 종료 역순으로 생성 합니다. 개체 소멸 될 때 해당 기본 항목 및 멤버는 특정 순서로 삭제 됩니다.  언어는 힙 할당 또는 새 배치와 같은 특별 한 작업을 수행 하지 않을 경우 자동으로 개체를 제거 합니다.  예를 들어 [스마트 포인터](../cpp/smart-pointers-modern-cpp.md) 와 같은 `unique_ptr` 하 고 `shared_ptr`, C++ 표준 라이브러리 컨테이너와 `vector`, 캡슐화 **새** / **삭제** 하 고 `new[]` / `delete[]` 소멸자가 있는 개체입니다. 이유는 스마트 포인터 및 C++ 표준 라이브러리 컨테이너 사용 하 여 중요 한 것입니다.

수명 관리의 다른 중요 한 개념: 소멸자입니다. 소멸자는 리소스를 해제할을 캡슐화합니다.  (일반적으로 사용 되는 니모닉 RRID, Resource Release Is Destruction입니다.)  리소스는 "시스템"에서 가져와 나중에 다시 제공 해야 하는 것입니다.  메모리는 가장 일반적인 리소스에 있지만 파일, 소켓, 질감 및 기타 메모리 내 리소스가 있습니다. 리소스를 "소유" 필요 하지만를 사용 하 여 완료 되 면 해제 해야 하는 경우 사용할 수 있습니다 하는 것을 의미 합니다.  개체 소멸 될 때 해당 소멸자가 소유 하는 리소스를 해제 합니다.

최종 개념은 DAG (방향성 비순환 그래프).  프로그램에서 소유권의 구조는 DAG를 형성합니다. 자체 개체가 소유할 수 있습니다-없는 불가능 하지만 근본적으로 의미가 없습니다. 하지만 두 개체는 세 번째 개체의 소유권을 공유할 수 있습니다.  여러 종류의 링크가 같이 DAG에 나타날 수 있습니다. A가 B의 구성원이 (B는 소유)를 C 저장소를 `vector<D>` (C D 요소당 소유), E 저장소를 `shared_ptr<F>` (E 공유 소유권 f의 가능한 다른 개체를 사용 하 여) 등입니다.  순환이 가지 고 DAG에서 모든 링크는 개체로 표시 됩니다 (원시 포인터, 핸들 또는 기타 메커니즘) 하는 대신 소멸자가 있는 다음 않고 언어 리소스 누수 가능 하지 않습니다. 리소스가 더 이상 필요한 가비지 수집기를 실행 하지 않고 즉시 해제 됩니다. 추적 수명은 스택 범위, 자료, 멤버 및 관련된 사례에 대 한 오버 헤드 해제 하 고에 대 한 저렴 한 `shared_ptr`합니다.

### <a name="heap-based-lifetime"></a>힙 기반 수명

힙 개체 수명에 대 한 사용 [스마트 포인터](../cpp/smart-pointers-modern-cpp.md)합니다. 사용 하 여 `shared_ptr` 고 `make_shared` 기본 포인터와 할당자입니다. 사용 하 여 `weak_ptr` 주기 중단, 캐싱, 수행 및에 영향을 주거나 수명에 대 한 아무 것도 가정 하지 않고 개체를 관찰 합니다.

```cpp
void func() {

auto p = make_shared<widget>(); // no leak, and exception safe
...
p->draw();

} // no delete required, out-of-scope triggers smart pointer destructor
```

사용 하 여 `unique_ptr` 고유 소유권에 대 한 예는 *캡슐화 pimpl* 관용구 합니다. (참조 [컴파일 시간 캡슐화에 대 한 Pimpl](../cpp/pimpl-for-compile-time-encapsulation-modern-cpp.md).) 확인을 `unique_ptr` 모두 명시적의 기본 대상이 **새** 식입니다.

```cpp
unique_ptr<widget> p(new widget());
```

비 소유권 및 관찰에 대 한 원시 포인터를 사용할 수 있습니다. 소유 되지 않은 포인터 dangle 수 있지만 누출 수 없습니다.

```cpp
class node {
  ...
  vector<unique_ptr<node>> children; // node owns children
  node* parent; // node observes parent, which is not a concern
  ...
};
node::node() : parent(...) { children.emplace_back(new node(...) ); }
```

성능 최적화가 필요한 경우 사용 해야 할 수 있습니다 *잘 캡슐화 된* 포인터 및 삭제에 대 한 명시적 호출을 소유 합니다. 예에는 고유한 하위 수준 데이터 구조를 구현 하는 경우입니다.

### <a name="stack-based-lifetime"></a>스택 기반 수명

최신 C++에서 *스택 기반 범위* 자동 결합 때문에 강력한 코드를 작성 하는 강력한 방법 *스택 수명* 하 고 *데이터 멤버 수명* 높은 효율성을 사용 하 여- 추적 수명은 기본적으로 무료 오버 헤드입니다. 힙 개체 수명 철저 한 수동 관리가 필요 및 원시 포인터를 사용 하 여 작업 하는 경우에 특히 원본 리소스 누수 및 비효율성을 수 있습니다. 이 코드를에서는 스택 기반 범위를 보여 주는 것이 좋습니다.

```cpp
class widget {
private:
    gadget g;   // lifetime automatically tied to enclosing object
public:
    void draw();
};

void functionUsingWidget () {
    widget w;   // lifetime automatically tied to enclosing scope
                // constructs w, including the w.g gadget member
    // ...
    w.draw();
    // ...
} // automatic destruction and deallocation for w and w.g
  // automatic exception safety,
  // as if "finally { w.dispose(); w.g.dispose(); }"
```

정적 수명을 제한적으로 사용 (전역 정적, 로컬 정적 함수) 하므로 문제가 발생할 수 있습니다. 전역 개체의 생성자는 예외를 throw 하면 어떻게 되나요? 일반적으로 응용 프로그램 오류를 디버그 하기가 어려워질 수 있도록 합니다. 생성 순서는 정적 수명 개체에 대 한 문제가 및 동시성 안전 하지 않습니다. 뿐만 아니라 개체 생성을은 문제가 소멸 순서 다형성이 포함 하는 경우에 특히 복잡할 수 있습니다. 사용자 개체 또는 변수가 다형 아니고 없는 복잡 한 생성/소멸 순서 지정, 경우에 경우 여전히 스레드로부터 안전한 동시성 문제 안전 하 게 다중 스레드 앱 스레드 로컬 저장소, 리소스 잠금 및 기타 특별 한 주의 하지 않고도 정적 개체의 데이터를 수정할 수 없습니다.

## <a name="see-also"></a>참고자료

[C++의 진화(모던 C++)](../cpp/welcome-back-to-cpp-modern-cpp.md)<br/>
[C++ 언어 참조](../cpp/cpp-language-reference.md)<br/>
[C++ 표준 라이브러리](../standard-library/cpp-standard-library-reference.md)
