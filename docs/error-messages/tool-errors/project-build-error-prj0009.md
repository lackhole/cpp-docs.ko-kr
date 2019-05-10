---
title: 프로젝트 빌드 오류 PRJ0009
ms.date: 11/04/2016
f1_keywords:
- PRJ0009
helpviewer_keywords:
- PRJ0009
ms.assetid: 89291778-cda4-495d-983f-ddcc06dfc98b
ms.openlocfilehash: 963b7c861f9e8ee7105ebdc23afff08c4be46465
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62359503"
---
# <a name="project-build-error-prj0009"></a>프로젝트 빌드 오류 PRJ0009

빌드 로그 작성에 대 한 열 수 없습니다.

**파일이 다른 프로세스에서 열려 있거나 쓰기 금지 되었는지 확인 합니다.**

설정한 후 합니다 **빌드 로깅** 속성을 **예** 빌드 또는 다시 작성 된 시각적 개체를 수행 하 고 C++ 단독 모드에서 빌드 로그를 열 수 없습니다.

검사는 **빌드 로깅** 열어 설정 합니다 **옵션** 대화 상자 (에 **도구** 메뉴에서 클릭 **옵션** 명령) 차례로 선택 **VC + + 빌드** 에 **프로젝트** 폴더입니다. 빌드 파일을 BuildLog.htm 이라고 하 고 중간 디렉터리 $(IntDir)에 기록 됩니다.

이 오류의 원인은 다음과 같습니다.

- 시각적 개체의 두 프로세스를 실행 하는 C++ 하 고 둘 다에서 동일한 프로젝트의 동일한 구성을 동시 빌드를 시도 합니다.

- 빌드 로그 파일의 파일을 잠그는 프로세스에서 열립니다.

- 사용자 파일을 만들 수 있는 권한이 없습니다.

- 현재 사용자 BuildLog.htm 파일에 대 한 쓰기 권한이 없습니다.