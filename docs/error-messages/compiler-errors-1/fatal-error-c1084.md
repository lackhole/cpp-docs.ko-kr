---
title: 심각한 오류 C1084
ms.date: 11/04/2016
f1_keywords:
- C1084
helpviewer_keywords:
- C1084
ms.assetid: b2f273ef-3a14-4d5f-8ce0-7a11a0388fe6
ms.openlocfilehash: 8c90616165a7b47d4251ace998fd49c613f244b5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62208817"
---
# <a name="fatal-error-c1084"></a>심각한 오류 C1084

다음 파일 형식 파일을 읽을 수 없습니다. 'file': message

이 오류는 일반적으로 컴파일러에서 수행한 내부 시스템 API 호출 실패의 결과입니다. 이 오류는 발생 하는 경우 표시 되는 메시지에서 생성 됩니다 [_wcserror_s](../../c-runtime-library/reference/strerror-s-strerror-s-wcserror-s-wcserror-s.md) 하거나 [FormatMessage](/windows/desktop/api/winbase/nf-winbase-formatmessage)합니다.

다음 단계를 수행하면 C1084 오류를 해결하는 데 도움이 될 수 있습니다.

- 지정한 파일이 있는지 확인합니다.

- 지정한 파일에 액세스하는 데 적절한 권한이 설정되어 있는지 확인합니다.

- 명령줄 구문에서 설명 된 규칙에 맞는 [컴파일러 명령줄 구문](../../build/reference/compiler-command-line-syntax.md)합니다.

- 환경 변수 설정 되어 있는지 확인 **TMP** 하 고 **TEMP** 된 집합 뿐만 아니라 이러한 환경 변수가 참조 하는 디렉터리에 액세스 하려면 적절 한 권한을 적절 하 게 합니다. 참조 하는 드라이브 확인 해야 합니다 **TMP** 하 고 **TEMP** 환경 변수에 적절 한 양의 사용 가능한 공간을 포함 합니다.

- "잘못된 파일 번호"라는 메시지가 표시되면 백그라운드에서 컴파일하는 동안 지정한 파일이 전경에서 닫혀 있을 수 있습니다.

위의 진단을 수행한 후 클린 빌드를 수행합니다.