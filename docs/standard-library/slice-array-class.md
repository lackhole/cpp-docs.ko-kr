---
title: slice_array 클래스
ms.date: 11/04/2016
f1_keywords:
- valarray/std::slice_array
helpviewer_keywords:
- slice_array class
ms.assetid: a182d5f7-f35c-4e76-86f2-b5ac64ddc846
ms.openlocfilehash: cf33c5f627a88698c84947f9b803edaebccf5566
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68450410"
---
# <a name="slicearray-class"></a>slice_array 클래스

valarray의 조각으로 정의된 하위 집합 배열 간의 작업을 제공하여 조각 개체를 지원하는 내부 보조 템플릿 클래스입니다.

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

## <a name="remarks"></a>설명

이 클래스는 **valarray\<Type>** 개체에서 선택할 요소의 시퀀스를 설명하는 [slice](../standard-library/slice-class.md) 클래스의 개체와 함께 [valarray](../standard-library/valarray-class.md) **\<Type>** 클래스의 개체에 대한 참조를 저장하는 개체를 설명합니다.

템플릿 클래스는 특정 valarray 작업에 의해 간접적으로 생성되며 프로그램에서 직접 사용할 수는 없습니다. 슬라이스 subscript 연산자에서 사용하는 내부 보조 템플릿 클래스는 다음과 같습니다.

`slice_array`\< **Type**> `valarray`< **Type**:: `operator[]` ( `slice`).

Valarray `slice_array<Type>` [&#91;&#93;](../standard-library/valarray-class.md#op_at) 의조각`sl` 에 대해 va sl 형식의 식을 작성 하 여 개체를 생성 합니다. `va` 그러면 slice_array 클래스의 멤버 함수는 선택한 요소의 시퀀스에만 영향을 주는 `valarray<Type>`점을 제외 하 고에 대해 정의 된 해당 함수 서명 처럼 동작 합니다. slice_array에 의해 제어되는 시퀀스는 조각 생성자의 3개 매개 변수(조각의 첫 번째 요소 인덱스, 요소의 수 및 요소 간 거리)로 정의됩니다. `va` **Va**[ `va`(2, 5, 3)]로 선언 된 valarray에서 slice_array 잘라내기는 인덱스 2, 5, 8, 11 및 14를 사용 하 여 요소를 선택 합니다. `slice` 인덱스가 유효해야 프로시저도 유효합니다.

## <a name="example"></a>예제

slice_array를 선언하고 사용하는 방법의 예제는 [slice::slice](../standard-library/slice-class.md#slice)의 예제를 참조하세요.

## <a name="requirements"></a>요구 사항

**헤더:** \<valarray>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)
