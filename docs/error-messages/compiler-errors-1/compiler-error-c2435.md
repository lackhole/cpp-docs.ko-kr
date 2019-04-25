---
title: 컴파일러 오류 C2435
ms.date: 11/04/2016
f1_keywords:
- C2435
helpviewer_keywords:
- C2435
ms.assetid: be6aa8f8-579b-42ea-bdd8-2d01393646ad
ms.openlocfilehash: 5cd7a83575da7ab2a30401406d0c2ccf6c1b603e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62166648"
---
# <a name="compiler-error-c2435"></a>컴파일러 오류 C2435

> '*var*': 동적 초기화는 관리 되는 CRT 필요, /clr: safe를 사용 하 여 컴파일할 수 없습니다

## <a name="remarks"></a>설명

**/clr: pure** 및 **/clr: safe** Visual Studio 2015에서 사용 되지 않고 Visual Studio 2017에서 지원 되지 않는 컴파일러 옵션입니다.

응용 프로그램별 도메인 전역 변수는 초기화 된 컴파일된 CRT가 필요 `/clr:pure`를 확인할 수 있는 이미지를 생성 하지 않는 합니다.

자세한 내용은 [appdomain](../../cpp/appdomain.md) 및 [process](../../cpp/process.md)를 참조하세요.

## <a name="example"></a>예제

다음 샘플에서는 C2435 오류가 생성 됩니다.

```cpp
// C2435.cpp
// compile with: /clr:safe /c
int globalvar = 0;   // C2435

__declspec(process)
int globalvar2 = 0;
```