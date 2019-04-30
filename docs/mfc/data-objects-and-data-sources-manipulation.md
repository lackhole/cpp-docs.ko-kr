---
title: '데이터 개체 및 데이터 소스: 조작'
ms.date: 11/04/2016
helpviewer_keywords:
- data objects [MFC], manipulating
- data sources [MFC], data operations
- data sources [MFC], inserting data
- Clipboard [MFC], determining available formats
- OLE [MFC], data objects
- Clipboard [MFC], passing format information
- data sources [MFC], determining available formats
- delayed rendering [MFC]
- OLE [MFC], data sources
ms.assetid: f7f27e77-bb5d-4131-b819-d71bf929ebaf
ms.openlocfilehash: 81dfe911866c4d1ba1720ee2c9854076c499f0a3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62241551"
---
# <a name="data-objects-and-data-sources-manipulation"></a>데이터 개체 및 데이터 소스: 조작

데이터 개체 또는 데이터 원본을 만든 후에, 다양 한 데이터를 삽입 하 고 데이터에 형식을 열거 하는 데이터를 제거 하는 등의 일반적인 작업을 수행할 수 있습니다. 이 문서에는 가장 일반적인 작업을 완료 하는 데 필요한 기술을 설명 합니다. 다루는 주제는 다음과 같습니다.

- [데이터 원본에 데이터 삽입](#_core_inserting_data_into_a_data_source)

- [데이터 개체에 사용할 수 있는 형식을 결정합니다.](#_core_determining_the_formats_available_in_a_data_object)

- [데이터 개체에서 데이터 검색](#_core_retrieving_data_from_a_data_object)

##  <a name="_core_inserting_data_into_a_data_source"></a> 데이터 원본에 데이터 삽입

제공 되는 중간에 주문형으로 또는 데이터를 즉시 제공 여부에 종속 데이터 원본에 데이터를 삽입 하는 방법입니다. 가능한 값은 다음과 같습니다.

### <a name="supplying-data-immediately-immediate-rendering"></a>즉시 데이터 (즉시 렌더링)를 제공합니다.

- 호출 `COleDataSource::CacheGlobalData` 반복적으로 데이터를 제공 되는 모든 클립보드 형식에 대 한 합니다. 사용할 클립보드 형식을 전달 데이터를 포함 하는 메모리에 대 한 핸들 및 선택적으로 **FORMATETC** 데이터를 설명 하는 구조입니다.

     또는

- 직접 작업 하려는 경우 **STGMEDIUM** 호출 구조 `COleDataSource::CacheData` 대신 `COleDataSource::CacheGlobalData` 위의 옵션입니다.

### <a name="supplying-data-on-demand-delayed-rendering"></a>(지연 된 렌더링) 요청 시 데이터를 제공 합니다.

고급 항목입니다.

- 호출 `COleDataSource::DelayRenderData` 반복적으로 데이터를 제공 되는 모든 클립보드 형식에 대 한 합니다. 사용 되는 클립보드 형식을 전달 및 필요에 따라를 **FORMATETC** 데이터를 설명 하는 구조입니다. 데이터 요청 될 때 호출 됩니다 `COleDataSource::OnRenderData`를 재정의 해야 합니다.

     또는

- 사용 하는 경우는 `CFile` 데이터를 제공 하는 개체 호출 `COleDataSource::DelayRenderFileData` 대신 `COleDataSource::DelayRenderData` 이전 옵션에서. 데이터 요청 될 때 호출 됩니다 `COleDataSource::OnRenderFileData`를 재정의 해야 합니다.

##  <a name="_core_determining_the_formats_available_in_a_data_object"></a> 데이터 개체에 사용할 수 있는 형식을 결정합니다.

응용 프로그램 데이터를 붙여 사용자를 허용 하기 전에 처리할 수 있는 클립보드에 형식이 있는지 알고 있어야 합니다. 이렇게 하려면 응용 프로그램이 다음을 수행 해야 합니다.

1. 만들기는 `COleDataObject` 개체와 **FORMATETC** 구조입니다.

1. 데이터 개체의 호출 `AttachClipboard` 멤버 함수를 클립보드에 데이터를 사용 하 여 데이터 개체를 연결 합니다.

1. 다음 작업 중 하나를 수행합니다.

   - 데이터 개체의 호출 `IsDataAvailable` 하나만 가지 또는 두 형식을 지정 하는 경우 멤버 함수에 필요 합니다. 시간을 절약할 수 있는 클립보드에 데이터 응용 프로그램 보다 훨씬 더 많은 형식에서 지 원하는 경우이 됩니다.

         -or-

   - 데이터 개체의 호출 `BeginEnumFormats` 멤버 함수를 클립보드에 사용할 수 있는 형식을 열거를 시작 합니다. 그런 다음 호출 `GetNextFormat` 클립보드 반환 될 때까지 응용 프로그램이 지 원하는 형식 또는 자세한 형식이 없습니다.

사용 중인 경우 **ON_UPDATE_COMMAND_UI**, 이제는 붙여넣기 및 붙여넣기 항목 편집 메뉴에서 설정할 수 있습니다. 이 작업을 수행 하려면 하나를 호출 `CMenu::EnableMenuItem` 또는 `CCmdUI::Enable`합니다. 어떤 컨테이너에 대 한 자세한 내용은 응용 프로그램 메뉴 항목을 사용 하 여 수행할를 참조 하십시오 [메뉴 및 리소스: 컨테이너 추가](../mfc/menus-and-resources-container-additions.md)합니다.

##  <a name="_core_retrieving_data_from_a_data_object"></a> 데이터 개체에서 데이터 검색

데이터 형식에 했으면에 데이터 개체에서 데이터를 검색 합니다. 이렇게 하려면 사용자가 데이터를 넣을 위치를 결정 하 고 응용 프로그램에서 적절 한 함수를 호출 합니다. 데이터는 다음 미디어 중 하나에서 사용할 수 있습니다.

|중간|호출할 함수|
|------------|----------------------|
|전역 메모리 (`HGLOBAL`)|`COleDataObject::GetGlobalData`|
|파일 (`CFile`)|`COleDataObject::GetFileData`|
|**STGMEDIUM** 구조 (`IStorage`)|`COleDataObject::GetData`|

일반적으로 미디어 함께 클립보드 형식으로 지정 됩니다. 예를 들어를 **CF_EMBEDDEDSTRUCT** 개체는 항상를 `IStorage` 필요한 중간 규모는 **STGMEDIUM** 구조입니다. 따라서 사용 `GetData` 받아들일 수 있는 이러한 함수 중 하나만 있기 때문에 **STGMEDIUM** 구조입니다.

클립보드 형식에 있는 경우에는 `IStream` 또는 `HGLOBAL` 중간, 프레임 워크를 제공할 수 있습니다는 `CFile` 데이터를 참조 하는 포인터입니다. 응용 프로그램에서 데이터를 가져올 거의 동일한 방식으로 파일에서 데이터를 가져올 때 읽을 파일을 사용할 수 있습니다. 기본적으로,이 클라이언트 쪽 인터페이스는 `OnRenderData` 및 `OnRenderFileData` 데이터 소스의 루틴입니다.

사용자는 동일한 형식의 다른 모든 데이터에 대 한 문서에 데이터 삽입 마찬가지로 이제 수 있습니다.

### <a name="what-do-you-want-to-know-more-about"></a>자세히 알아볼 항목

- [끌어서 놓기](../mfc/drag-and-drop-ole.md)

- [클립보드](../mfc/clipboard.md)

## <a name="see-also"></a>참고자료

[데이터 개체 및 데이터 소스(OLE)](../mfc/data-objects-and-data-sources-ole.md)<br/>
[COleDataObject 클래스](../mfc/reference/coledataobject-class.md)<br/>
[COleDataSource 클래스](../mfc/reference/coledatasource-class.md)
