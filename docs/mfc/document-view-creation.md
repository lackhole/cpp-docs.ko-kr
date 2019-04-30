---
title: 문서-뷰 만들기
ms.date: 11/04/2016
helpviewer_keywords:
- documents [MFC], creating
- views [MFC], and frame windows
- views [MFC], creating
- tables [MFC]
- MFC, views
- document/view architecture [MFC], creating document/view
- object creators
- MFC, documents
- tables [MFC], objects each MFC object creates
ms.assetid: bda14f41-ed50-439d-af9e-591174e7dd64
ms.openlocfilehash: b5f9b783e8e14744a816fd63b327ed95d9da8e8a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62240791"
---
# <a name="documentview-creation"></a>문서/뷰 만들기

프레임 워크의 구현을 제공 합니다 **새로 만들기** 및 **열기** 명령을 등의 **파일** 메뉴. 새 문서와 관련 된 보기 및 프레임 창 만들기에는 응용 프로그램 개체, 문서 서식 파일, 새로 만든된 문서 및 새로 만든된 프레임 창 간에 공동의 노력입니다. 다음 표에서 개체를 만드는 새로운 보여 줍니다.

### <a name="object-creators"></a>개체 작성자

|Creator|만듭니다.|
|-------------|-------------|
|Application 개체|문서 템플릿|
|문서 템플릿|문서|
|문서 템플릿|프레임 창|
|프레임 창|보기|

## <a name="see-also"></a>참고자료

[문서 템플릿 및 문서/뷰 만들기 프로세스](../mfc/document-templates-and-the-document-view-creation-process.md)<br/>
[문서 템플릿 만들기](../mfc/document-template-creation.md)<br/>
[MFC 개체 간 관계](../mfc/relationships-among-mfc-objects.md)<br/>
[새 문서, 창 및 뷰 만들기](../mfc/creating-new-documents-windows-and-views.md)
