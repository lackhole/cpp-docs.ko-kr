---
title: 심각한 오류 C1307
ms.date: 11/04/2016
f1_keywords:
- C1307
helpviewer_keywords:
- C1307
ms.assetid: 6f77d3d4-ba8a-476c-b540-aff19eb4efc4
ms.openlocfilehash: 1acdda77ac9cbf8d99752de3b78ab9c32bbb4cbc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62338534"
---
# <a name="fatal-error-c1307"></a>심각한 오류 C1307

프로필 데이터가 수집된 이후 프로그램이 편집되었습니다.

사용 하는 경우 [/ltcg: pgoptimize](../../build/reference/ltcg-link-time-code-generation.md), 링커 /ltcg: pginstrument 후 컴파일된 입력된 모듈을 검색 및 모듈에 없는 기존 프로필 데이터는 더 이상 관련이 지점에 변경 된 것입니다. 예를 들어 호출 그래프 다시 컴파일된 모듈에서 변경 된 경우 컴파일러에서 C1307를 생성 합니다.

이 오류를 해결 하려면 /ltcg: pginstrument 실행, 모든 테스트 실행을 다시 실행 하 고 /ltcg: pgoptimize를 실행 합니다. 실행 /ltcg: pginstrument 및 다시 실행 된 모든 테스트를 실행할 수 없습니다, 경우에 최적화 된 이미지를 만드는 /ltcg: pgupdate /ltcg: pgoptimize 대신 사용 합니다.