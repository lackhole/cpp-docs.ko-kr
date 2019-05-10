---
title: 데이터 교환
ms.date: 11/04/2016
helpviewer_keywords:
- property sheets [MFC], data exchange
- exchanging data with property sheets [MFC]
- DDX (dialog data exchange) [MFC], property sheets
ms.assetid: 689f02d0-51a9-455b-8ffb-5b44f0aefa28
ms.openlocfilehash: de82a337f19b7b2ac6039fd3f3c16ab67aa1dc99
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62405848"
---
# <a name="exchanging-data"></a>데이터 교환

대부분의 대화 상자와 마찬가지로 속성 시트 및 응용 프로그램 간의 데이터 교환을 속성 시트의 가장 중요 한 기능 중 하나입니다. 이 문서에서는이 작업을 수행 하는 방법을 설명 합니다.

속성 시트를 사용 하 여 데이터를 교환 하는 것은 실제로 속성 시트의 개별 속성 페이지를 사용 하 여 데이터를 교환 합니다. 속성 페이지를 사용 하 여 데이터를 교환 하기 위한 절차는 이후 대화 상자를 사용 하 여 데이터를 교환 하는 경우와 동일을 [CPropertyPage](../mfc/reference/cpropertypage-class.md) 개체가 방금 특수 [CDialog](../mfc/reference/cdialog-class.md) 개체입니다. 프로시저는 대화 상자 개체의 멤버 변수와 대화 상자에서에서 컨트롤 간에 데이터를 교환 하는 프레임 워크의 대화 상자 데이터 교환 (DDX) 기능을 활용 합니다.

속성 시트와 일반 대화 상자 데이터 교환에 대 한 중요 한 차이점은 속성 시트 속성 시트의 모든 페이지를 사용 하 여 데이터를 교환 해야 하므로 여러 페이지에는 DDX에 대 한 자세한 내용은 참조 하세요. [대화 상자 데이터 교환 및 유효성 검사](../mfc/dialog-data-exchange-and-validation.md)합니다.

다음 예에서는 뷰 및 속성 시트의 두 페이지 간에 교환할 데이터를 보여 줍니다.

[!code-cpp[NVC_MFCDocView#4](../mfc/codesnippet/cpp/exchanging-data_1.cpp)]

## <a name="see-also"></a>참고자료

[속성 시트](../mfc/property-sheets-mfc.md)
