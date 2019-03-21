---
title: 프로젝트 빌드 오류 PRJ0030
ms.date: 11/04/2016
f1_keywords:
- PRJ0030
helpviewer_keywords:
- PRJ0030
ms.assetid: c48b3727-e166-46e7-bcd7-3e5b2ac5c1d4
ms.openlocfilehash: aa1c8539247287f7644742857c3cb7de321a20a2
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57811478"
---
# <a name="project-build-error-prj0030"></a>프로젝트 빌드 오류 PRJ0030

매크로 확장 오류입니다. $(매크로)에 대해 수준 32를 초과 하는 재귀를 평가 합니다.

이 오류는 재귀 매크로에 의해 발생 합니다. 예를 들어, 설정 하는 경우는 **중간 디렉터리** 속성 (참조 [일반 속성 페이지 (프로젝트)](../../build/reference/general-property-page-project.md)) $ (IntDir), 재귀 해야 합니다.

이 오류를 해결 하려면 매크로 또는 매크로 정의 하는 데 사용 되는 측면에서 속성 정의 하지 않습니다.