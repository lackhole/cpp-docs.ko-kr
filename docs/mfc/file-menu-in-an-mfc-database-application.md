---
title: MFC 데이터베이스 애플리케이션의 파일 메뉴
ms.date: 11/04/2016
helpviewer_keywords:
- File menu
- database applications [MFC], File menu commands
ms.assetid: 92dafb75-c1b3-4860-80a0-87a83bfc36f2
ms.openlocfilehash: 6c9a195a81423417809b65b5edce32027071ad2e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62405783"
---
# <a name="file-menu-in-an-mfc-database-application"></a>MFC 데이터베이스 애플리케이션의 파일 메뉴

어떻게 해야 하면 Open, Close 해석, 저장 및 다른 이름으로 저장 명령을 파일 메뉴 MFC 데이터베이스 응용 프로그램을 만들고 직렬화를 사용 하지 않는 경우 다음은 몇 가지 제안 사항이이 질문에 대 한 스타일 지침은 없습니다 있기는 합니다.

- 파일 메뉴의 열려 있는 명령을 완전히 제거 합니다.

- 열기 명령을 데이터베이스로"열기"를 해석 하 고 사용자 응용 프로그램에서 인식 하는 데이터 원본 목록을 표시 합니다.

- 다른 이름으로 열기"프로필." 열기 명령을 해석합니다 His를 포함 하 여 사용자의 기본 설정과 같은 "사용자 프로필" 정보를 포함 하는 직렬화 된 문서를 저장할 파일을 사용 하지만 serialize 된 파일을 열 또는 자신의 로그인 ID (필요에 따라 암호 제외) 및 데이터 원본 자신이 가장에 대 한 열기를 유지 합니다. 최근에 사용 했습니다.

MFC 응용 프로그램 마법사 없는 문서 관련 파일 메뉴 명령을 사용 하 여 응용 프로그램 만들기를 지원 합니다. 선택 합니다 **데이터베이스 파일을 지원 하지 않는 뷰** 옵션을 합니다 **데이터베이스 지원** 페이지.

대개 하나 이상의 명령 처리기를 재정의 해야 하는 특수 한 방법으로 파일 메뉴 명령을 해석 하 여 `CWinApp`-클래스를 파생 합니다. 예를 들어, 완전히 재정의 하는 경우 `OnFileOpen` (구현 하는 `ID_FILE_OPEN` 명령)을 의미 "열려 있는 데이터베이스:"

- 기본 클래스 버전을 호출 하지 마십시오 `OnFileOpen`명령 프레임 워크의 기본 구현을 완전히 바꾸려는 때문입니다.

- 데이터 원본 목록 대화 상자를 표시 하는 처리기를 대신 사용 합니다. 호출 하 여 이러한 대화 상자를 표시할 수 있습니다 `CDatabase::OpenEx` 나 `CDatabase::Open` 매개 변수를 사용 하 여 **NULL**합니다. 사용자의 컴퓨터에서 모든 사용 가능한 데이터 소스를 표시 하는 ODBC 대화 상자가 열립니다.

- 저장을 제거할 단단히 싶을 일반적으로 데이터베이스 응용 프로그램 전체 문서를 저장 하지 않습니다, 때문에 serialize 된 문서를 사용 하 여 프로필 정보를 저장 하지 않는 한 구현으로 저장 합니다. 그렇지 않은 경우, 예를 들어, "트랜잭션을 커밋할." Save 명령을 구현할 수 있습니다. 참조 [Technical Note 22](../mfc/tn022-standard-commands-implementation.md) 이러한 명령을 재정의 하는 방법에 대 한 자세한 내용은 합니다.

## <a name="see-also"></a>참고자료

[Serialization: Serialization 및 입/출력 데이터베이스](../mfc/serialization-serialization-vs-database-input-output.md)
