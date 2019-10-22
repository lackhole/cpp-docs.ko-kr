---
title: gslice_array 클래스
ms.date: 11/04/2016
f1_keywords:
- valarray/std::gslice_array
helpviewer_keywords:
- gslice_array class
ms.assetid: ad1b4514-b14a-4baf-a293-d5a8e8674c75
ms.openlocfilehash: 68ce774128395e941ff80580a02c4ee28a74a4e4
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72689591"
---
# <a name="gslice_array-class"></a>gslice_array 클래스

Valarray의 일반 조각으로 정의 된 하위 집합 배열 간의 작업을 제공 하 여 일반 조각 개체를 지 원하는 내부 보조 클래스 템플릿입니다.

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

## <a name="remarks"></a>주의

이 클래스는 `valarray<Type>` 개체에서 선택할 요소의 시퀀스를 설명 하는 [gslice](../standard-library/gslice-class.md) 클래스의 `gs` 개체와 함께 **valarray \<Type** [array](../standard-library/valarray-class.md) 클래스 `va` 개체에 대 한 참조를 저장 하는 개체를 설명 합니다.

[Va&#91;gs&#93;](../standard-library/valarray-class.md#op_at)형식의 식을 작성 하 여 `gslice_array<Type>` 개체를 구성 합니다. Gslice_array 클래스의 멤버 함수는 선택한 요소의 시퀀스에만 영향을 주는 점을 제외 하 고 `valarray<Type>`에 대해 정의 된 해당 함수 서명 처럼 동작 합니다.

클래스 템플릿은 특정 valarray 작업을 통해 간접적으로 만들어지며 프로그램에서 직접 사용할 수 없습니다. 내부 보조 클래스 템플릿은 대신 조각 첨자 연산자에서 사용 됩니다.

`gslice_array`\< **Type**> `valarray`\< **Type**>:: `operator[]`(**constgslice&** ).

Valarray `va`의 조각 `gsl`에 대해 `va[gsl]` 형식의 식을 작성 하 여 `gslice_array<Type>` 개체를 구성 합니다. Gslice_array 클래스의 멤버 함수는 선택한 요소의 시퀀스에만 영향을 주는 점을 제외 하 고 `valarray<Type>`에 대해 정의 된 해당 함수 서명 처럼 동작 합니다. gslice_array에 의해 제어되는 시퀀스는 조각 생성자의 3개 매개 변수(첫 번째 조각의 첫 번째 요소 인덱스, 각 조각의 요소 수 및 각 조각에 있는 요소 간 거리)로 정의됩니다.

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

## <a name="see-also"></a>참조

[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)
