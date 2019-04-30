---
title: 문서 뷰 아키텍처에 대 한 자세한 설명
ms.date: 11/04/2016
helpviewer_keywords:
- documents [MFC], views
- multiple views [MFC], updating from document
- document/view architecture [MFC]
- views [MFC], and user input
- documents [MFC], accessing data from view
- views [MFC], updating
- input [MFC], view class
- documents [MFC], multiple views
- document/view architecture [MFC], accessing data from view
- document/view architecture [MFC], about document/view architecture
- views [MFC], accessing document data from
ms.assetid: 4e7f65dc-b166-45d8-bcd5-9bb0d399b946
ms.openlocfilehash: 51f963acf5aacdfe4050a076d3bb0e651a92d021
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62392977"
---
# <a name="a-portrait-of-the-documentview-architecture"></a>문서/뷰 아키텍처에 대한 자세한 설명

문서 및 뷰는 일반적인 MFC 응용 프로그램 페어링 되었습니다. 데이터 문서에 저장 되지만 뷰 데이터에 대 한 액세스 권한 있는입니다. 표시에서 저장소 및 데이터 유지 관리를 구분 하는 문서 보기에서 분리 합니다.

## <a name="gaining-access-to-document-data-from-the-view"></a>문서 보기에서 데이터에 액세스

뷰에 해당 문서의 데이터 액세스 사용 하 여 합니다 [GetDocument](../mfc/reference/cview-class.md#getdocument) 뷰 클래스를 만들어 또는 문서에 대 한 포인터를 반환 하는 함수를 C++ `friend` 문서 클래스의 합니다. 뷰에 그리기 또는 다른 방법으로 조작할 준비가 될 때 데이터를 가져오기 위해 데이터에 대 한 액세스를 사용 합니다.

예를 들어 뷰에서 [OnDraw](../mfc/reference/cview-class.md#ondraw) 멤버 함수는 보기에 사용 `GetDocument` 문서 포인터를 가져오려고 합니다. 해당 포인터를 사용 하 여 액세스 하는 `CString` 문서에서 데이터 멤버입니다. 에 문자열을 전달 하는 뷰는 `TextOut` 함수입니다. 이 예제에 대 한 코드를 보려면 [뷰에 그리기](../mfc/drawing-in-a-view.md)합니다.

## <a name="user-input-to-the-view"></a>보기에 사용자 입력

보기 선택 영역 또는 데이터의 편집 자체 내에서 마우스 클릭을 해석할 수 있습니다. 마찬가지로 키 입력 데이터 입력 또는 편집으로 해석할 수 있습니다. 텍스트를 관리 하는 보기에서 사용자가 입력 문자열을 가정 합니다. 문서에 대 한 포인터를 가져옵니다 뷰와 포인터를 사용 하 여 일부 데이터 구조에 저장 하는 문서에 새 데이터를 전달 합니다.

## <a name="updating-multiple-views-of-the-same-document"></a>동일한 문서의 여러 뷰를 업데이트 하는 중

동일한 문서의 여러 뷰를 사용 하 여 응용 프로그램에서-같은 텍스트 편집기에서 분할자 창-보기 먼저 문서에 새 데이터를 전달 합니다. 문서를 호출 하는 것 [UpdateAllViews](../mfc/reference/cdocument-class.md#updateallviews) 문서 자체에 새 데이터를 반영 합니다. 업데이트를 모든 보기를 지시 하는 멤버 함수입니다. 이 뷰를 동기화합니다.

### <a name="what-do-you-want-to-know-more-about"></a>자세히 알아볼 항목

- [문서/뷰 아키텍처의 이점](../mfc/advantages-of-the-document-view-architecture.md)

- [문서/뷰 아키텍처의 대체](../mfc/alternatives-to-the-document-view-architecture.md)

## <a name="see-also"></a>참고자료

[문서/뷰 아키텍처](../mfc/document-view-architecture.md)
