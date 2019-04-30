---
title: 응용 프로그램 컨트롤
ms.date: 11/04/2016
f1_keywords:
- vc.mfc.macros
helpviewer_keywords:
- application control [MFC]
ms.assetid: c1f69f15-e0fe-4515-9f36-d63d31869deb
ms.openlocfilehash: e4944c1cf1114bbd009ebc62b776628ba86b3b4d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62352049"
---
# <a name="application-control"></a>응용 프로그램 컨트롤

OLE 응용 프로그램 및 해당 개체를 통해 상당한 컨트롤에 필요합니다. OLE 시스템 Dll을 시작 하 고 응용 프로그램을 자동으로 릴리스, 프로덕션 및 개체의 수정 조정 및 등에 있어야 합니다. 이 항목에서는에 포함 된 함수에는 해당 요구 사항을 충족 합니다. OLE 시스템 Dll에 의해 호출 되는 것 외에도 이러한 함수 에서도 응용 프로그램에서 라고도 합니다.

### <a name="application-control"></a>응용 프로그램 컨트롤

|||
|-|-|
|[AfxOleCanExitApp](#afxolecanexitapp)|응용 프로그램이 종료될 수 있는지 여부를 나타냅니다.|
|[AfxOleGetMessageFilter](#afxolegetmessagefilter)|응용 프로그램의 현재 메시지 필터를 검색합니다.|
|[AfxOleGetUserCtrl](#afxolegetuserctrl)|현재 사용자 정의 컨트롤 플래그를 검색합니다.|
|[AfxOleSetUserCtrl](#afxolesetuserctrl)|설정 하거나 사용자 정의 컨트롤 플래그를 지웁니다.|
|[AfxOleLockApp](#afxolelockapp)|응용 프로그램의 활성 개체 수의 프레임 워크의 전역 카운트를 증가 시킵니다.|
|[AfxOleLockControl](#afxolelockcontrol)| 지정된 된 컨트롤의 클래스 팩터리를 잠급니다. |
|[AfxOleUnlockApp](#afxoleunlockapp)|감소 프레임 워크의 개수는 응용 프로그램의 활성 개체입니다.|
|[AfxOleUnlockControl](#afxoleunlockcontrol)| 지정된 된 컨트롤의 클래스 팩터리를 잠금 해제합니다. |
|[AfxOleRegisterServerClass](#afxoleregisterserverclass)|OLE 시스템 레지스트리에 서버를 등록합니다.|
|[AfxOleSetEditMenu](#afxoleseteditmenu)|에 대 한 사용자 인터페이스를 구현 합니다 *typename* 명령 개체입니다.|

##  <a name="afxolecanexitapp"></a>  AfxOleCanExitApp

응용 프로그램이 종료될 수 있는지 여부를 나타냅니다.

```
BOOL AFXAPI AfxOleCanExitApp();
```

### <a name="return-value"></a>반환 값

응용 프로그램이 종료될 수 있으면 0이 아닌 값이고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

개체에 대해 해결되지 않은 참조가 있으면 응용 프로그램이 종료될 수 없습니다. 전역 함수 `AfxOleLockApp` 및 `AfxOleUnlockApp`은 각각 응용 프로그램의 개체에 대한 참조 수를 늘리거나 줄입니다. 이 카운터가 0이 아니면 응용 프로그램이 종료될 수 없습니다. 카운터가 0이 아니면 사용자가 시스템 메뉴에서 닫기를 선택하거나 파일 메뉴에서 종료를 선택할 때 응용 프로그램의 기본 창이 숨겨집니다(삭제되지 않음). 이 함수를 호출 하는 프레임 워크 `CFrameWnd::OnClose`합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCAutomation#2](../../mfc/codesnippet/cpp/application-control_1.cpp)]

## <a name="requirements"></a>요구 사항

**헤더**: afxdisp.h

##  <a name="afxolegetmessagefilter"></a>  AfxOleGetMessageFilter

응용 프로그램의 현재 메시지 필터를 검색합니다.

```
COleMessageFilter* AFXAPI AfxOleGetMessageFilter();
```

### <a name="return-value"></a>반환 값

현재 메시지 필터에 대 한 포인터입니다.

### <a name="remarks"></a>설명

현재 액세스 하려면이 함수를 호출 `COleMessageFilter`-파생 개체를 호출 하는 것 처럼 `AfxGetApp` 현재 응용 프로그램 개체에 액세스 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCAutomation#3](../../mfc/codesnippet/cpp/application-control_2.cpp)]

[!code-cpp[NVC_MFCAutomation#4](../../mfc/codesnippet/cpp/application-control_3.cpp)]

### <a name="requirements"></a>요구 사항

**헤더**: afxwin.h

##  <a name="afxolegetuserctrl"></a>  AfxOleGetUserCtrl

현재 사용자 정의 컨트롤 플래그를 검색합니다.

```
BOOL AFXAPI AfxOleGetUserCtrl();
```

### <a name="return-value"></a>반환 값

사용자가 응용 프로그램의 제어 하는 경우 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

사용자가 응용 프로그램의 컨트롤 사용자가 명시적으로 열거나 새 문서를 생성 하는 경우. 해당 사용자가 컨트롤의 경우 응용 프로그램을 OLE 시스템 Dll에서 시작할 수 없습니다-즉, 사용자는 시스템 셸로 사용 하 여 응용 프로그램을 시작한 경우.

### <a name="requirements"></a>요구 사항

**헤더**: afxdisp.h

##  <a name="afxolesetuserctrl"></a>  AfxOleSetUserCtrl

설정 하거나에 대 한 참조에 설명 된 사용자 정의 컨트롤 플래그를 지웁니다 `AfxOleGetUserCtrl`합니다.

```
void AFXAPI AfxOleSetUserCtrl(BOOL bUserCtrl);
```

### <a name="parameters"></a>매개 변수

*bUserCtrl*<br/>
사용자 정의 컨트롤 플래그를 설정 하거나 선택 취소 되는지 여부를 지정 합니다.

### <a name="remarks"></a>설명

프레임 워크를이 함수를 호출 하지만 사용자를 만들거나 문서를 로드 하는 경우 문서가 로드 되거나 컨테이너 응용 프로그램에서 포함된 된 개체를 로드 하는 등의 간접 작업을 통해 만든 때가 아니라 합니다.

응용 프로그램에서 다른 작업 응용 프로그램의 컨트롤에 사용자를 추가 해야 하는 경우이 함수를 호출 합니다.

### <a name="requirements"></a>요구 사항

**헤더**: afxdisp.h

##  <a name="afxolelockapp"></a>  AfxOleLockApp

응용 프로그램의 활성 개체 수의 프레임 워크의 전역 카운트를 증가 시킵니다.

```
void AFXAPI AfxOleLockApp();
```

### <a name="remarks"></a>설명

프레임 워크 응용 프로그램에서 활성 개체 수의 개수를 유지 합니다. 합니다 `AfxOleLockApp` 및 `AfxOleUnlockApp` 함수는 각각 증가 및이 수가 감소 합니다.

사용자가 활성 개체가 포함 된 응용 프로그램을 닫을 하려고 할 때-활성 개체 수는 0이 아닌 응용 프로그램, 프레임 워크를 완전히 종료 하는 대신 사용자의 보기에서 응용 프로그램을 숨깁니다. `AfxOleCanExitApp` 함수 응용 프로그램을 종료할 수 있는지 여부를 나타냅니다.

호출 `AfxOleLockApp` 에서 클라이언트 응용 프로그램에서 사용 되는 동안 제거할 해당 개체에 적합 하지 않을 수는 경우 OLE 인터페이스를 노출 하는 개체입니다. 호출할 수도 `AfxOleUnlockApp` 를 호출 하는 모든 개체의 소멸자에서 `AfxOleLockApp` 생성자에서. 기본적으로 `COleDocument` (및 파생 클래스) 자동으로 잠금 및 응용 프로그램을 잠금 해제 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCAutomation#5](../../mfc/codesnippet/cpp/application-control_4.cpp)]

### <a name="requirements"></a>요구 사항

**헤더**: afxdisp.h

##  <a name="afxoleunlockapp"></a>  AfxOleUnlockApp

감소 프레임 워크의 응용 프로그램의 활성 개체 수입니다.

```
void AFXAPI AfxOleUnlockApp();
```

### <a name="remarks"></a>설명

참조 `AfxOleLockApp` 대 한 자세한 내용은 합니다.

활성 개체 수가 0에 도달 하면 `AfxOleOnReleaseAllObjects` 라고 합니다.

### <a name="example"></a>예제

예를 참조 하세요 [AfxOleLockApp](#afxolelockapp)합니다.

### <a name="requirements"></a>요구 사항

**헤더**: afxdisp.h

## <a name="afxolelockcontrol"></a>AfxOleLockControl

컨트롤과 연결된 동적으로 생성된 데이터가 메모리에 유지되도록 지정된 컨트롤의 클래스 팩터리를 잠급니다.

### <a name="syntax"></a>구문

```
BOOL AFXAPI AfxOleLockControl(  REFCLSID clsid  );
BOOL AFXAPI AfxOleLockControl( LPCTSTR lpszProgID );
```

### <a name="parameters"></a>매개 변수

*clsid*<br/>
컨트롤의 고유 클래스 ID입니다.

*lpszProgID*<br/>
컨트롤의 고유 프로그램 ID입니다.

### <a name="return-value"></a>반환 값

컨트롤의 클래스 팩터리가 성공적으로 잠겼을 경우 0이 아닌 값이고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이렇게 하면 컨트롤 표시 속도가 상당히 빨라질 수 있습니다. 예를 들어 대화 상자에서 컨트롤을 만들고 이 컨트롤을 `AfxOleLockControl`로 잠글 경우에는 대화 상자를 표시 또는 삭제할 때마다 대화 상자를 만들고 종료할 필요가 없습니다. 사용자가 대화 상자를 반복해서 열고 닫는 경우, 컨트롤을 잠그면 성능이 크게 향상될 수 있습니다. 컨트롤을 제거할 준비가 되면 `AfxOleUnlockControl`을 호출합니다.

### <a name="example"></a>예제

```cpp
// Starts and locks control's (Microsoft Calendar) class factory.
// Control will remain in memory for lifetime of
// application or until AfxOleUnlockControl() is called.

AfxOleLockControl(_T("MSCAL.Calendar"));
```

### <a name="requirements"></a>요구 사항

**헤더:** afxwin.h

##  <a name="afxoleregisterserverclass"></a>  AfxOleRegisterServerClass

이 함수를 사용 하면 OLE 시스템 레지스트리에 서버를 등록할 수 있습니다.

```
BOOL AFXAPI AfxOleRegisterServerClass(
    REFCLSID clsid,
    LPCTSTR lpszClassName,
    LPCTSTR lpszShortTypeName,
    LPCTSTR lpszLongTypeName,
    OLE_APPTYPE nAppType = OAT_SERVER,
    LPCTSTR* rglpszRegister = NULL,
    LPCTSTR* rglpszOverwrite = NULL);
```

### <a name="parameters"></a>매개 변수

*clsid*<br/>
서버의 OLE 클래스 ID에 대 한 참조

*lpszClassName*<br/>
서버 개체의 클래스 이름을 포함 하는 문자열에 대 한 포인터입니다.

*lpszShortTypeName*<br/>
"차트입니다."와 같은 서버의 개체 형식의 짧은 이름을 포함 하는 문자열에 대 한 포인터

*lpszLongTypeName*<br/>
"Microsoft Excel 5.0 차트입니다."와 같은 서버의 개체 형식의 긴 이름을 포함 하는 문자열에 대 한 포인터

*nAppType*<br/>
OLE 응용 프로그램 종류를 지정 하는 OLE_APPTYPE 열거형에서 가져온 값입니다. 가능한 값 다음과 같습니다.

- OAT_INPLACE_SERVER 서버 전체 서버 사용자 인터페이스에 있습니다.

- OAT_SERVER 서버 지원만 포함 합니다.

- OAT_CONTAINER 컨테이너 포함에 대 한 링크를 지원합니다.

- OAT_DISPATCH_OBJECT `IDispatch`-수 있는 개체입니다.

*rglpszRegister*<br/>
키 및 키에 대 한 기존 값이 없는 발견 되 면 OLE 시스템 레지스트리에 추가할 값을 나타내는 문자열에 대 한 포인터의 배열입니다.

*rglpszOverwrite*<br/>
키와 레지스트리에 지정된 된 키에 대 한 기존 값을 포함 하는 경우 OLE 시스템 레지스트리에 추가 되는 값을 나타내는 문자열에 대 한 포인터의 배열입니다.

### <a name="return-value"></a>반환 값

서버 클래스 성공적으로 등록 되 면 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

대부분의 응용 프로그램에서는 `COleTemplateServer::Register` 응용 프로그램의 문서 유형을 등록 합니다. 응용 프로그램의 시스템 레지스트리 형식으로 일반적인 패턴은 맞지 않은 경우 사용할 수 있습니다 `AfxOleRegisterServerClass` 더 제어 합니다.

레지스트리 키와 값의 집합으로 구성 됩니다. 합니다 *rglpszRegister* 하 고 *rglpszOverwrite* 인수는 문자열에 대 한 포인터의 배열, 구성 된 키와 값을 구분 하 여는 **NULL** 문자 ( `'\0'`). 이러한 문자열의 각 문자 시퀀스를 해당 위치 표시 하는 대체 가능 매개 변수를 가질 수 있습니다 *%1* 를 통해 *%5*합니다.

기호 채워지는 다음과 같습니다.

|기호|값|
|------------|-----------|
|%1|문자열로 서식이 지정 된 클래스 ID|
|%2|클래스 이름|
|%3|실행 파일 경로|
|%4|짧은 형식 이름|
|%5|긴 형식 이름|

### <a name="requirements"></a>요구 사항

**헤더**: afxdisp.h

##  <a name="afxoleseteditmenu"></a>  AfxOleSetEditMenu

에 대 한 사용자 인터페이스를 구현 합니다 *typename* 명령 개체입니다.

```
void AFXAPI AfxOleSetEditMenu(
    COleClientItem* pClient,
    CMenu* pMenu,
    UINT iMenuItem,
    UINT nIDVerbMin,
    UINT nIDVerbMax = 0,
    UINT nIDConvert = 0);
```

### <a name="parameters"></a>매개 변수

*pClient*<br/>
클라이언트가 OLE 항목에 대 한 포인터입니다.

*pMenu*<br/>
업데이트할 메뉴 개체에 대 한 포인터입니다.

*iMenuItem*<br/>
업데이트 메뉴 항목의 인덱스입니다.

*nIDVerbMin*<br/>
기본 동사에 해당 하는 명령 ID입니다.

*nIDVerbMax*<br/>
동사 마지막에 해당 하는 명령 ID입니다.

*nIDConvert*<br/>
변환 메뉴 항목의 ID입니다.

### <a name="remarks"></a>설명

메뉴 항목은 서버 기본 동사를 인식 하는 경우 "동사 *typename* 개체" 및 *nIDVerbMin* 명령이 사용자가 명령을 선택할 때 전송 됩니다. 서버에는 몇 가지 동사 인식 경우 메뉴 항목 " *typename* 개체" 모든 동사를 나열 하는 하위 메뉴 명령을 선택 하면 나타납니다. 하위 메뉴에서 동사를 선택 하면 *nIDVerbMin* 하는 경우 첫 번째 동사를 선택 하면 보내집니다 *nIDVerbMin* + 1은 두 번째 동사 등 선택한 경우 전송 됩니다. 기본 `COleDocument` 구현은이 기능을 자동으로 처리 합니다.

클라이언트 응용 프로그램 리소스 스크립트에서 다음 문이 있어야 합니다. (합니다. RC) 파일:

**#include \<afxolecl.rc>**

### <a name="requirements"></a>요구 사항

**헤더**: afxole.h

## <a name="afxoleunlockcontrol"></a> AfxOleUnlockControl

지정된 된 컨트롤의 클래스 팩터리를 잠금 해제합니다.

### <a name="syntax"></a>구문

```
BOOL AFXAPI AfxOleUnlockControl( REFCLSID clsid );
BOOL AFXAPI AfxOleUnlockControl( LPCTSTR lpszProgID );
```

### <a name="parameters"></a>매개 변수

*clsid*<br/>
컨트롤의 고유 클래스 ID입니다.

*lpszProgID*<br/>
컨트롤의 고유 프로그램 ID입니다.

### <a name="return-value"></a>반환 값

컨트롤의 클래스 팩터리가 성공적으로 잠금; 하지 않았으면 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

컨트롤을 사용 하 여 잠겨 `AfxOleLockControl`컨트롤과 연결 된 동적으로 생성된 된 데이터는 메모리에 남아 있도록 합니다. 크게 컨트롤을 만들고 제거 될 때마다 표시 되는 수 해야 하기 때문에 컨트롤의 표시 속도 높일 수이 있습니다. 컨트롤을 제거할 준비가 되면 `AfxOleUnlockControl`을 호출합니다.

### <a name="example"></a>예제

```cpp
// Unlock control's (Microsoft Calendar Control) class factory.

AfxOleUnlockControl(_T("MSCAL.Calendar"));
```

### <a name="requirements"></a>요구 사항

**헤더:** afxwin.h

## <a name="see-also"></a>참고자료

[매크로 및 전역](mfc-macros-and-globals.md)<br/>
