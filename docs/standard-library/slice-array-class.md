---
title: slice_array 클래스
ms.date: 11/04/2016
f1_keywords:
- valarray/std::slice_array
helpviewer_keywords:
- slice_array class
ms.assetid: a182d5f7-f35c-4e76-86f2-b5ac64ddc846
ms.openlocfilehash: 358348a57b823fcea82cd296967c83778819361d
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72688957"
---
# <a name="slice_array-class"></a>slice_array 클래스

Valarray의 조각으로 정의 된 하위 집합 배열 간의 작업을 제공 하 여 조각 개체를 지 원하는 내부 보조 클래스 템플릿입니다.

## <a name="syntax"></a>구문

```cpp
template <class Type>
class slice_array : public slice {
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

이 클래스는 **valarray\<Type>** 개체에서 선택할 요소의 시퀀스를 설명하는 [slice](../standard-library/slice-class.md) 클래스의 개체와 함께 [valarray](../standard-library/valarray-class.md) **\<Type>** 클래스의 개체에 대한 참조를 저장하는 개체를 설명합니다.

클래스 템플릿은 특정 valarray 작업을 통해 간접적으로 만들어지며 프로그램에서 직접 사용할 수 없습니다. 조각 첨자 연산자에서 사용 하는 내부 보조 클래스 템플릿입니다.

`slice_array`\< **Type**> `valarray`< **Type**:: `operator[]` ( `slice`).

Valarray `va`의 조각 `sl`에 대해 [va&#91;sl&#93;](../standard-library/valarray-class.md#op_at)형식의 식을 작성 해야만 `slice_array<Type>` 개체를 생성할 수 있습니다. Slice_array 클래스의 멤버 함수는 선택한 요소의 시퀀스에만 영향을 주는 점을 제외 하 고 `valarray<Type>`에 대해 정의 된 해당 함수 서명 처럼 동작 합니다. slice_array에 의해 제어되는 시퀀스는 조각 생성자의 3개 매개 변수(조각의 첫 번째 요소 인덱스, 요소의 수 및 요소 간 거리)로 정의됩니다. **Va**[`slice` (2, 5, 3)]로 선언 된 valarray `va` slice_array 잘라내기는 `va`에서 인덱스 2, 5, 8, 11 및 14를 사용 하 여 요소를 선택 합니다. 인덱스가 유효해야 프로시저도 유효합니다.

## <a name="example"></a>예제

slice_array를 선언하고 사용하는 방법의 예제는 [slice::slice](../standard-library/slice-class.md#slice)의 예제를 참조하세요.

## <a name="requirements"></a>요구 사항

**헤더:** \<valarray>

**네임스페이스:** std

## <a name="see-also"></a>참조

[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)
