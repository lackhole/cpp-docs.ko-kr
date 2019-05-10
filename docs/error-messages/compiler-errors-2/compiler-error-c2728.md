---
title: 컴파일러 오류 C2728
ms.date: 11/04/2016
f1_keywords:
- C2728
helpviewer_keywords:
- C2728
ms.assetid: 65635f91-1cd1-46e4-9ad7-14726d0546af
ms.openlocfilehash: 1fbbc3d63386ebe98a447de8b7166a5263d2168f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62208417"
---
# <a name="compiler-error-c2728"></a>컴파일러 오류 C2728

'type' : 네이티브 배열은 이러한 형식을 포함할 수 없습니다.

배열 생성 구문을 사용하여 관리되는 개체 또는 WinRT 개체를 만들었습니다. 관리되는 개체 또는 WinRT 개체의 배열은 네이티브 배열 구문을 사용하여 만들 수 없습니다.

자세한 내용은 [배열](../../extensions/arrays-cpp-component-extensions.md)을 참조하세요.

다음 샘플에서는 C2728 오류가 발생하는 경우 및 이를 해결하는 방법을 보여 줍니다.

```
// C2728.cpp
// compile with: /clr

int main() {
   int^ arr[5];   // C2728

   // try the following line instead
   array<int>^arr2;
}
```
