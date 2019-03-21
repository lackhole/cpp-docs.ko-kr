---
title: NMAKE의 종료 코드
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, exit codes
- exit codes
ms.assetid: 75f6913c-1da5-4572-a2d3-8a4e058bed15
ms.openlocfilehash: 25ea4060e7b7a968b6a9da78f344e645c5d43a44
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57826390"
---
# <a name="exit-codes-from-nmake"></a>NMAKE의 종료 코드

NMAKE 다음 종료 코드를 반환합니다.

|코드|의미|
|----------|-------------|
|0|오류 없음 (가능한 경우 경고)|
|1|불완전 한 빌드 (/K을 사용한 경우에 발생)|
|2|다음 중 하나 때문일 프로그램 오류:|
||메이크파일의-구문 오류|
||명령에서-오류 또는 종료 코드|
||-사용자가 중단|
|4|시스템 오류-메모리가 부족 합니다.|
|255|대상 최신 상태가 아닙니다 (/Q를 사용한 경우에 발생)|

## <a name="see-also"></a>참고자료

[NMAKE 실행](running-nmake.md)
