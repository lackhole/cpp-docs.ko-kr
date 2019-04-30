---
title: 문서에서 명령 처리
ms.date: 11/04/2016
helpviewer_keywords:
- message maps [MFC], in document class
- command handling [MFC]
- documents [MFC], message maps
- message handling [MFC], WM_COMMAND messages
- command handling [MFC], commands in documents
- documents [MFC], handling messages in
ms.assetid: c7375584-27af-4275-b2fd-afea476785d0
ms.openlocfilehash: f3cce539d52bd04e97a6b5f84cbd833b05afb5bb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62240576"
---
# <a name="handling-commands-in-the-document"></a>문서에서 명령 처리

문서 클래스에는 메뉴 항목, 도구 모음 단추 또는 액셀러레이터 키에 의해 생성 되는 특정 명령을 처리할 수도 있습니다. 기본적으로 `CDocument` 저장을 처리 하 고 serialization을 사용 하는 파일 메뉴에서 명령 이름으로 저장 합니다. 데이터에 영향을 주는 다른 명령은 문서의 멤버 함수에 의해 처리할 수도 있습니다. 예를 들어 Scribble 프로그램에서 클래스 `CScribDoc` 모든 문서에 현재 저장 된 데이터를 삭제 하는 명확한 모든 편집 명령에 대 한 처리기를 제공 합니다. 문서에는 메시지 맵 있을 수 있지만 문서 보기와 달리 표준 Windows 메시지를 처리할 수 없습니다-만 **WM_COMMAND** 메시지 또는 "명령입니다."

## <a name="see-also"></a>참고자료

[문서 사용](../mfc/using-documents.md)
