---
title: 컴파일러 오류 C3895
ms.date: 11/04/2016
f1_keywords:
- C3895
helpviewer_keywords:
- C3895
ms.assetid: 771b9fe5-d6d4-4297-bf57-e2f857722155
ms.openlocfilehash: c4b1cad9ef48f1f16b411aab46e1bb9285d69ff3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62385539"
---
# <a name="compiler-error-c3895"></a>컴파일러 오류 C3895

'var': 형식 데이터 멤버 'volatile' 일 수 없습니다

특정 유형의 예를 들어 데이터 멤버 [리터럴](../../extensions/literal-cpp-component-extensions.md) 또는 [initonly](../../dotnet/initonly-cpp-cli.md),이 하 여야 [volatile](../../cpp/volatile-cpp.md)합니다.

다음 샘플에서는 C3895 오류가 생성 됩니다.

```
// C3895.cpp
// compile with: /clr
ref struct Y1 {
   initonly
   volatile int data_var2;   // C3895
};
```