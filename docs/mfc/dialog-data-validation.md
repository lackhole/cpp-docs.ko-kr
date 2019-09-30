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
ms.openlocfilehash: c89ed82b148062ddb64fa85eaabda12f44e59895
ms.sourcegitcommit: 1e6386be9084f70def7b3b8b4bab319a117102b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/30/2019
ms.locfileid: "71685773"
---
# <a name="dialog-data-validation"></a>대화 상자 데이터 유효성 검사

[대화 상자 데이터 교환](../mfc/dialog-data-exchange.md)의 예제에 표시 된 것 처럼 DDV 함수를 호출 하 여 데이터 교환 외에 유효성 검사를 지정할 수 있습니다. 예제의 @no__t 0 호출은 텍스트 상자 컨트롤에 입력 한 문자열이 20 자 보다 길지 않은지 확인 합니다. DDV 함수는 일반적으로 유효성 검사에 실패 한 경우 메시지 상자를 사용 하 여 사용자에 게 경고 하 고 사용자가 데이터를 다시 입력할 수 있도록 잘못 된 컨트롤에 포커스를 둡니다. 지정 된 컨트롤에 대 한 DDV 함수는 동일한 컨트롤에 대 한 DDX 함수 바로 다음에 호출 해야 합니다.

사용자 고유의 사용자 지정 DDX 및 DDV 루틴을 정의할 수도 있습니다. 이에 대 한 자세한 내용과 DDX 및 DDV의 다른 측면에 대 한 자세한 내용은 [MFC 기술 참고 26](../mfc/tn026-ddx-and-ddv-routines.md)을 참조 하십시오.

[멤버 변수 추가 마법사](../ide/add-member-variable-wizard.md) 는 데이터 맵에 모든 DDX 및 DDV 호출을 기록 합니다.

## <a name="see-also"></a>참조

[대화 상자 데이터 교환 및 유효성 검사](../mfc/dialog-data-exchange-and-validation.md)<br/>
[MFC에서 대화 상자 작업](../mfc/life-cycle-of-a-dialog-box.md)<br/>
[대화 상자 데이터 교환](../mfc/dialog-data-exchange.md)
