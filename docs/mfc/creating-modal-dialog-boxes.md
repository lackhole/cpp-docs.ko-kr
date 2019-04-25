---
title: 모달 대화 상자 만들기
ms.date: 11/04/2016
helpviewer_keywords:
- modal dialog boxes [MFC], creating
- MFC dialog boxes [MFC], creating
- MFC dialog boxes [MFC], modal
ms.assetid: 26c7a68c-79f6-4862-a5a8-6024984644d2
ms.openlocfilehash: 5de6eeb616f32c7b8829d827988a972e41658530
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62174096"
---
# <a name="creating-modal-dialog-boxes"></a>모달 대화 상자 만들기

모달 대화 상자를 만들려면에 선언 된 두 public 생성자 중 하나를 호출 [CDialog](../mfc/reference/cdialog-class.md)합니다. 그런 다음 대화 상자 개체를 호출 [DoModal](../mfc/reference/cdialog-class.md#domodal) 멤버 함수 대화 상자를 표시 하 고 사용자가 확인 될 때까지 상호 작용을 관리 하거나 취소 합니다. 이 관리는 `DoModal`을 사용하여 대화 상자 모달을 만듭니다. 모달 대화 상자에 대해 `DoModal`에서는 대화 상자 리소스를 로드합니다.

## <a name="see-also"></a>참고자료

[대화 상자의 수명 주기](../mfc/life-cycle-of-a-dialog-box.md)
