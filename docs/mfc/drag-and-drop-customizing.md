---
title: '끌어서 놓기: 사용자 지정'
ms.date: 11/04/2016
helpviewer_keywords:
- drag and drop [MFC], implementing in non-OLE applications
- drag and drop [MFC], customizing behavior
- drag and  [MFC], COleDataSource object
- drag and drop [MFC], calling DoDragDrop
- OLE drag and drop [MFC], customizing behavior
ms.assetid: 03369d3e-46bf-4140-b58c-d0c9657cf38a
ms.openlocfilehash: b4749f8d45c962f8b9217e4c6367538d3e6a3608
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62405952"
---
# <a name="drag-and-drop-customizing"></a>끌어서 놓기: 사용자 지정

대부분의 애플리케이션에서는 끌어 놓기 기능의 기본 구현으로도 충분합니다. 하지만 일부 애플리케이션에서는 이러한 표준 동작을 변경해야 할 수 있습니다. 이 문서에서는 이러한 기본값을 변경하는 데 필요한 단계를 설명합니다. 또한 이 기술을 사용해서 놓기 대상으로 복합 문서를 지원하지 않는 애플리케이션을 설정할 수 있습니다.

표준 OLE 끌어 놓기 동작을 사용자 지정하거나 비OLE 애플리케이션이 있는 경우, 데이터를 포함할 `COleDataSource` 개체를 만들어야 합니다. 사용자가 끌어 놓기 작업을 시작하면 코드가 끌어 놓기 작업을 지원하는 다른 클래스 대신 이 개체에서 `DoDragDrop` 함수를 호출해야 합니다.

필요에 따라 `COleDropSource` 개체를 만들어서 변경하려는 동작 유형에 따라 놓기를 제어하고 일부 함수를 재정의할 수 있습니다. 그런 다음 이러한 함수의 기본 동작을 변경하도록 이 놓기 소스 개체가 `COleDataSource::DoDragDrop`으로 전달됩니다. 이러한 여러 옵션을 통해 애플리케이션에서 끌어 놓기 작업을 지원하는 데 유연성을 크게 향상시킬 수 있습니다. 데이터 원본에 대 한 자세한 내용은 문서 참조 [데이터 개체 및 데이터 소스 (OLE)](../mfc/data-objects-and-data-sources-ole.md)합니다.

다음 함수를 재정의해서 끌어 놓기 작업을 사용자 지정할 수 있습니다.

|재정의|사용자 지정|
|--------------|------------------|
|`OnBeginDrag`|`DoDragDrop` 호출 후 끌기 시작 방법.|
|`GiveFeedback`|여러 놓기 결과에 대한 시각적 피드백(예: 커서 모양).|
|`QueryContinueDrag`|끌어 놓기 작업의 종료. 이 함수를 사용하면 놓기 작업 중 보조키 상태를 확인할 수 있습니다.|

## <a name="see-also"></a>참고자료

[끌어서 놓기(OLE)](../mfc/drag-and-drop-ole.md)<br/>
[COleDropSource 클래스](../mfc/reference/coledropsource-class.md)<br/>
[COleDataSource 클래스](../mfc/reference/coledatasource-class.md)
