---
title: 컴파일러 경고 C4958
ms.date: 11/04/2016
f1_keywords:
- C4958
helpviewer_keywords:
- C4958
ms.assetid: e79b9e9c-d572-4a3a-a3b6-60962b70864a
ms.openlocfilehash: 96b73975f391493340dd01d85ad30a8c888b44c0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62208073"
---
# <a name="compiler-warning-c4958"></a>컴파일러 경고 C4958

> '*작업*': 포인터 산술 연산은 확인할 수 없습니다

## <a name="remarks"></a>설명

포인터 산술 연산을 사용하여 확인할 수 없는 이미지를 생성합니다.

자세한 내용은 [순수형 및 안정형 코드 (C++/CLI)](../../dotnet/pure-and-verifiable-code-cpp-cli.md)합니다.

합니다 **/clr: safe** 컴파일러 옵션은 Visual Studio 2015에서 사용 되지 않으며 Visual Studio 2017에서 지원 되지 않습니다.

이 경고는 오류로 발생하며 [warning](../../preprocessor/warning.md) pragma 또는 [/wd](../../build/reference/compiler-option-warning-level.md) 컴파일러 옵션과 함께 사용하지 않도록 설정할 수 있습니다.

## <a name="example"></a>예제

다음 샘플에서는 C4958을 생성합니다.

```cpp
// C4958.cpp
// compile with: /clr:safe
// #pragma warning( disable : 4958 )
using namespace System;

int main( ) {
   Int32 arr[] = new Int32[10];
   Int32* p = &arr[0];
   p++;   // C4958
}
```

컴파일러는 포인터 산술 연산을 사용하여 배열 연산을 구현합니다. 따라서 네이티브 배열은 확인할 수 없습니다. 대신 CLR 배열을 사용합니다. 자세한 내용은 [배열](../../extensions/arrays-cpp-component-extensions.md)을 참조하세요.

다음 샘플에서는 C4958을 생성합니다.

```cpp
// C4958b.cpp
// compile with: /clr:safe
// #pragma warning( disable : 4958 )

int main() {
   int array[5];
   array[4] = 0;   // C4958
}
```