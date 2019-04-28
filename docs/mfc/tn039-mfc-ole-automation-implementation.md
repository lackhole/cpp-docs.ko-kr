---
title: 'TN039: MFC OLE 자동화 구현'
ms.date: 06/28/2018
f1_keywords:
- vc.mfc.ole
helpviewer_keywords:
- MFC, COM support
- IDispatch interface
- MFC, OLE DB and
- TN039
- Automation, MFC COM interface entry points
ms.assetid: 765fa3e9-dd54-4f08-9ad2-26e0546ff8b6
ms.openlocfilehash: cd6f8d681ef7e6517f2172ca6b22b13723a962fd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62305491"
---
# <a name="tn039-mfcole-automation-implementation"></a>TN039: MFC/OLE 자동화 구현

> [!NOTE]
> 다음 기술 노트는 온라인 설명서에 먼저 포함되어 있었으므로 업데이트되지 않았습니다. 따라서 일부 절차 및 항목은 만료되거나 올바르지 않을 수 있습니다. 최신 정보를 보려면 온라인 설명서 색인에서 관심 있는 항목을 검색하는 것이 좋습니다.

## <a name="overview-of-ole-idispatch-interface"></a>OLE IDispatch 인터페이스 개요

`IDispatch` 인터페이스는는 응용 프로그램 같은 Visual BASIC 또는 다른 언어와 같은 다른 응용 프로그램을 만들 수 있는 응용 프로그램의 기능을 사용 하는 속성과 메서드를 노출 하는 방법입니다. 이 인터페이스의 가장 중요 한 부분은 `IDispatch::Invoke` 함수입니다. "디스패치 맵"을 사용 하 여 MFC 구현 `IDispatch::Invoke`합니다. 디스패치 맵 레이아웃에 "shape"의 MFC 구현 정보를 제공 하 `CCmdTarget`-파생 클래스에서 직접 개체의 속성을 조작 하거나 멤버에 맞게 개체 내에서 함수를 호출할 수 있도록 `IDispatch::Invoke` 요청 수입니다.

대부분의 경우 ClassWizard 및 MFC 응용 프로그램 프로그래머가에서 OLE 자동화의 세부 정보를 대부분을 숨기려면 협력 합니다. 프로그래머가 응용 프로그램에서 노출 하는 실제 기능에 중점적으로 설명 하 고 기본 구조에 걱정할 필요가 없습니다.

그러나 백그라운드에서 수행 하는 MFC를 이해 해야 하는 경우가 있습니다. 이 프레임 워크를 할당 하는 방법을 다룰 **DISPID**멤버 함수 및 속성에 있습니다. MFC 할당 하는 데 사용 하 여 알고리즘에 대 한 지식이 **DISPID**가 필요한 응용 프로그램의 개체에 대 한 "형식 라이브러리"를 만들 때와 같은 Id를 알 필요가 있습니다.

## <a name="mfc-dispid-assignment"></a>MFC DISPID 할당

자동화 (Visual Basic 사용자, 예를 들어), automation의 최종 사용자의 실제 이름을 확인 있지만 (예: obj. 코드의 속성 및 메서드 사용 ShowWindow) 구현의 `IDispatch::Invoke` 실제 이름을 수신 하지 않습니다. 수신한을 최적화 하기 위해를 **DISPID**는 쿠키가 32 비트 "매직" 메서드 또는 속성에 액세스할 수 있는 설명입니다. 이러한 **DISPID** 에서 값이 반환 된 `IDispatch` 호출 하는 다른 메서드를 통해 구현 `IDispatch::GetIDsOfNames`합니다. 자동화 클라이언트 응용 프로그램 호출 `GetIDsOfNames` 각 멤버 또는 속성에 액세스 하 고 그에 대 한 이후 호출에 대 한 캐시를 하려는 면 `IDispatch::Invoke`합니다. 이 이렇게 하면 비용이 많이 드는 문자열 조회는 한 번 개체 사용 당 대신 한 번만 수행 당 `IDispatch::Invoke` 호출 합니다.

MFC를 결정 합니다 **DISPID**각 메서드 및 속성에 대 한 두 가지 사항에 따라:

- 디스패치 맵 (1 상대적)의 위쪽에서의 거리

- 디스패치 맵 가장 많이 파생 된 클래스 (상대 0)에서 거리

합니다 **DISPID** 두 부분으로 나뉩니다. 합니다 **LOWORD** 의 합니다 **DISPID** 디스패치 맵 위쪽에서 거리를 첫 번째 구성 요소를 포함 합니다. 합니다 **HIWORD** 최다 파생된 클래스에서의 거리를 포함 합니다. 예를 들어:

```cpp
class CDispPoint : public CCmdTarget
{
public:
    short m_x, m_y;
    // ...
    DECLARE_DISPATCH_MAP()
    // ...
};

class CDisp3DPoint : public CDispPoint
{
public:
    short m_z;
    // ...
    DECLARE_DISPATCH_MAP()
    // ...
};

BEGIN_DISPATCH_MAP(CDispPoint, CCmdTarget)
    DISP_PROPERTY(CDispPoint, "x", m_x, VT_I2)
    DISP_PROPERTY(CDispPoint, "y", m_y, VT_I2)
END_DISPATCH_MAP()

BEGIN_DISPATCH_MAP(CDisp3DPoint, CDispPoint)
    DISP_PROPERTY(CDisp3DPoint, "z", m_z, VT_I2)
END_DISPATCH_MAP()
```

알 수 있듯이는 OLE 자동화 인터페이스를 노출 하는 둘 다 두 클래스입니다. 다른에서 파생 하 고 따라서 OLE automation 부분을 포함 하는 기본 클래스의 기능을 활용 하 여 이러한 클래스 중 하나 ("x" 및 "y" 여기서에서 속성).

MFC는 생성 **DISPID**CDispPoint를 다음과 같이 클래스에 대 한 합니다.

```cpp
property X    (DISPID)0x00000001
property Y    (DISPID)0x00000002
```

속성은 기본 클래스에서 되지 않으므로 합니다 **HIWORD** 의 합니다 **DISPID** 은 항상 0 (CDispPoint에 대 한 가장 많이 파생 된 클래스에서 거리가 0).

MFC는 생성 **DISPID**CDisp3DPoint를 다음과 같이 클래스에 대 한 합니다.

```cpp
property Z    (DISPID)0x00000001
property X    (DISPID)0x00010001
property Y    (DISPID)0x00010002
```

Z 속성에서 제공 되는 **DISPID** 0으로 **HIWORD** CDisp3DPoint 속성을 노출 하는 클래스에 정의 되어 있으므로. X 및 Y 속성은 기본 클래스에서 정의 되므로 합니다 **HIWORD** 의 합니다 **DISPID** 1 이므로 이러한 속성이 정의 되어 있는 클래스는 최다 파생된 클래스에서 하나의 파생 된 거리 만큼 떨어진 합니다.

> [!NOTE]
> 합니다 **LOWORD** 항상 명시적으로 맵에 없는 경우에 지도에서 위치에 따라 결정 됩니다 **DISPID** (대 한 내용은 다음 섹션을 참조 합니다 **_ID** 버전을 `DISP_PROPERTY` 고 `DISP_FUNCTION` 매크로).

## <a name="advanced-mfc-dispatch-map-features"></a>고급 MFC 디스패치 맵 기능

이 릴리스의 Visual 클래스 마법사를 지원 하지 않는 추가 기능을 여러 가지 C++입니다. 클래스 마법사 지원 `DISP_FUNCTION`, `DISP_PROPERTY`, 및 `DISP_PROPERTY_EX` 정의 하는 메서드와 멤버 변수 속성을 가져오거나 설정 합니다. 멤버 함수 속성에 각각 있습니다. 이러한 기능은 일반적으로 대부분의 자동화 서버를 만드는 데 필요한 모든입니다.

지원 ClassWizard 매크로 적합 하지 않을 때 다음 추가 매크로 사용할 수 있습니다: `DISP_PROPERTY_NOTIFY`, 및 `DISP_PROPERTY_PARAM`합니다.

## <a name="disppropertynotify--macro-description"></a>DISP_PROPERTY_NOTIFY — 매크로 설명

```cpp
DISP_PROPERTY_NOTIFY(
    theClass,
    pszName,
    memberName,
    pfnAfterSet,
    vtPropType)
```

### <a name="parameters"></a>매개 변수

*theClass*<br/>
클래스의 이름입니다.

*pszName*<br/>
속성의 외부 이름입니다.

*memberName*<br/>
속성이 저장 되는 멤버 변수의 이름입니다.

*pfnAfterSet*<br/>
속성이 변경 될 때 호출할 멤버 함수의 이름입니다.

*vtPropType*<br/>
속성의 형식을 지정 하는 값입니다.

### <a name="remarks"></a>설명

이 매크로 매우 비슷합니다 DISP_PROPERTY를 제외 하 고 추가 인수를 허용 합니다. 추가 인수가 *pfnAfterSet,* 아무 것도 반환 및 매개 변수를 'void OnPropertyNotify()'를 사용 하는 멤버 함수 여야 합니다. 호출 됩니다 **후** 멤버 변수를 수정 했습니다.

## <a name="disppropertyparam--macro-description"></a>DISP_PROPERTY_PARAM — 매크로 설명

```cpp
DISP_PROPERTY_PARAM(
    theClass,
    pszName,
    pfnGet,
    pfnSet,
    vtPropType,
    vtsParams)
```

### <a name="parameters"></a>매개 변수

*theClass*<br/>
클래스의 이름입니다.

*pszName*<br/>
속성의 외부 이름입니다.

*memberGet*<br/>
속성을 가져오는 데 멤버 함수의 이름입니다.

*memberSet*<br/>
속성을 설정 하는 데 사용 하는 멤버 함수의 이름입니다.

*vtPropType*<br/>
속성의 형식을 지정 하는 값입니다.

*vtsParams*<br/>
각 매개 변수에 대해 VTS_를 구분 하는 공간의 문자열입니다.

### <a name="remarks"></a>설명

훨씬이 매크로 DISP_PROPERTY_EX 매크로 같은 별도 Get 및 Set 멤버 함수를 사용 하 여 액세스 하는 속성을 정의 합니다. 그러나이 매크로 사용 하면 속성에 대 한 매개 변수 목록을 지정할 수 있습니다. 이 다른 방법으로 매개 변수화 되거나 인덱싱된 속성을 구현 하기 위한 유용 합니다. 매개 변수를 항상 표시 됩니다 먼저 속성에 대 한 새 값 뒤에. 예를 들어:

```cpp
DISP_PROPERTY_PARAM(CMyObject, "item", GetItem, SetItem, VT_DISPATCH, VTS_I2 VTS_I2)
```

get 및 set 멤버 함수에 해당 합니다.

```cpp
LPDISPATCH CMyObject::GetItem(short row, short col)
void CMyObject::SetItem(short row, short col, LPDISPATCH newValue)
```

## <a name="dispxxxxid--macro-descriptions"></a>DISP_XXXX_ID — 매크로 설명

```cpp
DISP_FUNCTION_ID(
    theClass,
    pszName,
    dispid,
    pfnMember,
    vtRetVal,
    vtsParams)
DISP_PROPERTY_ID(
    theClass,
    pszName,
    dispid,
    memberName,
    vtPropType)
DISP_PROPERTY_NOTIFY_ID(
    theClass,
    pszName,
    dispid,
    memberName,
    pfnAfterSet,
    vtPropType)
DISP_PROPERTY_EX_ID(
    theClass,
    pszName,
    dispid,
    pfnGet,
    pfnSet,
    vtPropType)
DISP_PROPERTY_PARAM_ID(
    theClass,
    pszName,
    dispid,
    pfnGet,
    pfnSet,
    vtPropType,
    vtsParams)
```

### <a name="parameters"></a>매개 변수

*theClass*<br/>
클래스의 이름입니다.

*pszName*<br/>
속성의 외부 이름입니다.

*dispid*<br/>
속성 또는 메서드에 대 한 고정된 DISPID입니다.

*pfnGet*<br/>
속성을 가져오는 데 멤버 함수의 이름입니다.

*pfnSet*<br/>
속성을 설정 하는 데 사용 하는 멤버 함수의 이름입니다.

*memberName*<br/>
속성에 매핑할 멤버 변수의 이름

*vtPropType*<br/>
속성의 형식을 지정 하는 값입니다.

*vtsParams*<br/>
각 매개 변수에 대해 VTS_를 구분 하는 공간의 문자열입니다.

### <a name="remarks"></a>설명

이러한 매크로 사용 하면 지정 하는 **DISPID** MFC 대신 자동으로 하나를 할당 합니다. 이러한 고급 매크로 이름이 같은 매크로 이름에 해당 ID를 추가 하는 점을 제외 하 고 (예: **DISP_PROPERTY_ID**) ID 바로 뒤에 지정 된 매개 변수에 의해 결정 됩니다 합니다 *pszName* 매개 변수입니다. AFXDISP를 참조 하세요. 이러한 매크로 대 한 자세한 내용은 H입니다. 합니다 **_ID** 디스패치 맵 끝에 항목을 배치 해야 합니다. 자동 영향에 **DISPID** 동일한 방식으로 비-생성 **_ID** 매크로 버전은 (는 **DISPID**의위치에 따라 결정 됩니다). 예를 들어:

```cpp
BEGIN_DISPATCH_MAP(CDisp3DPoint, CCmdTarget)
    DISP_PROPERTY(CDisp3DPoint, "y", m_y, VT_I2)
    DISP_PROPERTY(CDisp3DPoint, "z", m_z, VT_I2)
    DISP_PROPERTY_ID(CDisp3DPoint, "x", 0x00020003, m_x, VT_I2)
END_DISPATCH_MAP()
```

MFC는 CDisp3DPoint 클래스에 대 한 다음과 같은 Dispid을 생성 합니다.

```cpp
property X    (DISPID)0x00020003
property Y    (DISPID)0x00000002
property Z    (DISPID)0x00000001
```

고정 지정 **DISPID** 기존 디스패치 인터페이스에 대 한 이전 버전과 호환성을 유지 하기 위해 또는 특정 시스템 정의 메서드 또는 속성을 구현 하려면 유용 (일반적으로 음수에 나타난  **DISPID**와 같은 합니다 **DISPID_NEWENUM** 컬렉션).

## <a name="retrieving-the-idispatch-interface-for-a-coleclientitem"></a>COleClientItem IDispatch 인터페이스를 검색합니다.

여러 서버는 OLE 서버 기능 외에도 해당 문서 개체 내에서 자동화를 지원 합니다. 이 자동화 인터페이스에 대 한 액세스 권한을 얻으려면, 직접 액세스 하는 데 필요한 것은 `COleClientItem::m_lpObject` 멤버 변수입니다. 아래 코드를 검색 합니다 `IDispatch` 에서 파생 된 개체에 대 한 인터페이스 `COleClientItem`합니다. 찾을이 기능이 필요한 경우 응용 프로그램에 아래 코드를 포함할 수 있습니다.

```cpp
LPDISPATCH CMyClientItem::GetIDispatch()
{
    ASSERT_VALID(this);
    ASSERT(m_lpObject != NULL);

    LPUNKNOWN lpUnk = m_lpObject;

    Run();      // must be running

    LPOLELINK lpOleLink = NULL;
    if (m_lpObject->QueryInterface(IID_IOleLink,
        (LPVOID FAR*)&lpOleLink) == NOERROR)
    {
        ASSERT(lpOleLink != NULL);
        lpUnk = NULL;
        if (lpOleLink->GetBoundSource(&lpUnk) != NOERROR)
        {
            TRACE0("Warning: Link is not connected!\n");
            lpOleLink->Release();
            return NULL;
        }
        ASSERT(lpUnk != NULL);
    }

    LPDISPATCH lpDispatch = NULL;
    if (lpUnk->QueryInterface(IID_IDispatch, &lpDispatch) != NOERROR)
    {
        TRACE0("Warning: does not support IDispatch!\n");
        return NULL;
    }

    ASSERT(lpDispatch != NULL);
    return lpDispatch;
}
```

디스패치 인터페이스에서 반환 된이 함수 다음 직접 사용 하거나 연결할 수 없습니다는 `COleDispatchDriver` 형식이 안전한 액세스 합니다. 직접 사용 하는 경우를 호출 해야 해당 `Release` 멤버 포인터를 사용 하 여 때 작업을 통해 (의 `COleDispatchDriver` 소멸자 기능은 기본적으로).

## <a name="see-also"></a>참고자료

[번호별 기술 참고 사항](../mfc/technical-notes-by-number.md)<br/>
[범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)
