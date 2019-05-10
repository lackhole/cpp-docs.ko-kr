---
title: 링커 도구 오류 LNK2004
ms.date: 11/04/2016
f1_keywords:
- LNK2004
helpviewer_keywords:
- LNK2004
ms.assetid: 07645371-e67b-4a2c-b0e0-dde24c94ef7e
ms.openlocfilehash: 8088494106aa702fda0497fa431e48267167a185
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62160421"
---
# <a name="linker-tools-error-lnk2004"></a>링커 도구 오류 LNK2004

gp 관련 픽스업 오버플로 '대상'; 짧은 'section' 섹션에서는 너무 크거나 범위를 벗어났습니다.

섹션 너무 큽니다.

이 오류를 해결 하려면 명시적으로 #pragma 섹션 (".sectionname", 읽기, 쓰기, long)을 통해 긴 섹션에서 데이터를 배치 하 고 사용 하 여 짧은 섹션의 크기를 줄일 `__declspec(allocate(".sectionname"))` 데이터 정의 및 선언 합니다.  예를 들면 다음과 같습니다.

```
#pragma section(".data$mylong", read, write, long)
__declspec(allocate(".data$mylong"))
char    rg0[1] = { 1 };
char    rg1[2] = { 1 };
char    rg2[4] = { 1 };
char    rg3[8] = { 1 };
char    rg4[16] = { 1 };
char    rg5[32] = { 1 };
```

또한 컴파일러는 long 데이터 섹션에 할당 하는 8 바이트 보다 큰 데이터 집합이 될 고유한 구조에 논리적으로 그룹화 된 데이터를 이동할 수 있습니다.  예를 들면 다음과 같습니다.

```
// from this...
int     w1  = 23;
int     w2 = 46;
int     w3 = 23*3;
int     w4 = 23*4;

// to this...
struct X {
    int     w1;
    int     w2;
    int     w3;
    int     w4;
} x  = { 23, 23*2, 23*3, 23*4 };
```

이 오류는 심각한 오류 뒤에 `LNK1165`입니다.