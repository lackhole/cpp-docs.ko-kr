---
title: 레코드 뷰 클래스의 기능  (MFC Data Access)
ms.date: 11/04/2016
helpviewer_keywords:
- record views, classes
- record view classes
ms.assetid: e7b2820f-09c4-483f-83c0-317e8be42bdf
ms.openlocfilehash: 5f8de956065571109c988bd2940d21822bba7cfd
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59029877"
---
# <a name="features-of-record-view-classes--mfc-data-access"></a>레코드 뷰 클래스의 기능  (MFC Data Access)

클래스를 사용 하 여 양식 기반 데이터 액세스 프로그래밍을 수행할 수 있습니다 [CFormView](../mfc/reference/cformview-class.md), 되지만 [CRecordView](../mfc/reference/crecordview-class.md) 는 일반적으로 더 나은 클래스에서 파생 합니다. 외에 해당 `CFormView` 기능을 `CRecordView`:

- 폼 컨트롤과 연결 된 레코드 집합 개체 간에 대화 상자 데이터 교환 (DDX)를 제공합니다.

- 연결 된 레코드 집합 개체의 레코드를 탐색 하기 위한 첫 번째 이동, 다음으로 이동, 이전으로 이동 및 마지막으로 이동 명령을 처리 합니다.

- 사용자가 다른 레코드로 이동할 때 현재 레코드에 변경 내용을 업데이트 합니다.

탐색에 대 한 자세한 내용은 참조 하세요. [레코드 뷰: 레코드 뷰에서의 탐색 지원](../data/supporting-navigation-in-a-record-view-mfc-data-access.md)합니다.

## <a name="see-also"></a>참고자료

[레코드 뷰  (MFC Data Access)](../data/record-views-mfc-data-access.md)<br/>
[ODBC 드라이버 목록](../data/odbc/odbc-driver-list.md)