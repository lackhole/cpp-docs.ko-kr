---
title: 대화 상자 데이터 유효성 검사
ms.date: 11/04/2016
helpviewer_keywords:
- validating data [MFC], message boxes
- data validation [MFC], dialog boxes
- dialog boxes [MFC], validating data
- validating data [MFC], dialog box data entry
- DDV (dialog data validation) [MFC]
- data validation [MFC], message boxes
ms.assetid: f070c309-2044-4ff2-8c92-1ec1ea84af58
ms.openlocfilehash: cef9941cccd49ca61f0a93472636656f7241a61e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62383817"
---
# <a name="dialog-data-validation"></a>대화 상자 데이터 유효성 검사

예제에 나와 있는 것 처럼 DDV 함수를 호출 하 여 데이터를 교환 하는 것 외에도 유효성 검사를 지정할 수 있습니다 [대화 상자 데이터 교환](../mfc/dialog-data-exchange.md)합니다. `DDV_MaxChars` 예에서 호출 아닌지 텍스트 상자 컨트롤에 입력 한 문자열이 20 자를 초과 합니다. DDV 함수는 일반적으로 유효성 검사가 실패 하 고 사용자 데이터를 다시 입력할 수 있도록 문제가 되는 컨트롤에 포커스를 둡니다 메시지 상자를 사용 하 여 사용자를 경고 합니다. 지정된 된 컨트롤에 대 한 DDV 함수는 동일한 컨트롤에 대 한 DDX 함수 직후 호출 되어야 합니다.

또한 사용자 고유의 사용자 지정 DDX 및 DDV 루틴을 정의할 수 있습니다. 이 고 DDX 및 DDV의 다른 측면에 대 한 내용은 참조 하세요 [MFC 기술 참고 26](../mfc/tn026-ddx-and-ddv-routines.md)합니다.

합니다 [멤버 변수 추가 마법사](../ide/add-member-variable-wizard.md) DDX는 일부만 작성 및 DDV 데이터 구조의 대 한 호출 수입니다.

## <a name="see-also"></a>참고자료

[대화 상자 데이터 교환 및 유효성 검사](../mfc/dialog-data-exchange-and-validation.md)<br/>
[대화 상자의 수명 주기](../mfc/life-cycle-of-a-dialog-box.md)<br/>
[대화 상자 데이터 교환](../mfc/dialog-data-exchange.md)
