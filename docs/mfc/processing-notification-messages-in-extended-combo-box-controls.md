---
title: 확장된 콤보 상자 컨트롤에서 알림 메시지 처리
ms.date: 11/04/2016
helpviewer_keywords:
- extended combo boxes [MFC], notifications
- notifications [MFC], extended combo box controls
ms.assetid: 4e442758-d054-4746-bb1a-6ff84accb127
ms.openlocfilehash: 044cef644f746f7cb70944805882bd8e2f2806b4
ms.sourcegitcommit: 3caf5261b3ea80d9cf14038c116ba981d655cd13
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/11/2019
ms.locfileid: "70908104"
---
# <a name="processing-notification-messages-in-extended-combo-box-controls"></a>확장된 콤보 상자 컨트롤에서 알림 메시지 처리

사용자가 확장된 콤보 상자를 조작하면 컨트롤(`CComboBoxEx`)이 해당 부모 창(일반적으로 뷰 또는 대화 상자 개체)에 알림 메시지를 보냅니다. 이에 대한 응답으로 작업을 수행하려는 경우 이러한 메시지를 처리합니다. 예를 들어 사용자가 드롭다운 목록을 활성화 하거나 컨트롤의 편집 상자를 클릭 하면 CBEN_BEGINEDIT 알림이 전송 됩니다.

[클래스 마법사](reference/mfc-class-wizard.md) 를 사용 하 여 구현 하려는 메시지의 부모 클래스에 알림 처리기를 추가 합니다.

다음 목록에서는 확장된 콤보 상자 컨트롤에서 전송되는 다양한 알림에 대해 설명합니다.

- CBEN_BEGINEDIT 사용자가 드롭다운 목록을 활성화 하거나 컨트롤의 편집 상자를 클릭 하면 전송 됩니다.

- 항목이 삭제 될 때 전송 되는 CBEN_DELETEITEM입니다.

- CBEN_DRAGBEGIN 사용자가 컨트롤의 편집 부분에 표시 된 항목의 이미지를 끌기 시작 하면 전송 됩니다.

- CBEN_ENDEDIT 사용자가 편집 상자 내에서 작업을 완료 하거나 컨트롤의 드롭다운 목록에서 항목을 선택 했을 때 전송 됩니다.

- CBEN_GETDISPINFO를 전송 하 여 콜백 항목에 대 한 표시 정보를 검색 합니다.

- 새 항목이 컨트롤에 삽입 되 면 CBEN_INSERTITEM 전송 됩니다.

## <a name="see-also"></a>참고자료

[CComboBoxEx 사용](../mfc/using-ccomboboxex.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
