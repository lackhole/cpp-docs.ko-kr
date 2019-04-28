---
title: 컴파일러 오류 C2393
ms.date: 11/04/2016
f1_keywords:
- C2393
helpviewer_keywords:
- C2393
ms.assetid: 4bd95728-e813-4ce8-844a-c6ebe235ca82
ms.openlocfilehash: 39ca693aed3f08e7b2df3d687f94d93384393f23
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62302399"
---
# <a name="compiler-error-c2393"></a>컴파일러 오류 C2393

> '*기호*': 세그먼트에 appdomain 별 기호를 할당할 수 없습니다 '*세그먼트*'

## <a name="remarks"></a>설명

**/clr: pure** 및 **/clr: safe** Visual Studio 2015에서 사용 되지 않고 Visual Studio 2017에서 지원 되지 않는 컴파일러 옵션입니다.

사용 [appdomain](../../cpp/appdomain.md) 변수를 사용 하 여 컴파일하고 의미 **/clr: pure** 또는 **/clr: safe**, 안전 또는 순수 이미지 데이터 세그먼트를 포함할 수 없습니다.

참조 [/clr (공용 언어 런타임 컴파일)](../../build/reference/clr-common-language-runtime-compilation.md) 자세한 내용은 합니다.

## <a name="example"></a>예제

다음 샘플 C2393를 생성합니다. 이 문제를 해결 하려면 데이터 세그먼트를 만들지 마십시오.

```cpp
// C2393.cpp
// compile with: /clr:pure /c
#pragma data_seg("myseg")
int n = 0;   // C2393
```