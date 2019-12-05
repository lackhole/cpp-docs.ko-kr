---
title: ML 심각한 오류 A1017
ms.date: 08/30/2018
ms.custom: error-reference
f1_keywords:
- A1017
helpviewer_keywords:
- A1017
ms.assetid: bef0b312-5431-4e5a-b637-c19919acf01b
ms.openlocfilehash: 6fb0835cca135fc994866dc2453734d7b3012a64
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74856828"
---
# <a name="ml-fatal-error-a1017"></a>ML 심각한 오류 A1017

**소스 파일 이름이 없습니다.**

ML에서 조합 하거나 링커에 전달할 파일을 찾을 수 없습니다.

이 오류는 작업할 파일 이름을 지정 하지 않고 ML 명령줄 옵션을 제공 하는 경우에 생성 됩니다. 확장명이 .asm이 아닌 파일을 조합 하려면 **/Ta** 명령줄 옵션을 사용 합니다.

ML 환경 변수가 명령줄 옵션을 포함 하는 경우 매개 변수 없이 ML을 호출 하 여이 오류를 생성할 수도 있습니다.

## <a name="see-also"></a>참조

[ML 오류 메시지](../../assembler/masm/ml-error-messages.md)<br/>