---
title: 레코드 뷰 사용  (MFC Data Access)
ms.date: 11/04/2016
helpviewer_keywords:
- record views, customizing default code
ms.assetid: 91f2828f-0666-4273-ae28-e4703fd98521
ms.openlocfilehash: 9d64fc26e1c78bad0431bc9b10dd5117c4866159
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59029358"
---
# <a name="using-a-record-view--mfc-data-access"></a>레코드 뷰 사용  (MFC Data Access)

이 항목에서는 마법사가 자동으로 작성하는 레코드 뷰의 기본 코드를 사용자 지정하는 일반적인 방법을 설명합니다. 일반적으로 사용 하 여 레코드 선택을 제한 하려면를 [필터](../data/odbc/recordset-filtering-records-odbc.md) 하거나 [매개 변수](../data/odbc/recordset-parameterizing-a-recordset-odbc.md), 아마도 [정렬](../data/odbc/recordset-sorting-records-odbc.md) 레코드를 SQL 문을 사용자 지정 합니다.

사용 하 여 `CRecordView` 사용 하 여 훨씬 동일 [CFormView](../mfc/reference/cformview-class.md)합니다. 기본적인 방식은 레코드 뷰를 사용하여 단일 레코드 집합의 레코드를 표시하고 필요에 따라 업데이트하는 것입니다. 그 외에도 물론에 설명 된 대로 다른 레코드 집합을 사용 하려는 [레코드 뷰: 두 번째 레코드 집합에서 목록 상자 채우기](../data/filling-a-list-box-from-a-second-recordset-mfc-data-access.md)합니다.

## <a name="see-also"></a>참고자료

[레코드 뷰  (MFC Data Access)](../data/record-views-mfc-data-access.md)<br/>
[ODBC 드라이버 목록](../data/odbc/odbc-driver-list.md)