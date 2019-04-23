---
title: COleDataObject 클래스
ms.date: 11/04/2016
f1_keywords:
- COleDataObject
- AFXOLE/COleDataObject
- AFXOLE/COleDataObject::COleDataObject
- AFXOLE/COleDataObject::Attach
- AFXOLE/COleDataObject::AttachClipboard
- AFXOLE/COleDataObject::BeginEnumFormats
- AFXOLE/COleDataObject::Detach
- AFXOLE/COleDataObject::GetData
- AFXOLE/COleDataObject::GetFileData
- AFXOLE/COleDataObject::GetGlobalData
- AFXOLE/COleDataObject::GetNextFormat
- AFXOLE/COleDataObject::IsDataAvailable
- AFXOLE/COleDataObject::Release
helpviewer_keywords:
- COleDataObject [MFC], COleDataObject
- COleDataObject [MFC], Attach
- COleDataObject [MFC], AttachClipboard
- COleDataObject [MFC], BeginEnumFormats
- COleDataObject [MFC], Detach
- COleDataObject [MFC], GetData
- COleDataObject [MFC], GetFileData
- COleDataObject [MFC], GetGlobalData
- COleDataObject [MFC], GetNextFormat
- COleDataObject [MFC], IsDataAvailable
- COleDataObject [MFC], Release
ms.assetid: d1cc84be-2e1c-4bb3-a8a0-565eb08aaa34
ms.openlocfilehash: 24d79c684226d57839161946255781c3bdd5a043
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58779094"
---
# <a name="coledataobject-class"></a>COleDataObject 클래스

끌어 놓기를 통해 클립보드에서 또는 포함된 OLE 항목에서 다양한 형식의 데이터를 검색하기 위해 데이터를 전송하는 데 사용됩니다.

## <a name="syntax"></a>구문

```
class COleDataObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[COleDataObject::COleDataObject](#coledataobject)|`COleDataObject` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[COleDataObject::Attach](#attach)|지정된 된 OLE 데이터 개체를 연결 합니다 `COleDataObject`합니다.|
|[COleDataObject::AttachClipboard](#attachclipboard)|클립보드에 있는 데이터 개체를 연결 합니다.|
|[COleDataObject::BeginEnumFormats](#beginenumformats)|보다 이후 또는 하나에 대 한 준비 `GetNextFormat` 호출 합니다.|
|[COleDataObject::Detach](#detach)|연결 된 분리 `IDataObject` 개체입니다.|
|[COleDataObject::GetData](#getdata)|지정 된 형식으로 연결된 된 OLE 데이터 개체에서 데이터를 복사 합니다.|
|[COleDataObject::GetFileData](#getfiledata)|에 연결된 된 OLE 데이터 개체에서 데이터 복사를 `CFile` 지정된 된 형식에 대 한 포인터입니다.|
|[COleDataObject::GetGlobalData](#getglobaldata)|에 연결된 된 OLE 데이터 개체에서 데이터 복사를 `HGLOBAL` 지정 된 형식에서입니다.|
|[COleDataObject::GetNextFormat](#getnextformat)|사용 가능한 다음 데이터 형식을 반환합니다.|
|[COleDataObject::IsDataAvailable](#isdataavailable)|데이터를 지정 된 형식으로 사용할 수 있는지 확인 합니다.|
|[COleDataObject::Release](#release)|분리 및 연결 된 릴리스 `IDataObject` 개체입니다.|

## <a name="remarks"></a>설명

`COleDataObject` 기본 클래스는 없습니다.

이러한 종류의 데이터 전송에는 원본 및 대상 포함 됩니다. 데이터 원본 개체로 구현 되는 [COleDataSource](../../mfc/reference/coledatasource-class.md) 클래스입니다. 때마다 대상 응용 프로그램을 데이터를 삭제 했거나 개체 클립보드에서 붙여넣기 작업을 수행 하 라는 메시지가 표시 되는 `COleDataObject` 클래스를 만들어야 합니다.

이 클래스를 사용 하면 지정 된 형식의 데이터가 있는지 여부를 확인할 수 있습니다. 또한 사용 가능한 데이터 형식을 열거 하 고 또는 지정된 된 형식으로 사용할 수 있는지 여부를 확인 하 고, 후 원하는 형식으로의 데이터를 검색할 수 있습니다. 개체 검색을 비롯 한 여러 가지 방법으로 수행할 수 있습니다는 [CFile](../../mfc/reference/cfile-class.md)HGLOBAL, 또는를, `STGMEDIUM` 구조입니다.

자세한 내용은 참조는 [STGMEDIUM](/windows/desktop/api/objidl/ns-objidl-tagstgmedium) Windows SDK에는 구조입니다.

응용 프로그램에서 데이터 개체를 사용 하는 방법에 대 한 자세한 내용은 문서 참조 [데이터 개체 및 데이터 소스 (OLE)](../../mfc/data-objects-and-data-sources-ole.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`COleDataObject`

## <a name="requirements"></a>요구 사항

**헤더:** afxole.h

##  <a name="attach"></a>  COleDataObject::Attach

연결 하려면이 함수를 호출 합니다 `COleDataObject` OLE 데이터 개체를 사용 하 여 개체입니다.

```
void Attach(
    LPDATAOBJECT lpDataObject,
    BOOL bAutoRelease = TRUE);
```

### <a name="parameters"></a>매개 변수

*lpDataObject*<br/>
OLE 데이터 개체를 가리킵니다.

*bAutoRelease*<br/>
OLE 데이터 개체 해야 하면 TRUE 면이 해제 합니다 `COleDataObject` 개체가 제거, 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

자세한 내용은 [IDataObject](/windows/desktop/api/objidl/nn-objidl-idataobject) Windows SDK에 있습니다.

##  <a name="attachclipboard"></a>  COleDataObject::AttachClipboard

현재 클립보드에 있는 데이터 개체를 연결 하려면이 함수를 호출 합니다 `COleDataObject` 개체입니다.

```
BOOL AttachClipboard();
```

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

> [!NOTE]
>  이 데이터 개체 해제 될 때까지 클립보드를 잠급니다이 함수를 호출 합니다. 데이터 개체에 대 한 소멸자가을 릴리스 합니다 `COleDataObject`합니다. 자세한 내용은 [OpenClipboard](/windows/desktop/api/winuser/nf-winuser-openclipboard) 하 고 [CloseClipboard](/windows/desktop/api/winuser/nf-winuser-closeclipboard) Win32 설명서의 합니다.

##  <a name="beginenumformats"></a>  COleDataObject::BeginEnumFormats

이 함수에 대 한 후속 호출에 대 한 준비를 호출 `GetNextFormat` 항목에서 데이터 형식의 목록을 검색할 수 있도록 합니다.

```
void BeginEnumFormats();
```

### <a name="remarks"></a>설명

호출한 후 `BeginEnumFormats`,이 데이터 개체에서 지 원하는 첫 번째 형식의 위치에 저장 됩니다. 에 대 한 연속 호출 `GetNextFormat` 데이터 개체에 사용 가능한 형식 목록을 열거 합니다.

지정 된 형식으로 데이터의 가용성을 확인 하려면 사용 하 여 [COleDataObject::IsDataAvailable](#isdataavailable)합니다.

자세한 내용은 [IDataObject::EnumFormatEtc](/windows/desktop/api/objidl/nf-objidl-idataobject-enumformatetc) Windows SDK에 있습니다.

##  <a name="coledataobject"></a>  COleDataObject::COleDataObject

`COleDataObject` 개체를 생성합니다.

```
COleDataObject();
```

### <a name="remarks"></a>설명

에 대 한 호출 [COleDataObject::Attach](#attach) 하거나 [COleDataObject::AttachClipboard](#attachclipboard) 다른 호출 하기 전에 만들어야 `COleDataObject` 함수입니다.

> [!NOTE]
>  에 대 한 포인터를 끌어서 놓기 처리기 매개 변수 중 하나 이므로 `COleDataObject`, 끌어서 놓기 지원 하려면이 생성자를 호출 하지 않아도 됩니다.

##  <a name="detach"></a>  COleDataObject::Detach

분리 하려면이 함수를 호출 합니다 `COleDataObject` 데이터 개체를 해제 하지 않고 연결된 된 OLE 데이터 개체에서 개체입니다.

```
LPDATAOBJECT Detach();
```

### <a name="return-value"></a>반환 값

분리 된 OLE 데이터 개체에 대 한 포인터입니다.

### <a name="remarks"></a>설명

##  <a name="getdata"></a>  COleDataObject::GetData

지정 된 형식의 항목에서 데이터를 검색 하려면이 함수를 호출 합니다.

```
BOOL GetData(
    CLIPFORMAT cfFormat,
    LPSTGMEDIUM lpStgMedium,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>매개 변수

*cfFormat*<br/>
데이터를 반환할의 형식입니다. 이 매개 변수는 미리 정의 된 클립보드 형식 또는 네이티브 Windows에서 반환한 값 중 하나일 수 있습니다 [됩니다](/windows/desktop/api/winuser/nf-winuser-registerclipboardformata) 함수입니다.

*lpStgMedium*<br/>
가리키는 [STGMEDIUM](/windows/desktop/api/objidl/ns-objidl-tagstgmedium) 데이터를 받을 구조입니다.

*lpFormatEtc*<br/>
가리키는 [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) 데이터를 반환할의 형식을 설명 하는 구조입니다. 이 매개 변수 값을 제공 하 여 지정 된 클립보드 형식 이외의 추가 형식 정보를 지정 하려는 경우 *cfFormat*합니다. 다른 필드에 대 한 기본 값이 사용 됩니다 NULL 인 경우는 `FORMATETC` 구조입니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

자세한 내용은 [있음](/windows/desktop/api/objidl/nf-objidl-idataobject-getdata), [STGMEDIUM](/windows/desktop/api/objidl/ns-objidl-tagstgmedium), 및 [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) Windows sdk에서입니다.

자세한 내용은 [됩니다](/windows/desktop/api/winuser/nf-winuser-registerclipboardformata) Windows SDK에 있습니다.

##  <a name="getfiledata"></a>  COleDataObject::GetFileData

만들려는이 함수를 호출을 `CFile` 또는 `CFile`-파생 개체에 지정 된 형식의 데이터를 검색 하는 `CFile` 포인터입니다.

```
CFile* GetFileData(
    CLIPFORMAT cfFormat,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>매개 변수

*cfFormat*<br/>
데이터를 반환할의 형식입니다. 이 매개 변수는 미리 정의 된 클립보드 형식 또는 네이티브 Windows에서 반환한 값 중 하나일 수 있습니다 [됩니다](/windows/desktop/api/winuser/nf-winuser-registerclipboardformata) 함수입니다.

*lpFormatEtc*<br/>
가리키는 [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) 데이터를 반환할의 형식을 설명 하는 구조입니다. 이 매개 변수 값을 제공 하 여 지정 된 클립보드 형식 이외의 추가 형식 정보를 지정 하려는 경우 *cfFormat*합니다. 다른 필드에 대 한 기본 값이 사용 됩니다 NULL 인 경우는 `FORMATETC` 구조입니다.

### <a name="return-value"></a>반환 값

새 포인터 `CFile` 또는 `CFile`-성공 하면 NULL 데이터가 포함 된 개체를 파생 합니다.

### <a name="remarks"></a>설명

데이터에 저장 된 미디어에 따라 반환 값으로 가리키는 실제 형식이 될 수 있습니다 `CFile`하십시오 `CSharedFile`, 또는 `COleStreamFile`합니다.

> [!NOTE]
>  `CFile` 이 함수의 반환 값으로 액세스 하는 개체를 호출자가 소유 합니다. 것은 호출자의 책임 **삭제** 는 `CFile` 개체를 여는 파일을 닫는 중입니다.

자세한 내용은 [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) Windows SDK에 있습니다.

자세한 내용은 [됩니다](/windows/desktop/api/winuser/nf-winuser-registerclipboardformata) Windows SDK에 있습니다.

##  <a name="getglobaldata"></a>  COleDataObject::GetGlobalData

전역 메모리 블록을 할당 하는 데는 HGLOBAL에 지정 된 형식의 데이터를 검색 합니다.이 함수를 호출 합니다.

```
HGLOBAL GetGlobalData(
    CLIPFORMAT cfFormat,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>매개 변수

*cfFormat*<br/>
데이터를 반환할의 형식입니다. 이 매개 변수는 미리 정의 된 클립보드 형식 또는 네이티브 Windows에서 반환한 값 중 하나일 수 있습니다 [됩니다](/windows/desktop/api/winuser/nf-winuser-registerclipboardformata) 함수입니다.

*lpFormatEtc*<br/>
가리키는 [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) 데이터를 반환할의 형식을 설명 하는 구조입니다. 이 매개 변수 값을 제공 하 여 지정 된 클립보드 형식 이외의 추가 형식 정보를 지정 하려는 경우 *cfFormat*합니다. 다른 필드에 대 한 기본 값이 사용 됩니다 NULL 인 경우는 `FORMATETC` 구조입니다.

### <a name="return-value"></a>반환 값

성공할 경우 데이터를 포함 하는 전역 메모리 블록의 핸들 그렇지 않으면 NULL입니다.

### <a name="remarks"></a>설명

자세한 내용은 [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) Windows SDK에 있습니다.

자세한 내용은 [됩니다](/windows/desktop/api/winuser/nf-winuser-registerclipboardformata) Windows SDK에 있습니다.

##  <a name="getnextformat"></a>  COleDataObject::GetNextFormat

항목에서 데이터를 검색할 수 있는 모든 형식을 가져오려고 반복 해 서이 함수를 호출 합니다.

```
BOOL GetNextFormat(LPFORMATETC lpFormatEtc);
```

### <a name="parameters"></a>매개 변수

*lpFormatEtc*<br/>
가리키는 합니다 [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) 함수 호출에서 반환 된 형식 정보를 수신 하는 구조입니다.

### <a name="return-value"></a>반환 값

다른 경우 0이 아닌 형식은 사용할 수 있습니다. 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

호출한 후 [COleDataObject::BeginEnumFormats](#beginenumformats),이 데이터 개체에서 지 원하는 첫 번째 형식의 위치에 저장 됩니다. 에 대 한 연속 호출 `GetNextFormat` 데이터 개체에 사용 가능한 형식 목록을 열거 합니다. 이러한 함수를 사용 하 여 사용 가능한 형식 목록입니다.

지정된 된 형식으로의 가용성을 확인 하려면 호출 [COleDataObject::IsDataAvailable](#isdataavailable)합니다.

자세한 내용은 [IEnumXXXX::Next](https://msdn.microsoft.com/library/ms695273.aspx) Windows SDK에 있습니다.

##  <a name="isdataavailable"></a>  COleDataObject::IsDataAvailable

OLE 항목에서 데이터를 검색할 수 있는 특정 형식 인지 확인 하려면이 함수를 호출 합니다.

```
BOOL IsDataAvailable(
    CLIPFORMAT cfFormat,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>매개 변수

*cfFormat*<br/>
가리키는 클립보드 데이터 형식의 구조에 사용할 *lpFormatEtc*합니다. 이 매개 변수는 미리 정의 된 클립보드 형식 또는 네이티브 Windows에서 반환한 값 중 하나일 수 있습니다 [됩니다](/windows/desktop/api/winuser/nf-winuser-registerclipboardformata) 함수입니다.

*lpFormatEtc*<br/>
가리키는 [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) 원하는 형식을 설명 하는 구조입니다. 이 매개 변수 값을 제공 하 여 지정 된 클립보드 형식 이외의 추가 형식 정보를 지정 하려는 경우에 *cfFormat*합니다. 다른 필드에 대 한 기본 값이 사용 됩니다 NULL 인 경우는 `FORMATETC` 구조입니다.

### <a name="return-value"></a>반환 값

0이 아닌 데이터는 지정된 된 형식으로 사용할 수 있습니다 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 함수는 호출 하기 전에 유용 `GetData`하십시오 `GetFileData`, 또는 `GetGlobalData`합니다.

자세한 내용은 [IDataObject::QueryGetData](/windows/desktop/api/objidl/nf-objidl-idataobject-querygetdata) 하 고 [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) Windows SDK의 합니다.

자세한 내용은 [됩니다](/windows/desktop/api/winuser/nf-winuser-registerclipboardformata) Windows SDK에 있습니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CRichEditView::QueryAcceptData](../../mfc/reference/cricheditview-class.md#queryacceptdata)합니다.

##  <a name="release"></a>  COleDataObject::Release

소유권을 해제 하려면이 함수를 호출 합니다 [IDataObject](/windows/desktop/api/objidl/nn-objidl-idataobject) 이전에 연결 된 개체는 `COleDataObject` 개체입니다.

```
void Release();
```

### <a name="remarks"></a>설명

합니다 `IDataObject` 연관 된 합니다 `COleDataObject` 를 호출 하 여 `Attach` 또는 `AttachClipboard` 명시적으로 또는 프레임 워크에서. 경우는 *bAutoRelease* 의 매개 변수 `Attach` 은 FALSE를 `IDataObject` 개체 해제 되지 것입니다. 이 경우 호출자가 해제 하는 일을 담당 합니다 `IDataObject` 를 호출 하 여 [iunknown:: Release](/windows/desktop/api/unknwn/nf-unknwn-iunknown-release)합니다.

## <a name="see-also"></a>참고자료

[MFC Sample HIERSVR](../../overview/visual-cpp-samples.md)<br/>
[MFC 샘플 OCLIENT](../../overview/visual-cpp-samples.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[COleDataSource 클래스](../../mfc/reference/coledatasource-class.md)<br/>
[COleClientItem 클래스](../../mfc/reference/coleclientitem-class.md)<br/>
[COleServerItem 클래스](../../mfc/reference/coleserveritem-class.md)
