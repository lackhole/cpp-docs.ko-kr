---
title: '클립보드: 데이터 복사 및 붙여넣기'
ms.date: 11/04/2016
helpviewer_keywords:
- Clipboard, copying data to
- Clipboard, pasting
ms.assetid: 580e10be-241f-4f9f-94cf-8302edc5beef
ms.openlocfilehash: cff9094315dc97e2040eb4dbad25d044c7c51a81
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62327147"
---
# <a name="clipboard-copying-and-pasting-data"></a>클립보드: 데이터 복사 및 붙여넣기

이 항목에서는에서 OLE 응용 프로그램에서 클립보드에 복사 / 붙여넣기를 구현 하는 데 필요한 최소한의 작업만 설명 합니다. 참조 하는 것이 좋습니다 합니다 [데이터 개체 및 데이터 소스 (OLE)](../mfc/data-objects-and-data-sources-ole.md) 계속 하기 전에 항목입니다.

복사 또는 붙여넣기를 구현할 수 있습니다, 전에 편집 메뉴에서 복사, 잘라내기 및 붙여넣기 옵션을 처리 하는 함수를 제공 해야 합니다.

##  <a name="_core_copying_or_cutting_data"></a> 데이터 복사 또는 잘라내기

#### <a name="to-copy-data-to-the-clipboard"></a>클립보드에 데이터를 복사 하려면

1. 또는 있는지 여부를 복사할 데이터를 네이티브 데이터 포함 또는 연결 된 항목을 결정 합니다.

   - 데이터를 포함 하거나 연결을 하는 경우 가져오기에 대 한 포인터를 `COleClientItem` 선택 된 개체입니다.

   - 데이터가 네이티브 응용 프로그램 서버인 경우에서 파생 된 새 개체를 만들고 `COleServerItem` 선택한 데이터를 포함 합니다. 그렇지 않은 경우 만듭니다는 `COleDataSource` 데이터에 대 한 개체입니다.

1. 선택한 항목의 호출 `CopyToClipboard` 멤버 함수입니다.

1. 사용자가 복사 작업을 하는 대신 잘라내기 작업을 선택한 경우 응용 프로그램에서 선택한 데이터를 삭제 합니다.

이 시퀀스의 예제를 보려면 합니다 `OnEditCut` 하 고 `OnEditCopy` 함수는 MFC OLE 샘플 프로그램 [OCLIENT](../overview/visual-cpp-samples.md) 및 [HIERSVR](../overview/visual-cpp-samples.md)합니다. 1 단계 작업이 이미 완료 하므로 이러한 샘플 현재 선택 된 데이터에 대 한 포인터를 유지 하는 참고 합니다.

##  <a name="_core_pasting_data"></a> 데이터 붙여넣기

데이터 붙여넣기에 응용 프로그램에 데이터를 붙여넣을 때 사용할 형식을 선택 해야 하기 때문에 복사 하는 보다 복잡 한 경우

#### <a name="to-paste-data-from-the-clipboard"></a>클립보드의에서 데이터를 붙여 넣으려면

1. 뷰 클래스에서 구현 `OnEditPaste` 편집 메뉴에서 붙여넣기 옵션을 선택 하는 사용자를 처리할 수 있습니다.

1. 에 `OnEditPaste` 함수를 만드는 `COleDataObject` 개체와 호출 해당 `AttachClipboard` 이 개체를 클립보드에 데이터를 연결 하려면 멤버 함수입니다.

1. 호출 `COleDataObject::IsDataAvailable` 를 특정 형식으로 사용할 수 있는지 확인 합니다.

   또는 사용할 수 있습니다 `COleDataObject::BeginEnumFormats` 응용 프로그램에 가장 적합 한 찾을 때까지 다른 형식에 대 한 검색할 합니다.

1. 형식의 붙여넣기를 수행 합니다.

작동 방식에 대 한 예로, 구현을 참조를 `OnEditPaste` MFC OLE 샘플 프로그램에 정의 된 뷰 클래스의 멤버 함수 [OCLIENT](../overview/visual-cpp-samples.md) 하 고 [HIERSVR](../overview/visual-cpp-samples.md)합니다.

> [!TIP]
>  자체 함수로 붙여넣기 작업을 분리의 주요 장점은 끌어서 놓기 작업 중 응용 프로그램에서 데이터를 삭제할 때에 동일한 코드 붙여넣기를 사용할 수 있습니다. OCLIENT 및 HIERSVR, 프로그램 `OnDrop` 함수를 호출할 수도 `DoPasteItem`, 붙여넣기 작업을 구현 하는 작성 된 코드를 다시 사용 합니다.

편집 메뉴에서 옵션을 선택 하 여 붙여넣기를 처리 하려면 항목을 참조 하세요 [OLE의 대화 상자](../mfc/dialog-boxes-in-ole.md)합니다.

### <a name="what-do-you-want-to-know-more-about"></a>자세히 알아볼 항목

- [기타 서식 추가](../mfc/clipboard-adding-other-formats.md)

- [OLE 데이터 개체 및 데이터 원본 및 균일 한 데이터 전송](../mfc/data-objects-and-data-sources-ole.md)

- [OLE 끌어서 놓기](../mfc/drag-and-drop-ole.md)

- [OLE](../mfc/ole-background.md)

## <a name="see-also"></a>참고자료

[클립보드: OLE 클립보드 메커니즘 사용](../mfc/clipboard-using-the-ole-clipboard-mechanism.md)
