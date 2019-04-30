---
title: BSCMAKE 오류 BK1513
ms.date: 11/04/2016
f1_keywords:
- BK1513
helpviewer_keywords:
- BK1513
ms.assetid: 9ba87c09-8d82-4c80-b0cf-a8de63dcf9da
ms.openlocfilehash: c02e9b47b3d32e4d21914188b96913d6dff03127
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62279305"
---
# <a name="bscmake-error-bk1513"></a>BSCMAKE 오류 BK1513

비증분 업데이트에는 모든 .SBR 파일이 필요합니다.

하나 이상의 .sbr 파일이 잘렸으므로 BSCMAKE에서 새 찾아보기 정보(.bsc) 파일을 빌드할 수 없습니다. 잘린된.sbr 파일의 이름을 읽으십시오 합니다 [BK4502](../../error-messages/tool-errors/bscmake-warning-bk4502.md) 이 오류와 함께 제공 되는 경고입니다.

BSCMAKE는 잘린 .sbr 파일로 .bsc 파일을 업데이트할 수는 있지만 새 파일을 빌드할 수는 없습니다. BSCMAKE는 다음과 같은 경우 새 .bsc 파일을 빌드할 수 있습니다.

- .bsc 파일이 없는 경우

- .bsc 파일에 잘못된 파일 이름을 지정한 경우

- .bsc 파일이 손상된 경우

이 문제를 해결하려면 잘린.sbr 파일을 삭제하고 다시 빌드하거나 솔루션을 정리하고 다시 빌드합니다. (IDE에서 선택 **빌드할**, **솔루션 정리**를 선택한 후 **빌드**, **솔루션 다시 빌드**.)