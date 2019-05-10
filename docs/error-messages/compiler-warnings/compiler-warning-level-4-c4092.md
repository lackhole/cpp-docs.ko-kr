---
title: 컴파일러 경고 (수준 4) C4092
ms.date: 11/04/2016
f1_keywords:
- C4092
helpviewer_keywords:
- C4092
ms.assetid: 396ae826-a892-4327-bd66-f4762376d72b
ms.openlocfilehash: a6949586cf3faa00aafed37a72e58c1b80266cf5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401386"
---
# <a name="compiler-warning-level-4-c4092"></a>컴파일러 경고 (수준 4) C4092

sizeof 'unsigned 반환합니다.

피연산자는 `sizeof` 연산자가 매우 큰 이므로 `sizeof` 부호 없는 반환 **긴**합니다. 이 경고는 Microsoft 확장에 발생 합니다 ([/Ze](../../build/reference/za-ze-disable-language-extensions.md)). ANSI 호환성 (/Za)에서 결과 대신 잘립니다.