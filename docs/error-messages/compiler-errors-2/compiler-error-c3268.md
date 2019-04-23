---
title: 컴파일러 오류 C3268
ms.date: 11/04/2016
f1_keywords:
- C3268
helpviewer_keywords:
- C3268
ms.assetid: d74a630c-daea-4e29-9759-83efef7fb184
ms.openlocfilehash: d9954c12fb1065a4aa5e7afbdecd1f96758acaf9
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59777759"
---
# <a name="compiler-error-c3268"></a>컴파일러 오류 C3268

> '*함수*': 제네릭 함수 또는 제네릭 클래스의 멤버 함수는 가변 매개 변수 목록을 사용할 수 없습니다

## <a name="remarks"></a>설명

**/clr: pure** 및 **/clr: safe** Visual Studio 2015에서 사용 되지 않고 Visual Studio 2017에서 지원 되지 않는 컴파일러 옵션입니다.

참조 [제네릭](../../extensions/generics-cpp-component-extensions.md) 자세한 내용은 합니다.

## <a name="example"></a>예제

다음 샘플에서는 C3268을 생성합니다.

```cpp
// C3268.cpp
// compile with: /clr:pure /c
generic <class ItemType>
void Test(ItemType item, ...) {}   // C3268
// try the following line instead
// void Test(ItemType item) {}

generic <class ItemType2>
ref struct MyStruct { void Test(...){} };   // C3268
// try the following line instead
// ref struct MyStruct { void Test2(){} };   // OK
```