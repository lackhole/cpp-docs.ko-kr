---
title: 컴파일러 오류 C2195
ms.date: 11/04/2016
f1_keywords:
- C2195
helpviewer_keywords:
- C2195
ms.assetid: 9f9f035c-9c51-4173-a8ea-c6f907fc5c63
ms.openlocfilehash: 748516dbcdf5e135964e720d6215f31091bfed9e
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758530"
---
# <a name="compiler-error-c2195"></a>컴파일러 오류 C2195

' identifier ': 데이터 세그먼트입니다.

`code_seg` pragma는 `data_seg` pragma와 함께 사용 된 세그먼트 이름을 사용 합니다.

다음 샘플에서는 C2195를 생성 합니다.

```cpp
// C2195.cpp
#pragma data_seg("MYDATA")
#pragma code_seg("MYDATA")   // C2195
#pragma code_seg("MYDATA2")   // OK
```
