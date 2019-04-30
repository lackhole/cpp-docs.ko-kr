---
title: 컴파일러 오류 C2356
ms.date: 11/04/2016
f1_keywords:
- C2356
helpviewer_keywords:
- C2356
ms.assetid: 84d5a816-9a61-4d45-9978-38e485bbf767
ms.openlocfilehash: 0166cce6011017b8a18821666083f7c47f58b7a9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62302542"
---
# <a name="compiler-error-c2356"></a>컴파일러 오류 C2356

초기화 세그먼트 변환 단위 동안 바뀌지 않아야 합니다.

가능한 원인:

- `#pragma init_seg` 세그먼트 초기화 코드 앞에

- `#pragma init_seg` 앞에 다른 `#pragma init_seg`

를 해결 하려면 세그먼트 초기화 코드 모듈의 시작 부분으로 이동 합니다. 여러 영역을 초기화 해야 하는 경우 모듈을 구분 하기를 이동 합니다.

다음 샘플에서는 C2356를 생성합니다.

```
// C2356.cpp
#pragma warning(disable : 4075)

int __cdecl myexit(void (__cdecl *)());
int __cdecl myexit2(void (__cdecl *)());

#pragma init_seg(".mine$m",myexit)
#pragma init_seg(".mine$m",myexit2)   // C2356
```