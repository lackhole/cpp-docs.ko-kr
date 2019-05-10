---
title: 컴파일러 경고 (수준 1) C4124
ms.date: 11/04/2016
f1_keywords:
- C4124
helpviewer_keywords:
- C4124
ms.assetid: c08c3a65-9584-47a1-a147-44f00c4b230e
ms.openlocfilehash: 04732619571420e777244b81bf4b93b775477a20
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62310983"
---
# <a name="compiler-warning-level-1-c4124"></a>컴파일러 경고 (수준 1) C4124

스택 검사 __fastcall 효율적입니다.

`__fastcall` 스택 검사를 사용할 수 있는 키워드를 사용 했습니다.

`__fastcall` 규칙 처리 속도가 빠른 코드도 생성 하지만 느린 코드 스택 검사를 수행 합니다. 사용 하는 경우 `__fastcall`를 사용 하 여 스택 검사 해제는 **check_stack** pragma 또는 /Gs 합니다.

이러한 조건에서 선언 된 첫 번째 함수에 대해서만 경고가 발생 합니다.