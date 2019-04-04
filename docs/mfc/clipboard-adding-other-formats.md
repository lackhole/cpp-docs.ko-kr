---
title: '클립보드: 기타 서식 추가'
ms.date: 11/04/2016
helpviewer_keywords:
- formats [MFC], Clipboard
- Clipboard, formats
- custom formats, placing on Clipboard
- custom formats
- registering custom Clipboard data formats
- custom Clipboard data formats
ms.assetid: aea58159-65ed-4385-aeaa-3d9d5281903b
ms.openlocfilehash: 182abe71ccc9552c113ebb114b4351178e48b096
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58766849"
---
# <a name="clipboard-adding-other-formats"></a>클립보드: 기타 서식 추가

이 항목에서는 특히 OLE 지원에 대 한 지원 되는 형식의 목록을 확장 하는 방법에 설명 합니다. 항목 [클립보드: 복사 및 붙여넣기 데이터](../mfc/clipboard-copying-and-pasting-data.md) 클립보드에서 복사 / 붙여넣기를 지 원하는 데 필요한 최소 구현에 설명 합니다. 구현할 모든 인 경우만 클립보드에 형식은 **CF_METAFILEPICT**를 **CF_EMBEDSOURCE**를 **CF_OBJECTDESCRIPTOR**, 했으며 **CF_LINKSOURCE**합니다. 대부분의 응용 프로그램에는이 세 가지 보다 자세한 형식이 클립보드에 필요 합니다.

##  <a name="_core_registering_custom_formats"></a> 사용자 지정 형식 등록

모든 사용자 지정 클립보드 형식을 등록 하는 경우 사용 동일한 절차에 따라 사용자 고유의 사용자 지정 형식을 만들려면: 형식의 이름을 전달 합니다 **됩니다** 함수 및 해당 반환 값 형식 ID로 사용

##  <a name="_core_placing_formats_on_the_clipboard"></a> 클립보드에 배치할 형식

클립보드에 배치 된 추가 형식에 추가 하려면를 재정의 해야 합니다 `OnGetClipboardData` 하나에서 파생 된 클래스의 함수가 `COleClientItem` 또는 `COleServerItem` (인지에 따라 데이터를 복사할 기본). 이 함수에서 다음 절차를 사용 해야 합니다.

#### <a name="to-place-formats-on-the-clipboard"></a>클립보드에 형식을 추가 하려면

1. `COleDataSource` 개체를 만듭니다.

1. 이 데이터 원본을 호출 하 여 네이티브 데이터 형식을 지원 되는 형식 목록에 추가 하는 함수에 전달할 `COleDataSource::CacheGlobalData`합니다.

1. 표준 형식을 호출 하 여 추가 `COleDataSource::CacheGlobalData` 지원 하려는 각 표준 형식에 대 한 합니다.

이 방법은 MFC OLE 샘플 프로그램에서 사용 됩니다 [HIERSVR](../overview/visual-cpp-samples.md) (검사 합니다 `OnGetClipboardData` 멤버 함수는 **CServerItem** 클래스). 이 예제의 유일한 차이점은 해당 단계 3 HIERSVR 없는 다른 표준 형식을 지원 하기 때문에 구현 되어 있지 않습니다.

### <a name="what-do-you-want-to-know-more-about"></a>자세히 알아볼 항목

- [OLE 데이터 개체 및 데이터 원본 및 균일 한 데이터 전송](../mfc/data-objects-and-data-sources-ole.md)

- [OLE 끌어서 놓기](../mfc/drag-and-drop-ole.md)

- [OLE](../mfc/ole-background.md)

## <a name="see-also"></a>참고자료

[클립보드: OLE 클립보드 메커니즘 사용](../mfc/clipboard-using-the-ole-clipboard-mechanism.md)
