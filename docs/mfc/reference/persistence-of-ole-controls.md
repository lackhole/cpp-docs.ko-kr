---
title: OLE 컨트롤의 지속성
ms.date: 11/04/2016
helpviewer_keywords:
- OLE controls [MFC], persistence
- persistence, OLE controls
ms.assetid: 64f8dc80-f110-41af-b3ea-14948f6bfdf7
ms.openlocfilehash: 639a5a98da03307e3edf22deb6d32956c3f73374
ms.sourcegitcommit: 934cb53fa4cb59fea611bfeb9db110d8d6f7d165
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2019
ms.locfileid: "65611774"
---
# <a name="persistence-of-ole-controls"></a>OLE 컨트롤의 지속성

OLE 컨트롤의 한 가지 기능은 속성 지 속성 (또는 serialization)는 OLE 컨트롤을 읽거나을 파일 또는 스트림에서 속성 값을 쓸 수 있습니다. 컨테이너 응용 프로그램을 serialization을 사용 응용 프로그램에 컨트롤을 삭제 한 후에 컨트롤의 속성 값을 저장할 수 있습니다. OLE 컨트롤의 속성 값을 파일에서 읽을 수 또는 나중에 스트림이 때 컨트롤의 새 인스턴스를 생성 합니다.

### <a name="persistence-of-ole-controls"></a>OLE 컨트롤의 지속성

|||
|-|-|
|[PX_Blob](#px_blob)|Binary large object (BLOB) 데이터를 저장 하는 컨트롤 속성을 교환 합니다.|
|[PX_Bool](#px_bool)|컨트롤 속성 형식의 교환 **BOOL**합니다.|
|[PX_Color](#px_color)|컨트롤의 색 속성을 교환합니다.|
|[PX_Currency](#px_currency)|컨트롤 속성 형식의 교환 **CY**합니다.|
|[PX_DataPath](#px_datapath)|교환 컨트롤 속성 형식의 `CDataPathProperty`합니다.|
|[PX_Double](#px_double)|컨트롤 속성 형식의 교환 **이중**합니다.|
|[PX_Font](#px_font)|컨트롤의 글꼴 속성을 교환합니다.|
|[PX_Float](#px_float)|컨트롤 속성 형식의 교환 **float**합니다.|
|[PX_IUnknown](#px_iunknown)|정의 되지 않은 형식의 컨트롤 속성을 교환합니다.|
|[PX_Long](#px_long)|컨트롤 속성 형식의 교환 **긴**합니다.|
|[PX_Picture](#px_picture)|컨트롤의 그림 속성을 교환합니다.|
|[PX_Short](#px_short)|컨트롤 속성 형식의 교환 **짧은**합니다.|
|[PX_ULong](#px_ulong)|컨트롤 속성 형식의 교환 **ULONG**합니다.|
|[PX_UShort](#px_ushort)|컨트롤 속성 형식의 교환 **USHORT**합니다.|
|[PXstring](#px_string)|문자 문자열 컨트롤 속성을 교환합니다.|
|[PX_VBXFontConvert](#px_vbxfontconvert)|OLE 컨트롤 글꼴 속성을로 VBX 컨트롤의 글꼴 관련 속성을 교환합니다.|

또한는 `AfxOleTypeMatchGuid` 전역 함수는 제공된 된 GUID는 TYPEDESC 사이의 일치 항목을 테스트 하려면 제공 됩니다.

##  <a name="px_blob"></a>  PX_Blob

사용자 컨트롤 내에서이 함수를 호출 `DoPropExchange` 멤버 함수를 serialize 또는 binary large object (BLOB) 데이터를 저장 하는 속성을 초기화 합니다.

```
BOOL PX_Blob(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    HGLOBAL& hBlob,
    HGLOBAL hBlobDefault = NULL);
```

### <a name="parameters"></a>매개 변수

*pPX*<br/>
에 대 한 포인터를 [CPropExchange](../../mfc/reference/cpropexchange-class.md) 개체 (일반적으로 매개 변수로 전달 `DoPropExchange`).

*pszPropName*<br/>
교환 되는 속성의 이름입니다.

*hBlob*<br/>
속성이 저장 된 변수에 대 한 참조 (일반적으로 클래스의 멤버 변수).

*hBlobDefault*<br/>
속성에 대 한 기본 값입니다.

### <a name="return-value"></a>반환 값

Exchange에 성공 하면 0이 아닌 값 실패 한 경우 0입니다.

### <a name="remarks"></a>설명

속성의 값은 읽거나 참조 변수를 쓸 *hBlob*를 적절 하 게 합니다. 처음 호출 하기 전에이 변수를 NULL로 초기화 되어야 `PX_Blob` 처음으로 (일반적으로 이렇게 하려면 컨트롤의 생성자에서). 하는 경우 *hBlobDefault* 지정, 속성의 기본값으로 사용 됩니다. 이 값은 컨트롤의 초기화 또는 serialization 프로세스 어떤 이유로 실패 하는 경우 사용 됩니다.

핸들 *hBlob* 하 고 *hBlobDefault* 다음을 포함 하는 메모리 블록을 참조 하세요.

- 이진 데이터의 길이 (바이트)를 포함 하는 DWORD 올 즉시

- 블록 실제 이진 데이터를 포함 하는 메모리입니다.

사실은 `PX_Blob` 는 Windows를 사용 하 여 메모리를 할당 [GlobalAlloc](/windows/desktop/api/winbase/nf-winbase-globalalloc) API, BLOB 형식의 속성을 로드 하는 경우. 이 메모리를 해제 책임이 있습니다. 컨트롤의 소멸자를 호출 해야 하므로 [GlobalFree](/windows/desktop/api/winbase/nf-winbase-globalfree) 무료에 대 한 핸들 BLOB 유형의 속성에 컨트롤에 할당 된 메모리를 설정 합니다.

##  <a name="px_bool"></a>  PX_Bool

사용자 컨트롤 내에서이 함수를 호출 `DoPropExchange` 멤버 함수를 serialize 또는 BOOL 형식의 속성을 초기화 합니다.

```
BOOL PX_Bool(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    BOOL& bValue);

BOOL PX_Bool(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    BOOL& bValue,
    BOOL bDefault);
```

### <a name="parameters"></a>매개 변수

*pPX*<br/>
에 대 한 포인터를 [CPropExchange](../../mfc/reference/cpropexchange-class.md) 개체 (일반적으로 매개 변수로 전달 `DoPropExchange`).

*pszPropName*<br/>
교환 되는 속성의 이름입니다.

*bValue*<br/>
속성이 저장 된 변수에 대 한 참조 (일반적으로 클래스의 멤버 변수).

*bDefault*<br/>
속성에 대 한 기본 값입니다.

### <a name="return-value"></a>반환 값

Exchange에 성공 하면 0이 아닌 값 실패 한 경우 0입니다.

### <a name="remarks"></a>설명

속성의 값은 읽거나 참조 변수를 쓸 *bValue*를 적절 하 게 합니다. 하는 경우 *슬라이더가* 지정, 속성의 기본값으로 사용 됩니다. 이 값은 컨트롤의 serialization 프로세스 어떤 이유로 실패 하는 경우 사용 됩니다.

##  <a name="px_color"></a>  PX_Color

사용자 컨트롤 내에서이 함수를 호출 `DoPropExchange` 멤버 함수를 serialize 또는 OLE_COLOR 형식의 속성을 초기화 합니다.

```
BOOL PX_Color(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    OLE_COLOR& clrValue);

BOOL PX_Color(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    OLE_COLOR& clrValue,
    OLE_COLOR clrDefault);
```

### <a name="parameters"></a>매개 변수

*pPX*<br/>
에 대 한 포인터를 [CPropExchange](../../mfc/reference/cpropexchange-class.md) 개체 (일반적으로 매개 변수로 전달 `DoPropExchange`).

*pszPropName*<br/>
교환 되는 속성의 이름입니다.

*clrValue*<br/>
속성이 저장 된 변수에 대 한 참조 (일반적으로 클래스의 멤버 변수).

*clrDefault*<br/>
컨트롤 개발자가 정의 된 속성에 대 한 기본 값입니다.

### <a name="return-value"></a>반환 값

Exchange에 성공 하면 0이 아닌 값 실패 한 경우 0입니다.

### <a name="remarks"></a>설명

속성의 값은 읽거나 참조 변수를 쓸 *clrValue*를 적절 하 게 합니다. 하는 경우 *clrDefault* 지정, 속성의 기본값으로 사용 됩니다. 이 값은 컨트롤의 serialization 프로세스 어떤 이유로 실패 하는 경우 사용 됩니다.

##  <a name="px_currency"></a>  PX_Currency

사용자 컨트롤 내에서이 함수를 호출 `DoPropExchange` serialize 하거나 형식의 속성을 초기화 하려면 멤버 함수 **통화**합니다.

```
BOOL PX_Currency(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    CY& cyValue);

BOOL PX_Currency(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    CY& cyValue,
    CY cyDefault);
```

### <a name="parameters"></a>매개 변수

*pPX*<br/>
에 대 한 포인터를 [CPropExchange](../../mfc/reference/cpropexchange-class.md) 개체 (일반적으로 매개 변수로 전달 `DoPropExchange`).

*pszPropName*<br/>
교환 되는 속성의 이름입니다.

*cyValue*<br/>
속성이 저장 된 변수에 대 한 참조 (일반적으로 클래스의 멤버 변수).

*cyDefault*<br/>
속성에 대 한 기본 값입니다.

### <a name="return-value"></a>반환 값

Exchange에 성공 하면 0이 아닌 값 실패 한 경우 0입니다.

### <a name="remarks"></a>설명

속성의 값은 읽거나 참조 변수를 쓸 *cyValue*를 적절 하 게 합니다. 하는 경우 *cyDefault* 지정, 속성의 기본값으로 사용 됩니다. 이 값은 컨트롤의 serialization 프로세스 어떤 이유로 실패 하는 경우 사용 됩니다.

##  <a name="px_datapath"></a>  PX_DataPath

사용자 컨트롤 내에서이 함수를 호출 `DoPropExchange` serialize 하거나 형식의 데이터 경로 속성을 초기화 하려면 멤버 함수 [CDataPathProperty](../../mfc/reference/cdatapathproperty-class.md)합니다.

```
BOOL PX_DataPath(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    CDataPathProperty& dataPathProperty);

BOOL PX_DataPath(
    CPropExchange* pPX,
    CDataPathProperty& dataPathProperty);
```

### <a name="parameters"></a>매개 변수

*pPX*<br/>
에 대 한 포인터를 [CPropExchange](../../mfc/reference/cpropexchange-class.md) 개체 (일반적으로 매개 변수로 전달 `DoPropExchange`).

*pszPropName*<br/>
교환 되는 속성의 이름입니다.

*dataPathProperty*<br/>
속성이 저장 된 변수에 대 한 참조 (일반적으로 클래스의 멤버 변수).

### <a name="return-value"></a>반환 값

Exchange에 성공 하면 0이 아닌 값 실패 한 경우 0입니다.

### <a name="remarks"></a>설명

데이터 경로 속성 비동기 컨트롤 속성을 구현합니다. 속성의 값은 읽거나 참조 변수를 쓸 *dataPathProperty*를 적절 하 게 합니다.

##  <a name="px_double"></a>  PX_Double

사용자 컨트롤 내에서이 함수를 호출 `DoPropExchange` serialize 하거나 형식의 속성을 초기화 하려면 멤버 함수 **double**합니다.

```
BOOL PX_Double(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    double& doubleValue);

BOOL PX_Double(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    double& doubleValue,
    double doubleDefault);
```

### <a name="parameters"></a>매개 변수

*pPX*<br/>
에 대 한 포인터를 [CPropExchange](../../mfc/reference/cpropexchange-class.md) 개체 (일반적으로 매개 변수로 전달 `DoPropExchange`).

*pszPropName*<br/>
교환 되는 속성의 이름입니다.

*doubleValue*<br/>
속성이 저장 된 변수에 대 한 참조 (일반적으로 클래스의 멤버 변수).

*doubleDefault*<br/>
속성에 대 한 기본 값입니다.

### <a name="return-value"></a>반환 값

Exchange에 성공 하면 0이 아닌 값 실패 한 경우 0입니다.

### <a name="remarks"></a>설명

속성의 값을 읽거나 참조 변수를 쓸 *doubleValue*를 적절 하 게 합니다. 하는 경우 *doubleDefault* 지정, 속성의 기본값으로 사용 됩니다. 이 값은 컨트롤의 serialization 프로세스 어떤 이유로 실패 하는 경우 사용 됩니다.

##  <a name="px_font"></a>  PX_Font

사용자 컨트롤 내에서이 함수를 호출 `DoPropExchange` 멤버 함수를 serialize 또는 글꼴의 속성을 초기화 합니다.

```
BOOL PX_Font(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    CFontHolder& font,
    const FONTDESC FAR* pFontDesc = NULL,
    LPFONTDISP pFontDispAmbient = NULL);
```

### <a name="parameters"></a>매개 변수

*pPX*<br/>
에 대 한 포인터를 [CPropExchange](../../mfc/reference/cpropexchange-class.md) 개체 (일반적으로 매개 변수로 전달 `DoPropExchange`).

*pszPropName*<br/>
교환 되는 속성의 이름입니다.

*font*<br/>
에 대 한 참조를 `CFontHolder` 글꼴 속성을 포함 하는 개체입니다.

*pFontDesc*<br/>
에 대 한 포인터를 `FONTDESC` 에서는 글꼴 속성의 기본 상태로 초기화 하는 데 값이 포함 된 구조 위치 *pFontDispAmbient* NULL입니다.

*pFontDispAmbient*<br/>
에 대 한 포인터를 `IFontDisp` font 속성의 기본 상태를 초기화 하는 데 글꼴의 인터페이스입니다.

### <a name="return-value"></a>반환 값

Exchange에 성공 하면 0이 아닌 값 실패 한 경우 0입니다.

### <a name="remarks"></a>설명

속성의 값을 읽거나 쓸 `font`, `CFontHolder` 적절 한 경우를 참조 합니다. 경우 *pFontDesc* 하 고 *pFontDispAmbient* 필요한 경우 속성의 기본값을 초기화 하는 데 사용할 지정 됩니다. 이러한 값은 컨트롤의 serialization 프로세스 어떤 이유로 실패 하는 경우 사용 됩니다. NULL을 전달 하는 일반적으로 *pFontDesc* 반환한 앰비언트 값 `COleControl::AmbientFont` 에 대 한 *pFontDispAmbient*합니다. 글꼴 개체가 반환한 참고 `COleControl::AmbientFont` 를 호출 하 여 해제 되어야 합니다는 `IFontDisp::Release` 멤버 함수입니다.

##  <a name="px_float"></a>  PX_Float

사용자 컨트롤 내에서이 함수를 호출 `DoPropExchange` serialize 하거나 형식의 속성을 초기화 하려면 멤버 함수 **float**합니다.

```
BOOL PX_Float(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    float& floatValue);

BOOL PX_Float(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    float& floatValue,
    float floatDefault);
```

### <a name="parameters"></a>매개 변수

*pPX*<br/>
에 대 한 포인터를 [CPropExchange](../../mfc/reference/cpropexchange-class.md) 개체 (일반적으로 매개 변수로 전달 `DoPropExchange`).

*pszPropName*<br/>
교환 되는 속성의 이름입니다.

*floatValue*<br/>
속성이 저장 된 변수에 대 한 참조 (일반적으로 클래스의 멤버 변수).

*floatDefault*<br/>
속성에 대 한 기본 값입니다.

### <a name="return-value"></a>반환 값

Exchange에 성공 하면 0이 아닌 값 실패 한 경우 0입니다.

### <a name="remarks"></a>설명

속성의 값을 읽거나 참조 변수를 쓸 *floatValue*를 적절 하 게 합니다. 하는 경우 *floatDefault* 지정, 속성의 기본값으로 사용 됩니다. 이 값은 컨트롤의 serialization 프로세스 어떤 이유로 실패 하는 경우 사용 됩니다.

##  <a name="px_iunknown"></a>  PX_IUnknown

사용자 컨트롤 내에서이 함수를 호출 `DoPropExchange` 멤버 함수를 serialize 하거나 개체 함으로써 표시 되는 속성을 초기화 하는 `IUnknown`-파생 인터페이스입니다.

```
BOOL PX_IUnknown(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    LPUNKNOWN& pUnk,
    REFIID iid,
    LPUNKNOWN pUnkDefault = NULL);
```

### <a name="parameters"></a>매개 변수

*pPX*<br/>
에 대 한 포인터를 [CPropExchange](../../mfc/reference/cpropexchange-class.md) 개체 (일반적으로 매개 변수로 전달 `DoPropExchange`).

*pszPropName*<br/>
교환 되는 속성의 이름입니다.

*pUnk*<br/>
속성의 값을 나타내는 개체의 인터페이스를 포함 하는 변수에 대 한 참조입니다.

*iid*<br/>
속성 개체의 인터페이스를 나타내는 인터페이스 ID 컨트롤에 의해 사용 됩니다.

*pUnkDefault*<br/>
속성에 대 한 기본 값입니다.

### <a name="return-value"></a>반환 값

Exchange에 성공 하면 0이 아닌 값 실패 한 경우 0입니다.

### <a name="remarks"></a>설명

속성의 값을 읽거나 참조 변수를 쓸 *pUnk*를 적절 하 게 합니다. 하는 경우 *pUnkDefault* 지정, 속성의 기본값으로 사용 됩니다. 이 값은 컨트롤의 serialization 프로세스 어떤 이유로 실패 하는 경우 사용 됩니다.

##  <a name="px_long"></a>  PX_Long

사용자 컨트롤 내에서이 함수를 호출 `DoPropExchange` serialize 하거나 형식의 속성을 초기화 하려면 멤버 함수 **긴**합니다.

```
BOOL PX_Long(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    long& lValue);

BOOL PX_Long(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    long& lValue,
    long lDefault);
```

### <a name="parameters"></a>매개 변수

*pPX*<br/>
에 대 한 포인터를 [CPropExchange](../../mfc/reference/cpropexchange-class.md) 개체 (일반적으로 매개 변수로 전달 `DoPropExchange`).

*pszPropName*<br/>
교환 되는 속성의 이름입니다.

*lValue*<br/>
속성이 저장 된 변수에 대 한 참조 (일반적으로 클래스의 멤버 변수).

*lDefault*<br/>
속성에 대 한 기본 값입니다.

### <a name="return-value"></a>반환 값

Exchange에 성공 하면 0이 아닌 값 실패 한 경우 0입니다.

### <a name="remarks"></a>설명

속성의 값을 읽거나 참조 변수를 쓸 *lValue*를 적절 하 게 합니다. 하는 경우 *lDefault* 지정, 속성의 기본값으로 사용 됩니다. 이 값은 컨트롤의 serialization 프로세스 어떤 이유로 실패 하는 경우 사용 됩니다.

##  <a name="px_picture"></a>  PX_Picture

사용자 컨트롤 내에서이 함수를 호출 `DoPropExchange` 멤버 함수를 serialize 또는 컨트롤의 그림 속성을 초기화 합니다.

```
BOOL PX_Picture(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    CPictureHolder& pict);

BOOL PX_Picture(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    CPictureHolder& pict,
    CPictureHolder& pictDefault);
```

### <a name="parameters"></a>매개 변수

*pPX*<br/>
에 대 한 포인터를 [CPropExchange](../../mfc/reference/cpropexchange-class.md) 개체 (일반적으로 매개 변수로 전달 `DoPropExchange`).

*pszPropName*<br/>
교환 되는 속성의 이름입니다.

*pict*<br/>
에 대 한 참조를 [CPictureHolder](../../mfc/reference/cpictureholder-class.md) 속성이 저장 된 개체 (일반적으로 클래스의 멤버 변수).

*pictDefault*<br/>
속성에 대 한 기본 값입니다.

### <a name="return-value"></a>반환 값

Exchange에 성공 하면 0이 아닌 값 실패 한 경우 0입니다.

### <a name="remarks"></a>설명

속성의 값을 읽거나 참조 변수를 쓸 *pict*를 적절 하 게 합니다. 하는 경우 *pictDefault* 지정, 속성의 기본값으로 사용 됩니다. 이 값은 컨트롤의 serialization 프로세스 어떤 이유로 실패 하는 경우 사용 됩니다.

##  <a name="px_short"></a>  PX_Short

사용자 컨트롤 내에서이 함수를 호출 `DoPropExchange` serialize 하거나 형식의 속성을 초기화 하려면 멤버 함수 **짧은**합니다.

```
BOOL PX_Short(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    short& sValue);

BOOL PX_Short(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    short& sValue,
    short sDefault);
```

### <a name="parameters"></a>매개 변수

*pPX*<br/>
에 대 한 포인터를 [CPropExchange](../../mfc/reference/cpropexchange-class.md) 개체 (일반적으로 매개 변수로 전달 `DoPropExchange`).

*pszPropName*<br/>
교환 되는 속성의 이름입니다.

*sValue*<br/>
속성이 저장 된 변수에 대 한 참조 (일반적으로 클래스의 멤버 변수).

*sDefault*<br/>
속성에 대 한 기본 값입니다.

### <a name="return-value"></a>반환 값

Exchange에 성공 하면 0이 아닌 값 실패 한 경우 0입니다.

### <a name="remarks"></a>설명

속성의 값을 읽거나 참조 변수를 쓸 *sValue*를 적절 하 게 합니다. 하는 경우 *sDefault* 지정, 속성의 기본값으로 사용 됩니다. 이 값은 컨트롤의 serialization 프로세스 어떤 이유로 실패 하는 경우 사용 됩니다.

##  <a name="px_ulong"></a>  PX_ULong

사용자 컨트롤 내에서이 함수를 호출 `DoPropExchange` serialize 하거나 형식의 속성을 초기화 하려면 멤버 함수 **ULONG**합니다.

```
BOOL PX_ULong(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    ULONG& ulValue);

BOOL PX_ULong(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    ULONG& ulValue,
    long ulDefault);
```

### <a name="parameters"></a>매개 변수

*pPX*<br/>
에 대 한 포인터를 [CPropExchange](../../mfc/reference/cpropexchange-class.md) 개체 (일반적으로 매개 변수로 전달 `DoPropExchange`).

*pszPropName*<br/>
교환 되는 속성의 이름입니다.

*ulValue*<br/>
속성이 저장 된 변수에 대 한 참조 (일반적으로 클래스의 멤버 변수).

*ulDefault*<br/>
속성에 대 한 기본 값입니다.

### <a name="return-value"></a>반환 값

Exchange에 성공 하면 0이 아닌 값 실패 한 경우 0입니다.

### <a name="remarks"></a>설명

속성의 값을 읽거나 참조 변수를 쓸 *ulValue*를 적절 하 게 합니다. 하는 경우 *ulDefault* 지정, 속성의 기본값으로 사용 됩니다. 이 값은 컨트롤의 serialization 프로세스 어떤 이유로 실패 하는 경우 사용 됩니다.

##  <a name="px_ushort"></a>  PX_UShort

사용자 컨트롤 내에서이 함수를 호출 `DoPropExchange` serialize 하거나 형식의 속성을 초기화 하려면 멤버 함수 **unsigned short**합니다.

```
BOOL PX_UShort(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    USHORT& usValue);

BOOL PX_UShort(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    USHORT& usValue,
    USHORT usDefault);
```

### <a name="parameters"></a>매개 변수

*pPX*<br/>
에 대 한 포인터를 [CPropExchange](../../mfc/reference/cpropexchange-class.md) 개체 (일반적으로 매개 변수로 전달 `DoPropExchange`).

*pszPropName*<br/>
교환 되는 속성의 이름입니다.

*usValue*<br/>
속성이 저장 된 변수에 대 한 참조 (일반적으로 클래스의 멤버 변수).

*usDefault*<br/>
속성에 대 한 기본 값입니다.

### <a name="return-value"></a>반환 값

Exchange에 성공 하면 0이 아닌 값 실패 한 경우 0입니다.

### <a name="remarks"></a>설명

속성의 값을 읽거나 참조 변수를 쓸 *usValue*를 적절 하 게 합니다. 하는 경우 *usDefault* 지정, 속성의 기본값으로 사용 됩니다. 이 값은 컨트롤의 serialization 프로세스 어떤 이유로 실패 하는 경우 사용 됩니다.

##  <a name="px_string"></a>  PXstring

사용자 컨트롤 내에서이 함수를 호출 `DoPropExchange` 멤버 함수를 serialize 또는 문자 문자열 속성을 초기화 합니다.

```
BOOL PXstring(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    CString& strValue);

BOOL PXstring(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    CString& strValue,
    CString strDefault);
```

### <a name="parameters"></a>매개 변수

*pPX*<br/>
에 대 한 포인터를 [CPropExchange](../../mfc/reference/cpropexchange-class.md) 개체 (일반적으로 매개 변수로 전달 `DoPropExchange`).

*pszPropName*<br/>
교환 되는 속성의 이름입니다.

*strValue*<br/>
속성이 저장 된 변수에 대 한 참조 (일반적으로 클래스의 멤버 변수).

*strDefault*<br/>
속성에 대 한 기본 값입니다.

### <a name="return-value"></a>반환 값

Exchange에 성공 하면 0이 아닌 값 실패 한 경우 0입니다.

### <a name="remarks"></a>설명

속성의 값을 읽거나 참조 변수를 쓸 *strValue*를 적절 하 게 합니다. 하는 경우 *strDefault* 지정, 속성의 기본값으로 사용 됩니다. 이 값은 컨트롤의 serialization 프로세스 어떤 이유로 실패 하는 경우 사용 됩니다.

##  <a name="px_vbxfontconvert"></a>  PX_VBXFontConvert

사용자 컨트롤 내에서이 함수를 호출 `DoPropExchange` VBX 컨트롤의 글꼴 관련 속성을 변환 하 여 글꼴 속성을 초기화 하는 멤버 함수입니다.

```
BOOL PX_VBXFontConvert(
    CPropExchange* pPX,
    CFontHolder& font);
```

### <a name="parameters"></a>매개 변수

*pPX*<br/>
에 대 한 포인터를 [CPropExchange](../../mfc/reference/cpropexchange-class.md) 개체 (일반적으로 매개 변수로 전달 `DoPropExchange`).

*font*<br/>
변환 된 VBX 글꼴 관련 속성에 있는 OLE 컨트롤의 글꼴 속성입니다.

### <a name="return-value"></a>반환 값

Exchange에 성공 하면 0이 아닌 값 실패 한 경우 0입니다.

### <a name="remarks"></a>설명

이 함수는 VBX 컨트롤에 대 한 직접적인 대체가으로 설계 된 OLE 컨트롤에 의해서만 사용 됩니다. Visual Basic 개발 환경에서 해당 대체 OLE 컨트롤을 사용 하 여 VBX 컨트롤을 포함 하는 폼으로 변환 하는 경우 컨트롤의 호출 `IDataObject::SetData` 함수를 VBX 컨트롤의 속성 데이터를 포함 하는 속성 집합에 전달 합니다. 이 작업의 경우 인해 컨트롤의 `DoPropExchange` 호출할 함수입니다. `DoPropExchange` 호출할 수 있습니다 `PX_VBXFontConvert` VBX 컨트롤의 글꼴 관련 속성을 변환 하려면 (예를 들어, "FontName," "FontSize" 등) OLE 컨트롤의 글꼴 속성의 해당 구성 요소에 있습니다.

`PX_VBXFontConvert` 컨트롤 VBX 양식 응용 프로그램에서 실제로 변환 되는 경우에 호출 해야 합니다. 예를 들어:

[!code-cpp[NVC_MFCActiveXControl#14](../../mfc/codesnippet/cpp/persistence-of-ole-controls_1.cpp)]
[!code-cpp[NVC_MFCActiveXControl#15](../../mfc/codesnippet/cpp/persistence-of-ole-controls_2.cpp)]

## <a name="see-also"></a>참고자료

[매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)
