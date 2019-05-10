---
title: '방법: 상태 표시줄에 명령 정보 표시'
ms.date: 11/04/2016
helpviewer_keywords:
- prompts [MFC]
- displaying command status [MFC]
- status bars [MFC], message area
- status bars [MFC], displaying command information
ms.assetid: de895cbe-61ee-46bf-9787-76b247527d6d
ms.openlocfilehash: c93787b3799306d6008299e7c1be6e429bc4c2d9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62160291"
---
# <a name="how-to-display-command-information-in-the-status-bar"></a>방법: 상태 표시줄에 명령 정보 표시

응용 프로그램의 기본 구조를 만들려면 응용 프로그램 마법사를 실행 하면 도구 모음 및 상태 표시줄을 지원할 수 있습니다. 응용 프로그램 마법사에서 방금 한 가지 옵션 모두 지원 합니다. 상태 표시줄에 있는 경우 메뉴 항목 위에 포인터를 이동할 때 응용 프로그램이 자동으로 유용한 피드백을 제공 합니다. 자동으로 메뉴 항목을 강조 표시 되 면 프롬프트 문자열을 상태 표시줄에 표시. 예를 들어 경우 포인터 위로 이동 합니다 **잘라내기** 명령을 합니다 **편집** 메뉴 상태 표시줄에 "선택 영역을 잘라내어 클립보드에 저장 합니다." 메시지에 대 한 영역의 상태 표시줄에 표시 될 수 있습니다. 프롬프트를 지 원하는 메뉴 항목의 용도 이해 합니다. 이 도구 모음 단추를 클릭할 때에 작동 합니다.

프로그램에 추가한 메뉴 항목에 대 한 프롬프트 문자열을 정의 하 여이 상태 표시줄을 추가할 수 있습니다. 이렇게 하려면 메뉴 편집기의 메뉴 항목의 속성을 편집 하는 경우 프롬프트 문자열을 제공 합니다. 정의한 문자열을 응용 프로그램 리소스 파일에 저장 됩니다. 방법을 설명 하는 명령과 동일한 Id를 갖습니다.

기본적으로 응용 프로그램 마법사를 추가 **AFX_IDS_IDLEMESSAGE**, 프로그램은 새 메시지를 대기 하는 경우 표시 되는 표준 "준비" 메시지의 ID입니다. 메시지 "도움이 필요한 경우 F1 키를 누르십시오."으로 변경 된 응용 프로그램 마법사에서 상황에 맞는 도움말 옵션을 지정 하는 경우

## <a name="see-also"></a>참고자료

[메시지 처리 및 매핑](../mfc/message-handling-and-mapping.md)
