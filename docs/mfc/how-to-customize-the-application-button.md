---
title: '방법: 응용 프로그램 단추 사용자 지정'
ms.date: 09/07/2019
helpviewer_keywords:
- application button [MFC], customizing
ms.assetid: ebb11180-ab20-43df-a234-801feca9eb38
ms.openlocfilehash: 3a1d1625e80e6c6f4440864629a5123bed5744c7
ms.sourcegitcommit: 3caf5261b3ea80d9cf14038c116ba981d655cd13
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/11/2019
ms.locfileid: "70907799"
---
# <a name="how-to-customize-the-application-button"></a>방법: 응용 프로그램 단추 사용자 지정

응용 프로그램 단추를 클릭 하면 명령 메뉴가 표시 됩니다. 일반적으로 메뉴에는 **열기**, **저장**, **인쇄**및 **종료**와 같은 파일 관련 명령이 포함 되어 있습니다.

![MFC 리본 응용 프로그램 단추](../mfc/media/application_button.png "MFC 리본 응용 프로그램 단추")

응용 프로그램 단추를 사용자 지정 하려면 **속성** 창 ( **리소스 뷰**)에서 열고 해당 속성을 수정한 다음 리본 컨트롤을 미리 봅니다.

### <a name="to-open-the-application-button-in-the-properties-window"></a>속성 창에서 응용 프로그램 단추를 열려면

1. Visual Studio의 **보기** 메뉴에서 **리소스 뷰**를 클릭 합니다.

1. **리소스 뷰**에서 리본 리소스를 두 번 클릭 하 여 디자인 화면에 표시 합니다.

1. 디자인 화면에서 응용 프로그램 단추 메뉴를 마우스 오른쪽 단추로 클릭 한 다음 **속성**을 클릭 합니다.

## <a name="application-button-properties"></a>응용 프로그램 단추 속성

다음 표에서는 응용 프로그램 단추의 속성을 정의 합니다.

|속성|정의|
|--------------|----------------|
|**단추**|응용 프로그램 메뉴의 오른쪽 아래 모퉁이에 표시 되는 최대 3 개의 단추 컬렉션을 포함 합니다.|
|**캡션**|컨트롤의 텍스트를 지정 합니다. 다른 리본 요소와 달리 응용 프로그램 단추에는 캡션 텍스트가 표시 되지 않습니다. 대신 접근성에 텍스트가 사용 됩니다.|
|**HDPI 이미지**|HDPI (high dpi) 응용 프로그램 단추 아이콘의 식별자를 지정 합니다. 응용 프로그램이 높은 DPI 모니터에서 실행 될 때 **이미지**대신 **hdpi 이미지가** 사용 됩니다.|
|**HDPI 초대형 이미지**|높은 DPI 큰 이미지의 식별자를 지정 합니다. 응용 프로그램이 높은 DPI 모니터에서 실행 되는 경우 **큰 이미지**대신 **hdpi 큰 이미지가** 사용 됩니다.|
|**HDPI 작은 이미지**|높은 DPI 작은 이미지의 식별자를 지정 합니다. 응용 프로그램이 높은 DPI 모니터에서 실행 될 때 **작은 이미지**대신 **hdpi 소형 이미지가** 사용 됩니다.|
|**ID**|컨트롤의 식별자를 지정 합니다.|
|**Image**|응용 프로그램 단추 아이콘의 식별자를 지정 합니다. 아이콘은 알파 투명도를 포함 하는 32 비트 26x26 비트맵입니다. 응용 프로그램 단추를 클릭 하거나 가리킬 때 아이콘의 투명 부분이 강조 표시 됩니다.|
|**키**|키 팁 탐색이 설정 된 경우 표시 되는 문자열을 지정 합니다. ALT 키를 누르면 키 팁 탐색이 활성화 됩니다.|
|**이미지 크게**|일련의 32x32 아이콘이 포함 된 이미지의 식별자를 지정 합니다. 아이콘은 기본 항목 컬렉션의 단추에 사용 됩니다.|
|**기본 항목**|응용 프로그램 메뉴에 나타나는 메뉴 항목의 컬렉션을 포함 합니다.|
|**MRU 캡션**|최근 목록 패널에 표시 되는 텍스트를 지정 합니다.|
|**작은 이미지**|일련의 16x16 아이콘이 포함 된 이미지의 식별자를 지정 합니다. 아이콘은 Buttons 컬렉션의 단추에 사용 됩니다.|
|**사용**|최근 목록 패널을 사용 하거나 사용 하지 않도록 설정 합니다. 최근 목록 패널은 응용 프로그램 메뉴에 표시 됩니다.|
|**Width**|최근 목록 패널의 너비 (픽셀)를 지정 합니다.|

응용 프로그램 메뉴가 디자인 화면에 표시 되지 않습니다. 이를 보려면 리본을 미리 보거나 응용 프로그램을 실행 해야 합니다.

#### <a name="to-preview-the-ribbon-control"></a>리본 컨트롤을 미리 보려면

- **리본 편집기 도구 모음**에서 **테스트 리본**을 클릭 합니다.

## <a name="see-also"></a>참고자료

[리본 디자이너(MFC)](../mfc/ribbon-designer-mfc.md)
