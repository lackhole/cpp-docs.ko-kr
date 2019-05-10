---
title: 프로젝트 빌드 경고 PRJ0041
ms.date: 11/04/2016
f1_keywords:
- PRJ0041
helpviewer_keywords:
- PRJ0041
ms.assetid: dc9f4cf9-6bd5-4222-89e8-7802a59bb96b
ms.openlocfilehash: b0fceff05ffe35515965b7e0a880c8b4c941b07e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62297725"
---
# <a name="project-build-warning-prj0041"></a>프로젝트 빌드 경고 PRJ0041

누락 된 찾을 수 없습니다 '종속성' file '파일에 대 한 종속성입니다. 프로젝트가 빌드할 수 있지만이 파일을 찾을 때까지 만료 표시할 계속 될 수 있습니다.

파일 (리소스 파일 또는.idl/.odl 파일 예를 들어 포함 include 문이 프로젝트 시스템에서 확인할 수 없습니다.

프로젝트 시스템에서 전처리기 문 (예: #if)를 처리 하지 않으므로 잘못 된 문이 실질적으로 빌드의 일부로 되지 않을 수 있습니다.

이 경고를 해결 하려면.rc 파일에 모든 불필요 한 코드를 삭제 하거나 적절 한 이름의 자리 표시자 파일을 추가 합니다.