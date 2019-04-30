---
title: 'MFC ActiveX 컨트롤: 속성'
ms.date: 11/04/2016
helpviewer_keywords:
- properties [MFC], ActiveX controls
- MFC ActiveX controls [MFC], properties
- properties [MFC]
ms.assetid: b678a53c-0d9e-476f-8aa0-23b80baaba46
ms.openlocfilehash: 5e01854e7ae7acdc33275351d0d26a76dfeabc9b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62324326"
---
# <a name="mfc-activex-controls-properties"></a>MFC ActiveX 컨트롤: 속성

ActiveX 컨트롤을 해당 컨트롤 컨테이너와 통신 하는 이벤트를 발생 시킵니다. 컨테이너를 사용 하 여 메서드 및 속성 컨트롤을 사용 하 여 통신 하도록 합니다. 메서드 및 속성 비슷합니다 사용 및 용도 각각 멤버 함수 및 멤버 변수를 C++ 클래스입니다. 속성은 모든 컨테이너에 노출 되는 ActiveX 컨트롤의 데이터 멤버입니다. 자동화 클라이언트 및 ActiveX 컨트롤 컨테이너와 같은 ActiveX 컨트롤을 포함 하는 응용 프로그램에 대 한 인터페이스를 제공 하는 속성입니다.

속성은 특성이 라고도 합니다.

ActiveX 컨트롤 메서드에 대 한 자세한 내용은 문서를 참조 하세요. [MFC ActiveX 컨트롤: 메서드](../mfc/mfc-activex-controls-methods.md)합니다.

ActiveX 컨트롤에는 재고와 사용자 지정 메서드 및 속성을 모두 구현할 수 있습니다. 클래스 `COleControl` 스톡 속성에 대 한 구현을 제공 합니다. (스톡 속성 목록을 전체 문서를 참조 하세요. [MFC ActiveX 컨트롤: 스톡 속성 추가](../mfc/mfc-activex-controls-adding-stock-properties.md).) 개발자가 정의한 사용자 지정 속성을 ActiveX 컨트롤에 특수화 된 기능을 추가 합니다. 자세한 내용은 참조 하세요. [MFC ActiveX 컨트롤: 사용자 지정 속성 추가](../mfc/mfc-activex-controls-adding-custom-properties.md)합니다.

메서드와 마찬가지로 사용자 지정 및 스톡 속성, 속성 및 메서드와의 기존 멤버 함수를 처리 하는 디스패치 맵은 구성 된 메커니즘을 지는 `COleControl` 클래스입니다. 또한 이러한 속성에는 컨트롤에 추가 정보를 전달 하는 데 사용 하는 개발자는 매개 변수가 있을 수 있습니다.

다음 문서를 자세히 ActiveX 컨트롤 속성을 설명합니다.

- [MFC ActiveX 컨트롤: 스톡 속성 추가](../mfc/mfc-activex-controls-adding-stock-properties.md)

- [MFC ActiveX 컨트롤: 사용자 지정 속성 추가](../mfc/mfc-activex-controls-adding-custom-properties.md)

- [MFC ActiveX 컨트롤: 고급 속성 구현](../mfc/mfc-activex-controls-advanced-property-implementation.md)

- [MFC ActiveX 컨트롤: 앰비언트 속성 액세스](../mfc/mfc-activex-controls-accessing-ambient-properties.md)

## <a name="see-also"></a>참고자료

[MFC ActiveX 컨트롤](../mfc/mfc-activex-controls.md)
