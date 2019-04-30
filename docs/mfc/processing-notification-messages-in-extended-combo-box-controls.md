---
title: 확장된 콤보 상자 컨트롤에서 알림 메시지 처리
ms.date: 11/04/2016
helpviewer_keywords:
- extended combo boxes [MFC], notifications
- notifications [MFC], extended combo box controls
ms.assetid: 4e442758-d054-4746-bb1a-6ff84accb127
ms.openlocfilehash: 1890267f26ef43fd1dbf8fdea28f02e3d882d475
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62378195"
---
# <a name="processing-notification-messages-in-extended-combo-box-controls"></a>확장된 콤보 상자 컨트롤에서 알림 메시지 처리

사용자가 확장된 콤보 상자를 조작하면 컨트롤(`CComboBoxEx`)이 해당 부모 창(일반적으로 뷰 또는 대화 상자 개체)에 알림 메시지를 보냅니다. 이에 대한 응답으로 작업을 수행하려는 경우 이러한 메시지를 처리합니다. 예를 들어 사용자가 드롭다운 목록을 활성화 하거나 컨트롤의 편집 상자에서 클릭을 CBEN_BEGINEDIT 알림이 전송 됩니다.

속성 창을 사용하면 구현하려는 해당 메시지의 부모 클래스에 알림 처리기를 추가할 수 있습니다.

다음 목록에서는 확장된 콤보 상자 컨트롤에서 전송되는 다양한 알림에 대해 설명합니다.

- CBEN_BEGINEDIT 사용자가 드롭다운 목록을 활성화 하거나 컨트롤의 편집 상자에서 클릭을 전송 합니다.

- CBEN_DELETEITEM 항목 삭제 된 경우 전송 합니다.

- CBEN_DRAGBEGIN 컨트롤의 편집 부분에 표시 되는 항목의 이미지를 끌기 시작할 때 전송 합니다.

- CBEN_ENDEDIT 사용자가 편집 상자 내에서 작업을 완료 하거나 컨트롤의 드롭다운 목록에서 항목을 선택한 경우 전송 합니다.

- CBEN_GETDISPINFO 콜백 항목에 대 한 표시 정보를 검색 하기 위해 전달 합니다.

- CBEN_INSERTITEM 컨트롤에 새 항목이 삽입 된 경우 전송 합니다.

## <a name="see-also"></a>참고자료

[CComboBoxEx 사용](../mfc/using-ccomboboxex.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
