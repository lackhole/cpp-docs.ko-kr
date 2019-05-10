---
title: 속성 (C++)
ms.date: 11/04/2016
f1_keywords:
- property_cpp
helpviewer_keywords:
- property __declspec keyword
- __declspec keyword [C++], property
ms.assetid: f3b850ba-bf48-4df7-a1d6-8259d97309ce
ms.openlocfilehash: ece1016b7a18873dfa477b0f8b6ae4271a0f8001
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62301489"
---
# <a name="property-c"></a>속성 (C++)

**Microsoft 전용**

이 특성은 클래스 또는 구조체 정의에서 비정적 "가상 데이터 멤버"에 적용할 수 있습니다. 컴파일러는 해당 참조를 함수 호출로 변경하여 이러한 "가상 데이터 멤버"를 데이터 멤버로 처리합니다.

## <a name="syntax"></a>구문

```
   __declspec( property( get=get_func_name ) ) declarator
   __declspec( property( put=put_func_name ) ) declarator
   __declspec( property( get=get_func_name, put=put_func_name ) ) declarator
```

## <a name="remarks"></a>설명

컴파일러는 멤버 선택 연산자의 오른쪽에이 특성으로 선언 된 데이터 멤버를 확인 하는 경우 ("**.**" or "**->**")를 변환 하는 작업을 `get` 또는 `put` 함수를 이러한 식은 l-value 또는 r-value 인지에 따라 합니다. "`+=`"와 같은 보다 복잡한 컨텍스트에서는 `get` 및 `put` 을 둘 다 수행하여 다시 작성됩니다.

이 특성은 클래스 또는 구조체 정의에 있는 빈 배열의 선언에서도 사용할 수 있습니다. 예를 들면 다음과 같습니다.

```cpp
__declspec(property(get=GetX, put=PutX)) int x[];
```

위의 문은 `x[]`를 하나 이상의 배열 인덱스와 함께 사용할 수 있음을 나타냅니다. 이 경우 `i=p->x[a][b]`가 `i=p->GetX(a, b)`로 바뀌고 `p->x[a][b] = i`가 `p->PutX(a, b, i);`로 바뀝니다.

**Microsoft 전용 종료**

## <a name="example"></a>예제

```cpp
// declspec_property.cpp
struct S {
   int i;
   void putprop(int j) {
      i = j;
   }

   int getprop() {
      return i;
   }

   __declspec(property(get = getprop, put = putprop)) int the_prop;
};

int main() {
   S s;
   s.the_prop = 5;
   return s.the_prop;
}
```

## <a name="see-also"></a>참고 항목

[__declspec](../cpp/declspec.md)<br/>
[키워드](../cpp/keywords-cpp.md)