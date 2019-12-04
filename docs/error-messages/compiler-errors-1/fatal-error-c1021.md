---
title: 심각한 오류 C1021
ms.date: 11/04/2016
f1_keywords:
- C1021
helpviewer_keywords:
- C1021
ms.assetid: e23171f4-ca6b-40c0-a913-a2edc6fa3766
ms.openlocfilehash: 861e768563cf737d6925d5753d80cd9269eff4fe
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756892"
---
# <a name="fatal-error-c1021"></a>심각한 오류 C1021

'string' 전처리기 명령이 잘못되었습니다.

`string` 은 유효하지 않은 [전처리기 지시문](../../preprocessor/preprocessor-directives.md)입니다. 오류를 해결하려면 `string`에 대해 올바른 전처리기 이름을 사용합니다.

다음 샘플에서는 C1021을 생성합니다.

```cpp
// C1021.cpp
#BadPreProcName    // C1021 delete line
```
