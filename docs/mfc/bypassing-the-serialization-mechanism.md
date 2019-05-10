---
title: Serialization 메커니즘 건너뛰기
ms.date: 11/04/2016
helpviewer_keywords:
- archive objects [MFC]
- bypassing serialization
- archives [MFC], serialization
- serialization [MFC], bypassing
- archives [MFC]
- serialization [MFC], role of framework
- serialization [MFC], overriding
ms.assetid: 48d4a279-b51c-4ba5-81cd-ed043312b582
ms.openlocfilehash: 1937098de30884be327c67a698dbb0023be248bb
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64345196"
---
# <a name="bypassing-the-serialization-mechanism"></a>Serialization 메커니즘 건너뛰기

앞에서 설명한 것 처럼 프레임 워크 / 파일에서 데이터를 읽고는 기본 방법을 제공 합니다. 유용한 많은 응용 프로그램의 요구에 맞는 보관 개체를 통해 직렬화 합니다. 이러한 응용 프로그램 및 파일을 읽고 메모리에 완전히, 사용자가 파일을 업데이트할 수 있습니다 다음 다시 디스크에 업데이트 된 버전을 씁니다.

그러나 일부 응용 프로그램 데이터에서 매우 다른 방식으로 작동 하 고 이러한 응용 프로그램 아카이브를 통한 serialization 적합 하지 않습니다. 데이터베이스 프로그램, 대용량 파일의 일부만 편집 하는 프로그램, 텍스트 전용 파일을 작성 하는 프로그램 및 데이터 파일을 공유 하는 프로그램을 예로 들 수 있습니다.

이러한 경우 재정의할 수 있습니다 합니다 [직렬화](../mfc/reference/cobject-class.md#serialize) 중재를 통해 파일 작업을 다른 방식으로 함수를 [CFile](../mfc/reference/cfile-class.md) 개체 대신 [CArchive](../mfc/reference/carchive-class.md) 개체입니다.

사용할 수는 `Open`, `Read`를 `Write`, `Close`, 및 `Seek` 클래스의 멤버 함수 `CFile` 파일을 열려면 파일 포인터를 이동 레코드 (지정 된 바이트 수를 읽을 파일에서 특정 시점 (검색) )이 시점에서 사용자가 레코드를 업데이트 하 고 다시 동일한 지점을 검색 레코드를 파일에 다시 쓸 수 있도록 합니다. 프레임 워크는 파일을 열고 사용할 수는 `GetFile` 클래스의 멤버 함수 `CArchive` 에 대 한 포인터를 가져오려고 합니다 `CFile` 개체입니다. 훨씬 더 정교 하 고 유연한 사용 하기 위해 재정의할 수 있습니다 합니다 [OnOpenDocument](../mfc/reference/cdocument-class.md#onopendocument) 하 고 [OnSaveDocument](../mfc/reference/cdocument-class.md#onsavedocument) 클래스의 멤버 함수 `CWinApp`합니다. 자세한 내용은 클래스를 참조 하세요 [CFile](../mfc/reference/cfile-class.md) 에 *MFC 참조*합니다.

이 시나리오에서는 프로그램 `Serialize` 재정의 하지 하려는 경우가 아니면, 예를 들어 문서를 닫을 때 최신 상태로 유지 하는 파일 헤더를 읽고 있습니다.

## <a name="see-also"></a>참고자료

[문서 사용](../mfc/using-documents.md)
