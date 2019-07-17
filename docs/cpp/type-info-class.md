---
title: type_info 클래스
ms.date: 11/04/2016
f1_keywords:
- type_info
helpviewer_keywords:
- class type_info
- type_info class
ms.assetid: 894ddda2-7de4-4da3-9404-d2c74e356c16
ms.openlocfilehash: b0cddd2c5cc09e77e8733ca88177c3b2223fc8ce
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68242085"
---
# <a name="typeinfo-class"></a>type_info 클래스

합니다 **type_info** 형식 정보를 컴파일러에 의해 프로그램 내에서 생성 하는 클래스에 설명 합니다. 이 클래스의 개체는 형식의 이름에 대한 포인터를 효과적으로 저장합니다. 합니다 **type_info** 클래스에는 또한 두 형식의 비교 또는 정렬 순서에 대 한 적절 한 인코딩된 값을 저장 합니다. 형식의 인코딩 규칙 및 정렬 시퀀스는 지정되지 않으며 프로그램 간에 다를 수 있습니다.

`<typeinfo>` 헤더 파일을 사용 하려면 포함 되어야 합니다 **type_info** 클래스입니다. 에 대 한 인터페이스를 **type_info** 클래스는:

```cpp
class type_info {
public:
    type_info(const type_info& rhs) = delete; // cannot be copied
    virtual ~type_info();
    size_t hash_code() const;
    _CRTIMP_PURE bool operator==(const type_info& rhs) const;
    type_info& operator=(const type_info& rhs) = delete; // cannot be copied
    _CRTIMP_PURE bool operator!=(const type_info& rhs) const;
    _CRTIMP_PURE int before(const type_info& rhs) const;
    size_t hash_code() const noexcept;
    _CRTIMP_PURE const char* name() const;
    _CRTIMP_PURE const char* raw_name() const;
};
```

개체를 인스턴스화할 수 없습니다는 **type_info** 클래스에 전용 복사 생성자만 있으므로 클래스를 직접. (임시)를 생성 하는 유일한 방법은 **type_info** 개체가 사용 하 여 [typeid](../cpp/typeid-operator.md) 연산자입니다. 복사 하거나 클래스의 개체를 할당할 수 없습니다. 개인 또한 대입 연산자 이므로 **type_info**합니다.

`type_info::hash_code` 형식의 값을 매핑하기에 적합 한 해시 함수를 정의 **typeinfo** 인덱스 값의 분포에 있습니다.

연산자 `==` 하 고 `!=` 사용 하 여 다른 같음 또는 같지 않음을 비교할 수 있습니다 **type_info** 개체를 각각.

형식의 정렬 순서와 상속 관계 간에 링크가 없습니다. 사용 된 `type_info::before` 형식의 정렬 순서를 결정 하는 멤버 함수입니다. 보장이 `type_info::before` 다른 프로그램 또는 같은 프로그램의 다른 실행에서 동일한 결과 생성 합니다. 이런 방식으로 `type_info::before` 비슷합니다 주소 `(&)` 연산자입니다.

`type_info::name` 멤버 함수가 반환 하는 `const char*` 형식의 알기 쉬운 이름을 나타내는 null로 끝나는 문자열에 있습니다. 가리키는 메모리는 캐시되며 직접 할당 해지되면 안 됩니다.

`type_info::raw_name` 멤버 함수가 반환 하는 `const char*` null로 끝나는 문자열로 개체 형식을 데코 레이트 된 이름을 나타내는입니다. 공간을 절약하기 위해 이름은 실제로 데코레이팅된 형식으로 저장됩니다. 따라서이 함수는 보다 빠르게 `type_info::name` 이름의 데코레이팅을 취소할 필요가 없기 때문입니다. 반환한 문자열을 `type_info::raw_name` 함수 비교 연산에 유용 하지만 읽을 수 없습니다. 사람이 읽을 수 있는 문자열에 필요한 경우 사용 된 `type_info::name` 함수를 대신 합니다.

경우에만 다형 클래스에 대 한 형식 정보가 생성 되는 [/GR (런타임 형식 정보 사용)](../build/reference/gr-enable-run-time-type-information.md) 컴파일러 옵션을 지정 합니다.

## <a name="see-also"></a>참고자료

[런타임 형식 정보](../cpp/run-time-type-information.md)