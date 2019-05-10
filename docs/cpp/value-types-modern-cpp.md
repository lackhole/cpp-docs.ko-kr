---
title: 값 형식(모던 C++)
ms.date: 05/07/2019
ms.topic: conceptual
ms.assetid: f63bb62c-60da-40d5-ac14-4366608fe260
ms.openlocfilehash: 204ea9f86377eb8a5796f01cb81a9161163d9649
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65221888"
---
# <a name="value-types-modern-c"></a>값 형식(모던 C++)

C++ 클래스는 기본 값 형식으로 됩니다. 이 항목에서는 값 형식 및 용도 관련 된 문제 소개 개요를 제공 합니다.

## <a name="value-vs-reference-types"></a>참조 형식 및 값

이전에 설명한 대로 C++ 클래스는 기본 값 형식입니다. 개체 지향 프로그래밍을 지원 하기 위해 원하는 다형성 동작에 사용 하도록 설정 하는 참조 형식으로 지정할 수 있습니다. 값 형식 참조 형식은 기본 클래스 및 가상 함수를 다형적으로 하는 반면에 경우에 따라 메모리 및 레이아웃 컨트롤의 관점에서 표시 됩니다. 기본적으로 값 형식은 복사할 수는 항상 복사 생성자 및 복사 할당 연산자를 의미 합니다. 참조 형식에 대해 수행한 클래스 복사할 수 없는 (복사 생성자 및 복사 할당 연산자를 사용 안 함)가 의도 한 다형성을 지 원하는 가상 소멸자를 사용 하 고 있습니다. 값 형식 복사 될 때 항상 제공 개별적으로 수정할 수 있는 독립적인 값 두 개는 내용에 대 한도입니다. 참조 형식 개체의 종류는 해당 id에 대 한? 이 이유로 "은 형식을 참조 하 고"는 "다형 형식" 라고도 합니다.

같은 참조 형식 (기본 클래스, 가상 함수)를 하려는 경우 명시적으로 해제 해야 복사에 표시 된 대로 `MyRefType` 다음 코드에서는 클래스입니다.

```cpp
// cl /EHsc /nologo /W4

class MyRefType {
private:
    MyRefType & operator=(const MyRefType &);
    MyRefType(const MyRefType &);
public:
    MyRefType () {}
};

int main()
{
    MyRefType Data1, Data2;
    // ...
    Data1 = Data2;
}
```

위의 코드를 컴파일한 다음 오류가 발생 합니다.

```Output
test.cpp(15) : error C2248: 'MyRefType::operator =' : cannot access private member declared in class 'MyRefType'
        meow.cpp(5) : see declaration of 'MyRefType::operator ='
        meow.cpp(3) : see declaration of 'MyRefType'
```

## <a name="value-types-and-move-efficiency"></a>값 형식 및 효율성을 이동

새 복사 최적화로 인해 복사 할당 오버 헤드를 금지 합니다. 예를 들어, 문자열의 벡터가 중간 문자열을 삽입 하면 있습니다 복사 재할당 오버 헤드 없이만 이동-터 자체의 확장에서 발생 하는 경우에 합니다. 예를 들어 두 개의 매우 큰 개체에 추가 작업을 수행 하는 다른 작업에 적용 됩니다. 이러한 값 작업 최적화를 어떻게 사용 합니까? 일부 C++ 컴파일러에서 컴파일러는이 기능을 사용 하기 암시적으로 마찬가지로 컴파일러에서 복사 생성자를 자동으로 생성할 수 있습니다. 그러나 C++에서 클래스를 "옵트인" 클래스 정의에서 선언 하 여 할당 및 생성자를 이동 해야 합니다. 이 이중 앰퍼샌드를 사용 하 여 수행 됩니다 (& &) 적절 한 멤버에 대 한 rvalue 참조 함수 선언 및 정의 이동 생성자 및 이동 할당 방법.  원본 개체에서 "부분은 도용" 하는 올바른 코드를 삽입 해야 합니다.

활성화를 이동 해야 하는 경우를 어떻게 결정 하나요? 사용 하도록 설정 하는 생성을 복사 해야 이미 알고 있는 경우 전체 복사본을 보다 저렴 한 변환할 수 있으면 사용 이동는 것이 원할입니다. 그러나 지원을 이동 해야를 알고 있으면이 반드시 사용 하도록 설정 하는 복사 하려는. "이동 전용 type"이 후자의 경우 호출 됩니다. 표준 라이브러리에 이미 있는 예로 `unique_ptr`합니다. 참고, 이전 `auto_ptr` 는 사용 되지 않으며로 대체 되었습니다 `unique_ptr` C++의 이전 버전에 이동 의미 체계 지원 부족으로 인해 정확 하 게 합니다.

이동 의미 체계를 사용 하 여 반환 값 또는 중간에서 삽입을 수 있습니다. 복사본의 최적화 된 이동입니다. 문제를 해결 하려면 힙 할당에 대 한 필요가 있습니다. 다음 의사 코드를 살펴보겠습니다.

```cpp
#include <set>
#include <vector>
#include <string>
using namespace std;

//...
set<widget> LoadHugeData() {
    set<widget> ret;
    // ... load data from disk and populate ret
    return ret;
}
//...
widgets = LoadHugeData();   // efficient, no deep copy

vector<string> v = IfIHadAMillionStrings();
v.insert( begin(v)+v.size()/2, "scott" );   // efficient, no deep copy-shuffle
v.insert( begin(v)+v.size()/2, "Andrei" );  // (just 1M ptr/len assignments)
//...
HugeMatrix operator+(const HugeMatrix& , const HugeMatrix& );
HugeMatrix operator+(const HugeMatrix& ,       HugeMatrix&&);
HugeMatrix operator+(      HugeMatrix&&, const HugeMatrix& );
HugeMatrix operator+(      HugeMatrix&&,       HugeMatrix&&);
//...
hm5 = hm1+hm2+hm3+hm4+hm5;   // efficient, no extra copies
```

### <a name="enabling-move-for-appropriate-value-types"></a>적절 한 값 형식에 대해 사용 하도록 설정 하면 이동

값 방식 클래스의 전체 복사본을 보다 저렴 한으로 이동 수 있는 경우 이동 생성을 사용 하도록 설정 하 고 효율성에 대 한 할당을 이동 합니다. 다음 의사 코드를 살펴보겠습니다.

```cpp
#include <memory>
#include <stdexcept>
using namespace std;
// ...
class my_class {
    unique_ptr<BigHugeData> data;
public:
    my_class( my_class&& other )   // move construction
        : data( move( other.data ) ) { }
    my_class& operator=( my_class&& other )   // move assignment
    { data = move( other.data ); return *this; }
    // ...
    void method() {   // check (if appropriate)
        if( !data )
            throw std::runtime_error("RUNTIME ERROR: Insufficient resources!");
    }
};
```

복사 생성/할당을 사용 하도록 설정 하는 경우 사용 하도록 설정할 수도 이동 생성/할당 경우 전체 복사본을 보다 저렴할 수 있습니다.

일부 *값이 아닌* 유형은 이동 전용 같은 경우 소유권을 이전만 리소스를 복제할 수 없습니다. 예를 들어, `unique_ptr` 같은 형식입니다.

## <a name="section"></a>단원

콘텐츠

## <a name="see-also"></a>참고자료

[C++ 형식 시스템(모던 C++)](../cpp/cpp-type-system-modern-cpp.md)<br/>
[C++의 진화(모던 C++)](../cpp/welcome-back-to-cpp-modern-cpp.md)<br/>
[C++ 언어 참조](../cpp/cpp-language-reference.md)<br/>
[C++ 표준 라이브러리](../standard-library/cpp-standard-library-reference.md)
