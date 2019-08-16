---
title: 프로젝트 빌드 오류 PRJ0016
ms.date: 11/04/2016
f1_keywords:
- PRJ0016
helpviewer_keywords:
- PRJ0016
ms.assetid: e9745336-883a-4c70-9c40-7753e02f0325
ms.openlocfilehash: 6733ef1f390f2ff377356dda3f7cd3ebfe10cc2b
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69509877"
---
# <a name="project-build-error-prj0016"></a>프로젝트 빌드 오류 PRJ0016

사용자의 보안 설정에 의해 프로세스가 생성 되지 않습니다. 이러한 설정은 빌드에 필요 합니다.

프로세스를 사용 하 여 프로세스를 만들 수 있는 권한이 없는 사용자로 로그인 되어 있습니다. 이 사용자 계정에 대 한 사용 권한 수준을 변경 하거나 계정 관리자에 게 문의 해야 합니다.

이 오류는 다음 레지스트리 키가 설정 된 경우에도 발생할 수 있습니다.

\\\HKCU\Software\Microsoft\Windows\CurrentVersion\Policies\Explorer\RestrictRun

이 오류를 해결 하려면 RestrictRun 키를 삭제 합니다. 이 레지스트리 키가 필요한 경우 키의 항목 목록에 **vcspawn** 를 추가 합니다.

이 오류가 발생 하는 또 다른 원인은 정책 설정에이 사용자 계정에 대 한 허용 된 창 프로그램으로 HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Policies\RestrictRun 레지스트리 키 아래에 VCSpawn가 포함 되어 있지 않기 때문입니다.

자세한 내용은 "허용 되는 Windows 응용 프로그램만 실행" 섹션의 [시스템 정책 설정 준수](/previous-versions/windows/desktop/Policy/adhering-to-system-policy-settings)를 참조 하세요.