---
title: 모덜리스 대화 상자 만들기
ms.date: 11/04/2016
helpviewer_keywords:
- MFC dialog boxes [MFC], modeless
- modeless dialog boxes [MFC], creating
- MFC dialog boxes [MFC], creating
ms.assetid: 70d78c7f-3d40-477b-9f78-0f33c359f88b
ms.openlocfilehash: 71cca82e667ddbf5cfc4c2abb5880cd69c7fafae
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62388490"
---
# <a name="creating-modeless-dialog-boxes"></a>모덜리스 대화 상자 만들기

모덜리스 대화 상자에 대 한 대화 상자 클래스에서 사용자 고유의 공용 생성자를 제공 해야 합니다. 모덜리스 대화 상자를 만들려면 공용 생성자를 호출 하 고 다음 대화 상자 개체를 호출 [만들기](../mfc/reference/cdialog-class.md#create) 대화 상자 리소스를 로드 하는 멤버 함수입니다. 호출할 수 있습니다 **만들기** 중 이나 생성자 호출 후 합니다. 대화 상자 리소스 속성에 있으면 **WS_VISIBLE**, 대화 상자가 즉시 나타납니다. 그렇지 않으면 호출 해야 하는 경우 해당 [ShowWindow](../mfc/reference/cwnd-class.md#showwindow) 멤버 함수입니다.

## <a name="see-also"></a>참고자료

[대화 상자의 수명 주기](../mfc/life-cycle-of-a-dialog-box.md)
