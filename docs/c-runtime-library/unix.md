---
title: UNIX
ms.date: 11/04/2016
f1_keywords:
- unix
helpviewer_keywords:
- UNIX
- POSIX compatibility
- POSIX file names
- UNIX, compatibility
ms.assetid: 40792414-7a5b-415d-bfa8-2bfb1ebb3731
ms.openlocfilehash: edabb639d8f45680415473ad7b017d426b931ab5
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57745243"
---
# <a name="unix"></a>UNIX

프로그램을 UNIX로 이식하려면 다음 지침을 따르십시오.

- SYS 하위 디렉터리에서 헤더 파일을 제거하지 마십시오. 프로그램을 UNIX로 전송할 계획이 없는 경우에만 SYS 헤더 파일을 다른 위치에 둘 수 있습니다.

- 경로 및 파일 이름을 나타내는 문자열을 인수로 사용하는 루틴에서 UNIX와 호환되는 경로 구분 기호를 사용합니다. UNIX에서는 이러한 용도로 슬래시(/)만 지원하지만 Win32 운영 체제에서는 백슬래시(\\)와 슬래시(/)를 모두 지원합니다. 따라서 이 문서는 `#include` 문에서 UNIX와 호환되는 슬래시를 경로 구분 기호로 사용합니다. 그러나 Windows 운영 체제 명령 셸인 CMD.EXE에서는 명령 프롬프트에 입력한 명령에서 슬래시를 지원하지 않습니다.

- UNIX에서 올바르게 작동하는 경로 및 파일 이름(대/소문자 구분)을 사용합니다. Win32 운영 체제에서 FAT(파일 할당 테이블) 파일 시스템은 대/소문자를 구분하지 않습니다. NTFS 파일 시스템은 디렉터리 목록의 대/소문자를 유지하지만 파일 검색 및 기타 시스템 작업에서는 대/소문자를 무시합니다.

    > [!NOTE]
    >  이 버전의 Visual C++에서는 UNIX 호환성 정보가 함수 설명에서 제외되었습니다.

## <a name="see-also"></a>참고 항목

[호환성](../c-runtime-library/compatibility.md)
