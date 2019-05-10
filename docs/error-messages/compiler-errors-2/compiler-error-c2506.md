---
title: 컴파일러 오류 C2506
ms.date: 11/04/2016
f1_keywords:
- C2506
helpviewer_keywords:
- C2506
ms.assetid: cfed21cd-2404-46f2-985e-d0c2c3820830
ms.openlocfilehash: 02f0a81204c4bc1c41111d32bae1c6946dee09ac
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62164867"
---
# <a name="compiler-error-c2506"></a>컴파일러 오류 C2506

'member': '__declspec(modifier)'이 기호에 적용할 수 없습니다

관리 되는 클래스의 정적 멤버에 대 한 프로세스당 또는 appdomain 별를 선언할 수 없습니다.

자세한 내용은 [appdomain](../../cpp/appdomain.md) 를 참조하세요.

## <a name="example"></a>예제

다음 샘플 C2506를 생성합니다.

```
// C2506.cpp
// compile with: /clr /c
ref struct R {
   __declspec(process) static int n;   // C2506
   int o;   // OK
};
```