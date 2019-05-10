---
title: 프로젝트 빌드 오류 PRJ0032
ms.date: 11/04/2016
f1_keywords:
- PRJ0032
helpviewer_keywords:
- PRJ0032
ms.assetid: bc6acbea-4041-4237-8b5a-f0434705d89f
ms.openlocfilehash: f1f292f3979c993a8fa8cb8ff44653ac7124b121
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64344354"
---
# <a name="project-build-error-prj0032"></a>프로젝트 빌드 오류 PRJ0032

프로젝트 수준의 사용자 지정 빌드 단계의 '출력' 속성이 '매크로' out 'macro_expansion' 계산 되는 포함 되어 있습니다.

프로젝트에서 사용자 지정 빌드 단계를 매크로 평가 문제 때문에 잘못 된 출력을 했습니다. 이 오류는 경로 잘못 구성 된 문자 또는 파일 경로에서 사용할 수 없는 문자 조합을 포함 하는 것을 의미할 수도 수 있습니다.

이 오류를 해결 하려면 매크로 수정 하거나 경로 지정을 수정 합니다. 확인 된 경로가 프로젝트 디렉터리의 절대 경로 보여 줍니다.