---
title: gslice_array 클래스
ms.date: 11/04/2016
f1_keywords:
- valarray/std::gslice_array
helpviewer_keywords:
- gslice_array class
ms.assetid: ad1b4514-b14a-4baf-a293-d5a8e8674c75
ms.openlocfilehash: 37c54d09fdfe920c832c4baa7984fee4e090d04a
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68448924"
---
# <a name="gslicearray-class"></a>gslice_array 클래스

valarray의 일반 조각으로 정의된 하위 집합 배열 간의 작업을 제공하여 일반 조각 개체를 지원하는 내부 보조 템플릿 클래스입니다.

## <a name="syntax"></a>구문

```cpp
template <class Type>
class gslice_array : public gsplice {
public:
    typedef Type value_type;
    void operator=(const valarray<Type>& x) const;

    void operator=(const Type& x) const;

    void operator*=(const valarray<Type>& x) const;

    void operator/=(const valarray<Type>& x) const;

    void operator%=(const valarray<Type>& x) const;

    void operator+=(const valarray<Type>& x) const;

    void operator-=(const valarray<Type>& x) const;

    void operator^=(const valarray<Type>& x) const;

    void operator&=(const valarray<Type>& x) const;

    void operator|=(const valarray<Type>& x) const;

    void operator<<=(const valarray<Type>& x) const;

    void operator>>=(const valarray<Type>& x) const;

// The rest is private or implementation defined
}
```

## <a name="remarks"></a>설명

이 `va` 클래스는 선택할 요소의 시퀀스를 설명 하는 [gslice](../standard-library/gslice-class.md) 클래스의 개체 `gs` 와 함께 [valarray](../standard-library/valarray-class.md) **\<형식 >** 클래스의 개체에 대 한 참조를 저장 하는 개체를 설명 합니다. `valarray<Type>` 개체입니다.

[Va&#91;gs&#93;](../standard-library/valarray-class.md#op_at)형식의 `gslice_array<Type>` 식을 작성 하 여 개체를 생성 합니다. 그러면 gslice_array 클래스의 멤버 함수는 선택한 요소의 시퀀스에만 영향을 주는 `valarray<Type>`점을 제외 하 고에 대해 정의 된 해당 함수 서명 처럼 동작 합니다.

템플릿 클래스는 특정 valarray 작업에 의해 간접적으로 생성되며 프로그램에서 직접 사용할 수는 없습니다. 내부 보조 템플릿 클래스는 다음과 같은 조각 아래 첨자 연산자에서 사용됩니다.

`gslice_array`\< **Type**> `valarray`\< **Type**>:: `operator[]`(**constgslice&** ).

Valarray `gslice_array<Type>` `va[gsl]` 의조각`gsl` 에 대해 폼의 식을 작성 하 여 개체를 생성 합니다. `va` 그러면 gslice_array 클래스의 멤버 함수는 선택한 요소의 시퀀스에만 영향을 주는 `valarray<Type>`점을 제외 하 고에 대해 정의 된 해당 함수 서명 처럼 동작 합니다. gslice_array에 의해 제어되는 시퀀스는 조각 생성자의 3개 매개 변수(첫 번째 조각의 첫 번째 요소 인덱스, 각 조각의 요소 수 및 각 조각에 있는 요소 간 거리)로 정의됩니다.

다음 예제에서는

```cpp
const size_t lv[] = {2, 3};
const size_t dv[] = {7, 2};
const valarray<size_t> len(lv, 2), str(dv, 2);

// va[gslice(3, len, str)] selects elements with
//   indices 3, 5, 7, 10, 12, 14
```

인덱스가 유효해야 프로시저도 유효합니다.

## <a name="example"></a>예제

slice_array를 선언하고 사용하는 방법의 예제는 [gslice::gslice](../standard-library/gslice-class.md#gslice)의 예제를 참조하세요.

## <a name="requirements"></a>요구 사항

**헤더:** \<valarray>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)
