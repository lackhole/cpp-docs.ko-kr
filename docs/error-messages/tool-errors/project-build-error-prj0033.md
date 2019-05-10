---
title: 프로젝트 빌드 오류 PRJ0033
ms.date: 11/04/2016
f1_keywords:
- PRJ0033
helpviewer_keywords:
- PRJ0033
ms.assetid: 84d4a052-0586-4b78-9315-81c1e8386c1e
ms.openlocfilehash: e074ee18508271b56686aa16f9012085ed3bd77d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62346923"
---
# <a name="project-build-error-prj0033"></a>프로젝트 빌드 오류 PRJ0033

사용자 지정 빌드에 대 한 ' 추가 종속성 ' 속성이 'macro_expansion' 매크로 대 한 파일에 포함 된 ' file' ' '로 확인 됨 단계입니다.

파일에서 사용자 지정 빌드 단계 추가 종속성 매크로 평가 문제 때문에 오류가 포함 되어 있습니다. 이 오류는 경로 잘못 구성 된 문자 또는 파일 경로에서 사용할 수 없는 문자 조합을 포함 하는 것을 의미할 수도 수 있습니다.

이 오류를 해결 하려면 매크로 수정 하거나 경로 지정을 수정 합니다. 확인 된 경로가 프로젝트 디렉터리의 절대 경로 보여 줍니다.