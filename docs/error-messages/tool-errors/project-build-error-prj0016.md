---
title: 프로젝트 빌드 오류 PRJ0016
ms.date: 11/04/2016
f1_keywords:
- PRJ0016
helpviewer_keywords:
- PRJ0016
ms.assetid: e9745336-883a-4c70-9c40-7753e02f0325
ms.openlocfilehash: ada89b074fd8e0c2bfc75ba833e9c5966a145312
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62359425"
---
# <a name="project-build-error-prj0016"></a>프로젝트 빌드 오류 PRJ0016

만들어지는 프로세스를 방지 하는 사용자의 보안 설정 합니다. 이러한 설정은 빌드에 필요 합니다.

프로세스를 사용 하 여 프로세스를 만들 수 있는 권한이 없는 사용자로 로그인 합니다. 이 사용자 계정에 대 한 사용 권한 수준을 변경 하거나 계정 관리자에 게 문의 해야 합니다.

다음 레지스트리 키 설정 된 경우에이 오류가 발생할 수 있습니다.

\\\HKCU\Software\Microsoft\Windows\CurrentVersion\Policies\Explorer\RestrictRun

이 오류를 해결 하려면 RestrictRun 키를 삭제 합니다. 이 레지스트리 키가 필요할 경우 추가 **vcspawn.exe** 는 키의 항목 목록에 있습니다.

이 오류는 정책 설정에 포함 되지 않습니다 VCSpawn.exe HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Policies\RestrictRun 레지스트리 키에서이 사용자 계정에 대해 허용 된 창 프로그램으로 나타납니다.

자세한 내용은 참조 하세요. [시스템 정책을 설정 준수](https://msdn.microsoft.com/library/aa372139)를 "허용 된 Windows 응용 프로그램 실행" 섹션에서.