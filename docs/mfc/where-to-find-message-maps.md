---
title: 메시지 맵을 찾을 장소
ms.date: 11/04/2016
helpviewer_keywords:
- macros, message map
- locating message maps
- message classes [MFC], finding
- message-map macros
ms.assetid: bf59fbc8-b222-42d3-b5d3-0a79aa3cb923
ms.openlocfilehash: d9b9a50062334822f34047b8e22e67541ccaa952
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62217863"
---
# <a name="where-to-find-message-maps"></a>메시지 맵을 찾을 장소

응용 프로그램 마법사를 사용 하 여 새 기본 응용 프로그램을 만들 때 응용 프로그램 마법사를 만들면 각 명령 대상 클래스에 대 한 메시지 맵을 작성 합니다. 이 파생된 응용 프로그램, 문서, 뷰 및 프레임 창 클래스를 포함합니다. 특정 메시지와 미리 정의 된 명령에 대 한 응용 프로그램 마법사에 의해 제공 항목이 이미 이러한 메시지 맵의 일부 및 일부는 추가할 처리기에 대 한 자리 표시자 일 뿐입니다.

클래스의 메시지 맵을 합니다. 클래스에 대 한 CPP 파일입니다. 응용 프로그램 마법사에서 만들어지는 기본 메시지 맵을 사용 하 여 작업을 사용 하 여 속성 창 메시지 및 명령을 처리 하는 각 클래스에 대 한 항목을 추가. 일반적인 메시지 맵 일부 항목을 추가 하면 다음과 같습니다.

[!code-cpp[NVC_MFCMessageHandling#1](../mfc/codesnippet/cpp/where-to-find-message-maps_1.cpp)]

메시지 맵 매크로의 컬렉션으로 구성 됩니다. 두 매크로 [BEGIN_MESSAGE_MAP](reference/message-map-macros-mfc.md#begin_message_map) 하 고 [END_MESSAGE_MAP](reference/message-map-macros-mfc.md#end_message_map), 메시지 맵에서 대괄호입니다. 다른 매크로 같은 `ON_COMMAND`, 메시지 지도의 내용을 입력 합니다.

> [!NOTE]
>  메시지 맵 매크로 세미콜론 뒤 없습니다.

클래스 추가 마법사를 사용 하 여 새 클래스를 만들 때 클래스에 대 한 메시지 맵을 제공 합니다. 또는 소스 코드 편집기를 사용 하 여 수동으로 메시지 맵을 만들 수 있습니다.

## <a name="see-also"></a>참고자료

[프레임워크가 메시지 맵을 검색하는 방법](../mfc/how-the-framework-searches-message-maps.md)
