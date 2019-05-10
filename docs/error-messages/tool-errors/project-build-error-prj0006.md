---
title: 프로젝트 빌드 오류 PRJ0006
ms.date: 11/04/2016
f1_keywords:
- PRJ0006
helpviewer_keywords:
- PRJ0006
ms.assetid: ce092be4-1652-414f-8cb5-b97ef5841f89
ms.openlocfilehash: d62c774411fda80a3e94044b3272567177328ff5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62359659"
---
# <a name="project-build-error-prj0006"></a>프로젝트 빌드 오류 PRJ0006

'File' 임시 파일을 열 수 없습니다. 파일이 있는지, 그리고 디렉터리 쓰기 금지 되어 있는지 확인 합니다.

Visual C++ 빌드 프로세스 중에 임시 파일을 만들지 못했습니다. 이 대 한 이유:

- 임시 디렉터리가 없습니다.

- 읽기 전용으로 임시 디렉터리입니다.

- 디스크 공간이 부족 합니다.

- $ (Intdir) 폴더는 읽기 전용 이거나 읽기 전용 된 임시 파일을 포함 합니다.

또한 오류 PRJ0007 다음 경우에이 오류가 발생 합니다. 'Directory' 출력 디렉터리를 만들지 못했습니다. 오류 PRJ0007 $ (intdir) 디렉터리를 만들 수 없습니다를 일시적으로 파일의 생성을 나타내므로 실패를 의미 합니다.

지정할 때마다 임시 파일이 생성 됩니다.

- 응답 파일입니다.

- 사용자 지정 빌드 단계입니다.

- 빌드 이벤트입니다.