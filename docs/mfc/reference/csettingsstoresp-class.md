---
title: CSettingsStoreSP 클래스
ms.date: 11/04/2016
f1_keywords:
- CSettingsStoreSP
- AFXSETTINGSSTORE/CSettingsStoreSP
- AFXSETTINGSSTORE/CSettingsStoreSP::CSettingsStoreSP
- AFXSETTINGSSTORE/CSettingsStoreSP::Create
- AFXSETTINGSSTORE/CSettingsStoreSP::SetRuntimeClass
helpviewer_keywords:
- CSettingsStoreSP [MFC], CSettingsStoreSP
- CSettingsStoreSP [MFC], Create
- CSettingsStoreSP [MFC], SetRuntimeClass
ms.assetid: bcd37f40-cfd4-4d17-a5ce-3bfabe995dcc
ms.openlocfilehash: 5c7a992b983552340ebe21e59d2ee9a667841ec0
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64339529"
---
# <a name="csettingsstoresp-class"></a>CSettingsStoreSP 클래스

합니다 `CSettingsStoreSP` 클래스는 도우미 클래스의 인스턴스를 만드는 데 사용할 수 있는 합니다 [CSettingsStore 클래스](../../mfc/reference/csettingsstore-class.md)합니다.

## <a name="syntax"></a>구문

```
class CSettingsStoreSP
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CSettingsStoreSP::CSettingsStoreSP](#csettingsstoresp)|`CSettingsStoreSP` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CSettingsStoreSP::Create](#create)|파생 된 클래스의 인스턴스를 만들고 `CSettingsStore`합니다.|
|[CSettingsStoreSP::SetRuntimeClass](#setruntimeclass)|런타임 클래스를 설정합니다. `Create` 메서드 런타임 클래스를 사용 하 여 어떤 종류의 개체를 확인 합니다.|

### <a name="data-members"></a>데이터 멤버

|이름|설명|
|----------|-----------------|
|`m_dwUserData`|에 저장 된 사용자 지정 사용자 데이터는 `CSettingsStoreSP` 개체입니다. 생성자에서이 데이터를 제공 합니다 `CSettingsStoreSP` 개체입니다.|
|`m_pRegistry`|합니다 `CSettingsStore`-파생 된 개체는 `Create` 메서드를 만듭니다.|

## <a name="remarks"></a>설명

사용할 수는 `CSettingsStoreSP` 클래스 모든 MFC 레지스트리 작업 XML 파일, 데이터베이스 등의 다른 위치로 리디렉션할 수 있습니다. 이를 수행하려면 다음 단계를 따르십시오.

1. 클래스를 만듭니다 (같은 `CMyStore`)에서 파생 `CSettingsStore`합니다.

1. 사용 하 여 [DECLARE_DYNCREATE](run-time-object-model-services.md#declare_dyncreate) 하 고 [IMPLEMENT_DYNCREATE](run-time-object-model-services.md#implement_dyncreate) 사용자를 사용 하 여 매크로 `CSettingsStore` 클래스를 사용 하는 동적 생성 합니다.

1. 가상 함수를 재정의 하 고 구현 합니다 `Read` 고 `Write` 사용자 지정 클래스의 함수입니다. 원하는 위치로 데이터를 읽고 다른 모든 기능을 구현 합니다.

1. 응용 프로그램에서 호출할 `CSettingsStoreSP::SetRuntimeClass` 포인터를 전달 합니다 [CRuntimeClass 구조체](../../mfc/reference/cruntimeclass-structure.md) 클래스에서 가져온입니다.

프레임 워크는 주로 레지스트리를 액세스 하 고, 때마다 이제 동적으로 사용자 지정 클래스를 인스턴스화하고 하 고 읽기 또는 쓰기 데이터를 사용 합니다.

`CSettingsStoreSP::SetRuntimeClass` 전역 정적 변수를 사용 합니다. 따라서 하나의 사용자 지정 저장소를 한 번에 사용할 수 있습니다.

## <a name="requirements"></a>요구 사항

**헤더:** afxsettingsstore.h

##  <a name="create"></a>  CSettingsStoreSP::Create

파생 된 개체의 새 인스턴스를 만듭니다는 [CSettingsStore 클래스](../../mfc/reference/csettingsstore-class.md)합니다.

```
CSettingsStore& CSettingsStoreSP Create(
    BOOL bAdmin,
    BOOL bReadOnly);
```

### <a name="parameters"></a>매개 변수

*bAdmin*<br/>
[in] 결정 하는 부울 매개 변수 여부를 `CSettingsStore` 개체는 관리자 모드에서 만들어집니다.

*bReadOnly*<br/>
[in] 결정 하는 부울 매개 변수 여부를 `CSettingsStore` 읽기 전용 액세스에 대 한 개체가 만들어집니다.

### <a name="return-value"></a>반환 값

새로 만든에 대 한 참조 `CSettingsStore` 개체입니다.

### <a name="remarks"></a>설명

메서드를 사용할 수 있습니다 [CSettingsStoreSP::SetRuntimeClass](#setruntimeclass) 개체의 유형을 결정할 `CSettingsStoreSP::Create` 만들어집니다. 기본적으로이 메서드는 만듭니다는 `CSettingsStore` 개체입니다.

만드는 경우는 `CSettingsStore` 레지스트리에 대 한 모든 액세스에 대 한 기본 위치는 HKEY_LOCAL_MACHINE 관리자 모드에서 개체입니다. 그렇지 않으면 모든 레지스트리 액세스에 대 한 기본 위치는 HKEY_CURRENT_USER 합니다.

하는 경우 *bAdmin* 가 TRUE 인 응용 프로그램에 관리 권한이 있어야 합니다. 그렇지 않으면 레지스트리를 액세스 하려고 하면 실패 합니다.

### <a name="example"></a>예제

다음 예제에서는 사용 하는 방법에 설명 합니다 `Create` 메서드는 `CSettingsStoreSP` 클래스입니다.

[!code-cpp[NVC_MFC_RibbonApp#33](../../mfc/reference/codesnippet/cpp/csettingsstoresp-class_1.cpp)]

##  <a name="csettingsstoresp"></a>  CSettingsStoreSP::CSettingsStoreSP

생성 된 [CSettingsStoreSP 클래스](../../mfc/reference/csettingsstoresp-class.md) 개체입니다.

```
CSettingsStoreSP::CSettingsStoreSP(DWORD dwUserData = 0);
```

### <a name="parameters"></a>매개 변수

*dwUserData*<br/>
[in] 사용자 정의 데이터는는 `CSettingsStoreSP` 저장소 개체입니다.

### <a name="remarks"></a>설명

합니다 `CSettingsStoreSP` 에서 데이터를 저장 하는 개체 *dwUserData* 보호 된 멤버 변수의 `m_dwUserData`합니다.

##  <a name="setruntimeclass"></a>  CSettingsStoreSP::SetRuntimeClass

런타임 클래스를 설정합니다. 메서드 [CSettingsStoreSP::Create](#create) 런타임 클래스를 사용 하 여 만들 개체의 유형을 결정 합니다.

```
static BOOL __stdcall CSettingsStoreSP::SetRuntimeClass(CRuntimeClass* pRTI);
```

### <a name="parameters"></a>매개 변수

*pRTI*<br/>
[in] 파생 된 클래스에 대 한 런타임 클래스 정보에 대 한 포인터를 [CSettingsStore 클래스](../../mfc/reference/csettingsstore-class.md)합니다.

### <a name="return-value"></a>반환 값

성공 하면 클래스에서 식별 하는 경우에 FALSE *pRTI* 에서 파생 되지 않은 `CSettingsStore`합니다.

### <a name="remarks"></a>설명

사용할 수는 [CSettingsStoreSP 클래스](../../mfc/reference/csettingsstoresp-class.md) 클래스에서 파생 시키는 `CSettingsStore`합니다. 메서드를 사용 하 여 `SetRuntimeClass` 에서 파생 되는 사용자 지정 클래스의 개체를 만들려는 경우 `CSettingsStore`합니다.

## <a name="see-also"></a>참고자료

[클래스](../../mfc/reference/mfc-classes.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CSettingsStore Class](../../mfc/reference/csettingsstore-class.md)
