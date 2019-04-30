---
title: 컴파일러 경고(수준 1) C4650
ms.date: 11/04/2016
f1_keywords:
- C4650
helpviewer_keywords:
- C4650
ms.assetid: 3190b3e3-dcd6-4846-939b-f900ab652b2a
ms.openlocfilehash: ea3f1b6e792239692960e74c8360c6c3a1323815
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62393534"
---
# <a name="compiler-warning-level-1-c4650"></a>컴파일러 경고(수준 1) C4650

미리 컴파일된 헤더에는 없는 정보가 디버깅 헤더의 전역 기호만 사용할 수 있습니다.

Microsoft 기호 디버깅 정보를 사용 하 여 미리 컴파일된 헤더 파일을 컴파일되지 않았습니다.

에 연결 하는 경우 결과 실행 파일 또는 동적 연결 라이브러리 파일의 미리 컴파일된 헤더에 포함 된 로컬 기호 디버깅 정보 포함 되지 않습니다.

이 경고를 사용 하 여 미리 컴파일된 헤더 파일을 컴파일하여 방지할 수 있습니다 합니다 [/Zi](../../build/reference/z7-zi-zi-debug-information-format.md) 명령줄 옵션입니다.