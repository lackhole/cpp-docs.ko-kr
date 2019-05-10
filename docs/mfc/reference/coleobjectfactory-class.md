---
title: COleObjectFactory 클래스
ms.date: 11/04/2016
f1_keywords:
- COleObjectFactory
- AFXDISP/COleObjectFactory
- AFXDISP/COleObjectFactory::COleObjectFactory
- AFXDISP/COleObjectFactory::GetClassID
- AFXDISP/COleObjectFactory::IsLicenseValid
- AFXDISP/COleObjectFactory::IsRegistered
- AFXDISP/COleObjectFactory::Register
- AFXDISP/COleObjectFactory::RegisterAll
- AFXDISP/COleObjectFactory::Revoke
- AFXDISP/COleObjectFactory::RevokeAll
- AFXDISP/COleObjectFactory::UnregisterAll
- AFXDISP/COleObjectFactory::UpdateRegistry
- AFXDISP/COleObjectFactory::UpdateRegistryAll
- AFXDISP/COleObjectFactory::GetLicenseKey
- AFXDISP/COleObjectFactory::OnCreateObject
- AFXDISP/COleObjectFactory::VerifyLicenseKey
- AFXDISP/COleObjectFactory::VerifyUserLicense
helpviewer_keywords:
- COleObjectFactory [MFC], COleObjectFactory
- COleObjectFactory [MFC], GetClassID
- COleObjectFactory [MFC], IsLicenseValid
- COleObjectFactory [MFC], IsRegistered
- COleObjectFactory [MFC], Register
- COleObjectFactory [MFC], RegisterAll
- COleObjectFactory [MFC], Revoke
- COleObjectFactory [MFC], RevokeAll
- COleObjectFactory [MFC], UnregisterAll
- COleObjectFactory [MFC], UpdateRegistry
- COleObjectFactory [MFC], UpdateRegistryAll
- COleObjectFactory [MFC], GetLicenseKey
- COleObjectFactory [MFC], OnCreateObject
- COleObjectFactory [MFC], VerifyLicenseKey
- COleObjectFactory [MFC], VerifyUserLicense
ms.assetid: ab179c1e-4af2-44aa-a576-37c48149b427
ms.openlocfilehash: 25dce92f49ba9de08fcf33d54db8e97d520f5ea4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62224390"
---
# <a name="coleobjectfactory-class"></a>COleObjectFactory 클래스

서버, 자동화 개체, 문서와 같은 OLE 개체를 만드는 OLE 클래스 팩터리를 구현합니다.

## <a name="syntax"></a>구문

```
class COleObjectFactory : public CCmdTarget
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[COleObjectFactory::COleObjectFactory](#coleobjectfactory)|`COleObjectFactory` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[COleObjectFactory::GetClassID](#getclassid)|반환 된 OLE 클래스는이 팩터리가 만드는 개체의 ID입니다.|
|[COleObjectFactory::IsLicenseValid](#islicensevalid)|컨트롤의 라이선스를 유효한 인지 확인 합니다.|
|[COleObjectFactory::IsRegistered](#isregistered)|개체 팩터리 OLE 시스템 Dll 사용 하 여 등록 되는지 여부를 나타냅니다.|
|[COleObjectFactory::Register](#register)|OLE 시스템 Dll 사용 하 여이 개체 팩터리를 등록합니다.|
|[COleObjectFactory::RegisterAll](#registerall)|OLE 시스템 Dll 사용 하 여 모든 응용 프로그램의 개체 팩터리를 등록합니다.|
|[COleObjectFactory::Revoke](#revoke)|OLE 시스템 Dll 사용 하 여이 개체 팩터리의이 등록을 취소합니다.|
|[COleObjectFactory::RevokeAll](#revokeall)|OLE 시스템 Dll 사용 하 여 응용 프로그램의 개체 팩터리 등록을 취소합니다.|
|[COleObjectFactory::UnregisterAll](#unregisterall)|모든 응용 프로그램의 개체 팩터리를 등록 취소합니다.|
|[COleObjectFactory::UpdateRegistry](#updateregistry)|OLE 시스템 레지스트리를 사용 하 여이 개체 팩터리를 등록합니다.|
|[COleObjectFactory::UpdateRegistryAll](#updateregistryall)|OLE 시스템 레지스트리를 사용 하 여 모든 응용 프로그램의 개체 팩터리를 등록합니다.|

### <a name="protected-methods"></a>Protected 메서드

|이름|설명|
|----------|-----------------|
|[COleObjectFactory::GetLicenseKey](#getlicensekey)|컨트롤의 DLL에서 고유 키를 요청합니다.|
|[COleObjectFactory::OnCreateObject](#oncreateobject)|이 팩터리의 형식의 새 개체를 만들기 위해 프레임 워크에서 호출 됩니다.|
|[COleObjectFactory::VerifyLicenseKey](#verifylicensekey)|컨트롤에 포함 된 키 컨테이너에 포함 된 키와 일치 하는지 확인 합니다.|
|[COleObjectFactory::VerifyUserLicense](#verifyuserlicense)|컨트롤이 디자인 타임에 사용 하도록 허가 되어 있는지 확인 합니다.|

## <a name="remarks"></a>설명

`COleObjectFactory` 클래스에 다음 기능을 수행 하는 것에 대 한 멤버 함수:

- 개체의 등록을 관리 합니다.

- 개체 실행 하 고 메시지를 받을 준비가 OLE를 알려 주는 런타임에 등록 뿐만 아니라 OLE 시스템 등록을 업데이트 합니다.

- 개발자에 게 사용이 허가 된에 디자인 타임 및 런타임에 사용이 허가 된 응용 프로그램에 컨트롤의 사용을 제한 하 여 라이선스를 적용 합니다.

- OLE 시스템 레지스트리를 사용 하 여 컨트롤 개체 팩터리를 등록 합니다.

개체 만들기에 대 한 자세한 내용은 문서를 참조 하세요 [데이터 개체 및 데이터 소스 (OLE)](../../mfc/data-objects-and-data-sources-ole.md) 고 [데이터 개체 및 데이터 소스: 생성 및 소멸](../../mfc/data-objects-and-data-sources-creation-and-destruction.md)합니다. 등록에 대 한 자세한 문서를 참조 [등록](../../mfc/registration.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`COleObjectFactory`

## <a name="requirements"></a>요구 사항

**헤더:** afxdisp.h

##  <a name="coleobjectfactory"></a>  COleObjectFactory::COleObjectFactory

생성 된 `COleObjectFactory` 팩터리 목록에 추가 하는 개체로 등록 되지 않은 개체 팩터리를 초기화 합니다.

```
COleObjectFactory(
    REFCLSID clsid,
    CRuntimeClass* pRuntimeClass,
    BOOL bMultiInstance,
    LPCTSTR lpszProgID);

COleObjectFactory(
    REFCLSID clsid,
    CRuntimeClass* pRuntimeClass,
    BOOL bMultiInstance,
    int nFlags,
    LPCTSTR lpszProgID);
```

### <a name="parameters"></a>매개 변수

*clsid*<br/>
이 개체 팩터리 OLE 클래스 ID에 대 한 참조를 나타냅니다.

*pRuntimeClass*<br/>
런타임 클래스에 대 한 포인터를 C++ 개체를이 팩터리를 만들 수 있습니다.

*bMultiInstance*<br/>
단일 인스턴스 응용 프로그램의 여러 인스턴스화를 지원할 수 있는지 여부를 나타냅니다. TRUE 이면 개체를 만드는 각 요청에 대 한 응용 프로그램의 여러 인스턴스가 시작 됩니다.

*nFlags*<br/>
다음 플래그 중 하나 이상 포함 되어 있습니다.

- `afxRegDefault` 스레딩 모델이 ThreadingModel로 설정 아파트 =.

- `afxRegInsertable` 에 표시 하도록 허용 합니다 **개체 삽입** OLE 개체에 대 한 대화 상자.

- `afxRegApartmentThreading` ThreadingModel 레지스트리의 스레딩 모델을 설정 하는 아파트 =.

- `afxRegFreeThreading` ThreadingModel 레지스트리의 스레딩 모델을 설정 합니다. 무료 =.

   두 플래그를 조합할 수 있습니다 `afxRegApartmentThreading` 및 `afxRegFreeThreading` ThreadingModel 설정 = Both입니다. 참조 [InprocServer32](/windows/desktop/com/inprocserver32) 스레딩 모델 등록 대 한 자세한 내용은 Windows SDK에 있습니다.

*lpszProgID*<br/>
"Microsoft Excel입니다."와 같은 구두 프로그램 식별자를 포함 하는 문자열에 대 한 포인터

### <a name="remarks"></a>설명

그러나 개체를 사용 하려면 등록 해야 합니다.

자세한 내용은 [CLSID 키](/windows/desktop/com/clsid-key-hklm) Windows SDK에 있습니다.

##  <a name="getclassid"></a>  COleObjectFactory::GetClassID

이 팩터리를 나타내는 OLE 클래스 ID에 대 한 참조를 반환 합니다.

```
REFCLSID GetClassID() const;
```

### <a name="return-value"></a>반환 값

이 팩터리가 OLE 클래스 ID에 대 한 참조를 나타냅니다.

### <a name="remarks"></a>설명

자세한 내용은 [CLSID 키](/windows/desktop/com/clsid-key-hklm) Windows SDK에 있습니다.

##  <a name="getlicensekey"></a>  COleObjectFactory::GetLicenseKey

컨트롤의 DLL에서 고유한 라이선스 키를 요청 하 고 가리키는 BSTR에 저장 *pbstrKey*합니다.

```
virtual BOOL GetLicenseKey(
    DWORD dwReserved,
    BSTR* pbstrKey);
```

### <a name="parameters"></a>매개 변수

*dwReserved*<br/>
나중에 사용하기 위해 예약되어 있습니다.

*pbstrKey*<br/>
라이선스 키를 저장 하는 BSTR에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

라이선스 키 문자열; NULL이 아닌 경우 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 함수의 기본 구현은 0을 반환 하 고 BSTR 아무 것도 저장 합니다. MFC ActiveX 컨트롤을 사용 하 여 프로젝트를 만드는 경우 컨트롤은 컨트롤의 라이선스 키를 검색 하는 재정의 제공 합니다.

##  <a name="islicensevalid"></a>  COleObjectFactory::IsLicenseValid

컨트롤의 라이선스를 유효한 인지 확인 합니다.

```
BOOL IsLicenseValid();
```

### <a name="return-value"></a>반환 값

TRUE 이면 successul; 그렇지 않으면 false입니다.

##  <a name="isregistered"></a>  COleObjectFactory::IsRegistered

팩터리 OLE 시스템 Dll 사용 하 여 등록 된 경우 0이 아닌 값을 반환 합니다.

```
virtual BOOL IsRegistered() const;
```

### <a name="return-value"></a>반환 값

팩터리를 등록 되 면 0이 아닌 값 그렇지 않으면 0입니다.

##  <a name="oncreateobject"></a>  COleObjectFactory::OnCreateObject

새 개체를 만드는 프레임 워크에서 호출 됩니다.

```
virtual CCmdTarget* OnCreateObject();
```

### <a name="return-value"></a>반환 값

만든된 개체에 대 한 포인터입니다. 실패 한 경우 메모리 예외가 발생할 수 있습니다.

### <a name="remarks"></a>설명

이외의 다른 항목에서 개체를 만드는 데이 함수를 재정의 합니다 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 생성자에 전달 합니다.

##  <a name="register"></a>  COleObjectFactory::Register

OLE 시스템 Dll 사용 하 여이 개체 팩터리를 등록합니다.

```
virtual BOOL Register();
```

### <a name="return-value"></a>반환 값

팩터리를 성공적으로 등록 되 면 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 함수는 일반적으로 호출한 [CWinApp::InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) 응용 프로그램이 시작 될 때입니다.

##  <a name="registerall"></a>  COleObjectFactory::RegisterAll

OLE 시스템 Dll 사용 하 여 모든 응용 프로그램의 개체 팩터리를 등록합니다.

```
static BOOL PASCAL RegisterAll();
```

### <a name="return-value"></a>반환 값

팩터리; 성공적으로 등록 한 경우 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 함수는 일반적으로 호출한 [CWinApp::InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) 응용 프로그램이 시작 될 때입니다.

##  <a name="revoke"></a>  COleObjectFactory::Revoke

OLE 시스템 Dll 사용 하 여이 개체 팩터리의이 등록을 취소합니다.

```
void Revoke();
```

### <a name="remarks"></a>설명

응용 프로그램을 종료 하기 전에이 함수를 자동으로 호출 하는 프레임 워크입니다. 필요한 경우 재정의에서 호출할 [CWinApp::ExitInstance](../../mfc/reference/cwinapp-class.md#exitinstance)합니다.

##  <a name="revokeall"></a>  COleObjectFactory::RevokeAll

모든 OLE 시스템 Dll 사용 하 여 응용 프로그램의 개체 팩터리 등록 취소합니다.

```
static void PASCAL RevokeAll();
```

### <a name="remarks"></a>설명

응용 프로그램을 종료 하기 전에이 함수를 자동으로 호출 하는 프레임 워크입니다. 필요한 경우 재정의에서 호출할 [CWinApp::ExitInstance](../../mfc/reference/cwinapp-class.md#exitinstance)합니다.

##  <a name="unregisterall"></a>  COleObjectFactory::UnregisterAll

모든 응용 프로그램의 개체 팩터리를 등록 취소합니다.

```
static BOOL PASCAL UnregisterAll();
```

### <a name="return-value"></a>반환 값

성공하면 TRUE이고, 실패하면 FALSE입니다.

##  <a name="updateregistry"></a>  COleObjectFactory::UpdateRegistry

OLE 시스템 레지스트리를 사용 하 여 모든 응용 프로그램의 개체 팩터리를 등록합니다.

```
void UpdateRegistry(LPCTSTR lpszProgID = NULL);
virtual BOOL UpdateRegistry(BOOL bRegister);
```

### <a name="parameters"></a>매개 변수

*lpszProgID*<br/>
"Excel.Document.5."와 같은 사람이 읽을 수 있는 프로그램 식별자를 포함 하는 문자열에 대 한 포인터

*bRegister*<br/>
컨트롤 클래스의 개체 팩터리 등록할 수 있는지 여부를 결정 합니다.

### <a name="remarks"></a>설명

이 함수에 대 한 두 가지 형식 중 대 한 간략 한 논의 수행합니다.

- **UpdateRegistry (** `lpszProgID` **)** OLE 시스템 레지스트리를 사용 하 여이 개체 팩터리를 등록 합니다. 이 함수는 일반적으로 호출한 [CWinApp::InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) 응용 프로그램이 시작 될 때입니다.

- **UpdateRegistry (** `bRegister` **)** 함수의이 폼은 재정의할 수 있습니다. 하는 경우 *b 등록 하십시오* 가 TRUE 이면이 함수 레지스터 시스템 레지스트리를 사용 하 여 컨트롤 클래스입니다. 그렇지 않으면 클래스 등록 취소합니다.

   MFC ActiveX 컨트롤을 사용 하 여 프로젝트를 만드는 경우 컨트롤은이 순수 가상 함수 재정의 제공 합니다.

##  <a name="updateregistryall"></a>  COleObjectFactory::UpdateRegistryAll

OLE 시스템 레지스트리를 사용 하 여 모든 응용 프로그램의 개체 팩터리를 등록합니다.

```
static BOOL PASCAL UpdateRegistryAll(BOOL bRegister = TRUE);
```

### <a name="parameters"></a>매개 변수

*bRegister*<br/>
컨트롤 클래스의 개체 팩터리 등록할 수 있는지 여부를 결정 합니다.

### <a name="return-value"></a>반환 값

0이 아닌 팩터리 성공적으로 업데이트 됩니다. 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 함수는 일반적으로 호출한 [CWinApp::InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) 응용 프로그램이 시작 될 때입니다.

##  <a name="verifylicensekey"></a>  COleObjectFactory::VerifyLicenseKey

컨테이너는 OLE 컨트롤을 사용 하도록 라이선스를 갖고 있는지 확인 합니다.

```
virtual BOOL VerifyLicenseKey(BSTR bstrKey);
```

### <a name="parameters"></a>매개 변수

*bstrKey*<br/>
라이선스 문자열의 컨테이너의 버전을 저장 하는 BSTR입니다.

### <a name="return-value"></a>반환 값

런타임 라이선스를 잘못 되었습니다. 0이 아닌 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

기본 버전을 호출 하 여 [GetLicenseKey](#getlicensekey) 컨트롤의 복사본을 가져오려면 라이선스 문자열 및 문자열 비교 *bstrKey*합니다. 반환 값을 0이 아닌 두 문자열이 일치 하는 경우 그렇지 않으면 0을 반환 합니다.

라이선스의 사용자 지정된 확인을 제공 하려면이 함수를 재정의할 수 있습니다.

함수 [VerifyUserLicense](#verifyuserlicense) 디자인 타임 라이선스를 확인 합니다.

##  <a name="verifyuserlicense"></a>  COleObjectFactory::VerifyUserLicense

OLE 컨트롤에 대 한 디자인 타임 라이선스를 확인합니다.

```
virtual BOOL VerifyUserLicense();
```

### <a name="return-value"></a>반환 값

디자인 타임 라이선스를 잘못 되었습니다. 0이 아닌 그렇지 않으면 0입니다.

## <a name="see-also"></a>참고자료

[CCmdTarget 클래스](../../mfc/reference/ccmdtarget-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[COleTemplateServer 클래스](../../mfc/reference/coletemplateserver-class.md)
