---
title: 모달 대화 상자 만들기
ms.date: 11/04/2016
helpviewer_keywords:
- modal dialog boxes [MFC], creating
- MFC dialog boxes [MFC], creating
- MFC dialog boxes [MFC], modal
ms.assetid: 26c7a68c-79f6-4862-a5a8-6024984644d2
ms.openlocfilehash: ed0fe3b7ef8aeddea01f573bfe8e1c01a6b5b443
ms.sourcegitcommit: 1e6386be9084f70def7b3b8b4bab319a117102b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/30/2019
ms.locfileid: "71685679"
---
# <a name="creating-modal-dialog-boxes"></a>모달 대화 상자 만들기

모달 대화 상자를 만들려면 [CDialog](../mfc/reference/cdialog-class.md)에 선언 된 두 공용 생성자 중 하나를 호출 합니다. 그런 다음 dialog 개체의 [DoModal](../mfc/reference/cdialog-class.md#domodal) 멤버 함수를 호출 하 여 대화 상자를 표시 하 고 사용자가 확인 또는 취소를 선택할 때까지 대화 상자와의 상호 작용을 관리 합니다. 이 관리는 `DoModal`을 사용하여 대화 상자 모달을 만듭니다. 모달 대화 상자에 대해 `DoModal`에서는 대화 상자 리소스를 로드합니다.

## <a name="see-also"></a>참조

[MFC에서 대화 상자 작업](../mfc/life-cycle-of-a-dialog-box.md)
