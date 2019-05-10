---
title: 컴파일러 오류 C2195
ms.date: 11/04/2016
f1_keywords:
- C2195
helpviewer_keywords:
- C2195
ms.assetid: 9f9f035c-9c51-4173-a8ea-c6f907fc5c63
ms.openlocfilehash: 9d0fdb3623a86adb07e910b186305f3e468d24b8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62174538"
---
# <a name="compiler-error-c2195"></a>컴파일러 오류 C2195

'identifier': 데이터 세그먼트

합니다 `code_seg` pragma를 사용 하는 세그먼트 이름을 사용 합니다 `data_seg` pragma입니다.

다음 샘플에서는 C2195 오류가 생성 됩니다.

```
// C2195.cpp
#pragma data_seg("MYDATA")
#pragma code_seg("MYDATA")   // C2195
#pragma code_seg("MYDATA2")   // OK
```