---
title: 컴파일러 경고(수준 1) C4794
ms.date: 11/04/2016
f1_keywords:
- C4794
helpviewer_keywords:
- C4794
ms.assetid: badc9c36-fa1a-4fec-929b-7bfda7a7b79f
ms.openlocfilehash: d44e3af88de9457fdc5c2df905ccbae22d3562da
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62280375"
---
# <a name="compiler-warning-level-1-c4794"></a>컴파일러 경고(수준 1) C4794

스레드 로컬 스토리지 변수 'variable'의 세그먼트가 'section name'에서 '.tls$'로 변경되었습니다.

.tls$로 시작하지 않는 섹션에 tls 변수를 넣기 위해 [#pragma data_seg](../../preprocessor/data-seg.md) 를 사용했습니다.

.tls$*x* 섹션은 [__declspec (thread)](../../cpp/thread.md) 변수가 정의된 개체 파일에 있습니다. EXE 또는 DLL의 .tls 섹션은 다음 섹션에서 발생합니다.

## <a name="example"></a>예제

다음 샘플에서는 C4794를 생성합니다.

```
// C4794.cpp
// compile with: /W1 /c
#pragma data_seg(".someseg")
__declspec(thread) int i;   // C4794

// OK
#pragma data_seg(".tls$9")
__declspec(thread) int j;
```