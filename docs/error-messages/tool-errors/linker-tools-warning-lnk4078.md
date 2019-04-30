---
title: 링커 도구 경고 LNK4078
ms.date: 11/04/2016
f1_keywords:
- LNK4078
helpviewer_keywords:
- LNK4078
ms.assetid: 5a16796d-6caf-42d9-8f65-b042843eafb8
ms.openlocfilehash: d20eb0523ffebe9229d05b6316772259661f6020
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62399941"
---
# <a name="linker-tools-warning-lnk4078"></a>링커 도구 경고 LNK4078

서로 다른 특성을 지닌 여러 '섹션 이름' 섹션

두 링크 찾을 또는 더 많은 섹션 이름과 다른 특성입니다.

이 경고의 링크 또는 LIB 이전 버전에서 생성 된 가져오기 라이브러리 또는 내보내기 파일에서 발생할 수 있습니다.

파일 및 다시 연결을 다시 만듭니다.

## <a name="example"></a>예제

LNK4078 주요 변경에 의해 발생할 수도 있습니다: 의해 명명 된 섹션 [init_seg](../../preprocessor/init-seg.md) x86 읽기/쓰기를 이제 읽기 전용입니다.

다음 샘플 LNK4078를 생성합니다.

```
// LNK4078.cpp
// compile with: /W1
// LNK4078 expected
#include <stdio.h>
#pragma warning(disable : 4075)
typedef void (__cdecl *PF)(void);
int cxpf = 0;   // number of destructors to call
PF pfx[200];   // pointers to destructors.

struct A { A() {} };

int myexit (PF pf) { return 0; }

#pragma section(".mine$a", read, write)
// try the following line instead
// #pragma section(".mine$a", read)
__declspec(allocate(".mine$a")) int ii = 1;

#pragma section(".mine$z", read, write)
// try the following line instead
// #pragma section(".mine$z", read)
__declspec(allocate(".mine$z")) int i = 1;

#pragma data_seg()
#pragma init_seg(".mine$m", myexit)
A bbbb;
A cccc;
int main() {}
```