---
title: 컴파일러 오류 C2812
ms.date: 11/04/2016
f1_keywords:
- C2812
helpviewer_keywords:
- C2812
ms.assetid: 22aadb8c-7232-489d-a3ad-60662dda30a8
ms.openlocfilehash: 88b071f38cf41db9c929d25ffd526b3f2b7ca468
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62382959"
---
# <a name="compiler-error-c2812"></a>컴파일러 오류 C2812

> \#/clr을 사용한 가져오기가 지원 되지 않습니다: pure 및 /clr: safe

## <a name="remarks"></a>설명

**/clr: pure** 및 **/clr: safe** Visual Studio 2015에서 사용 되지 않고 Visual Studio 2017에서 지원 되지 않는 컴파일러 옵션입니다.

[#import 지시문](../../preprocessor/hash-import-directive-cpp.md) 지원 되지 않습니다 **/clr: pure** 및 **/clr: safe** 때문에 `#import` 네이티브 컴파일러 지원 라이브러리를 사용 해야 합니다.

## <a name="example"></a>예제

다음 샘플 C2812를 생성합니다.

```cpp
// C2812.cpp
// compile with: /clr:pure /c
#import "importlib.tlb"   // C2812
```