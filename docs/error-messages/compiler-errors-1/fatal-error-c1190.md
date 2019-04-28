---
title: 심각한 오류 C1190
ms.date: 11/04/2016
f1_keywords:
- C1190
helpviewer_keywords:
- C1190
ms.assetid: dee2266d-6c40-4f6e-91db-f01e65f8d2bc
ms.openlocfilehash: 8bd0332770dd0771ac7a02574185a506cf6fd416
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62228907"
---
# <a name="fatal-error-c1190"></a>심각한 오류 C1190

관리되는 대상 코드에는 '/clr' 옵션을 사용해야 합니다.

CLR 구문을 사용하지만 **/clr**을 지정하지 않았습니다.

자세한 내용은 [/clr (Common Language Runtime Compilation)](../../build/reference/clr-common-language-runtime-compilation.md)을 참조하세요.

다음 샘플에서는 C1190을 생성합니다.

```
// C1190.cpp
// compile with: /c
__gc class A {};   // C1190
ref class A {};
```