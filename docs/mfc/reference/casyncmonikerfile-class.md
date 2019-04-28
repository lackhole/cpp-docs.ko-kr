---
title: CAsyncMonikerFile 클래스
ms.date: 11/04/2016
f1_keywords:
- CAsyncMonikerFile
- AFXOLE/CAsyncMonikerFile
- AFXOLE/CAsyncMonikerFile::CAsyncMonikerFile
- AFXOLE/CAsyncMonikerFile::Close
- AFXOLE/CAsyncMonikerFile::GetBinding
- AFXOLE/CAsyncMonikerFile::GetFormatEtc
- AFXOLE/CAsyncMonikerFile::Open
- AFXOLE/CAsyncMonikerFile::CreateBindStatusCallback
- AFXOLE/CAsyncMonikerFile::GetBindInfo
- AFXOLE/CAsyncMonikerFile::GetPriority
- AFXOLE/CAsyncMonikerFile::OnDataAvailable
- AFXOLE/CAsyncMonikerFile::OnLowResource
- AFXOLE/CAsyncMonikerFile::OnProgress
- AFXOLE/CAsyncMonikerFile::OnStartBinding
- AFXOLE/CAsyncMonikerFile::OnStopBinding
helpviewer_keywords:
- CAsyncMonikerFile [MFC], CAsyncMonikerFile
- CAsyncMonikerFile [MFC], Close
- CAsyncMonikerFile [MFC], GetBinding
- CAsyncMonikerFile [MFC], GetFormatEtc
- CAsyncMonikerFile [MFC], Open
- CAsyncMonikerFile [MFC], CreateBindStatusCallback
- CAsyncMonikerFile [MFC], GetBindInfo
- CAsyncMonikerFile [MFC], GetPriority
- CAsyncMonikerFile [MFC], OnDataAvailable
- CAsyncMonikerFile [MFC], OnLowResource
- CAsyncMonikerFile [MFC], OnProgress
- CAsyncMonikerFile [MFC], OnStartBinding
- CAsyncMonikerFile [MFC], OnStopBinding
ms.assetid: 17378b66-a49a-4b67-88e3-7756ad26a2fc
ms.openlocfilehash: b86cba0c2e8f7991902a552d404355d6c1474138
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62237864"
---
# <a name="casyncmonikerfile-class"></a>CAsyncMonikerFile 클래스

ActiveX 컨트롤(이전의 OLE 컨트롤)에서 비동기 모니커를 사용할 수 있도록 기능을 제공합니다.

## <a name="syntax"></a>구문

```
class CAsyncMonikerFile : public CMonikerFile
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CAsyncMonikerFile::CAsyncMonikerFile](#casyncmonikerfile)|`CAsyncMonikerFile` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CAsyncMonikerFile::Close](#close)|페이지를 닫고 모든 리소스를 해제 합니다.|
|[CAsyncMonikerFile::GetBinding](#getbinding)|바인딩 비동기 전송에 대 한 포인터를 검색 합니다.|
|[CAsyncMonikerFile::GetFormatEtc](#getformatetc)|스트림의 데이터의 형식을 검색합니다.|
|[CAsyncMonikerFile::Open](#open)|비동기적으로 파일을 엽니다.|

### <a name="protected-methods"></a>Protected 메서드

|이름|설명|
|----------|-----------------|
|[CAsyncMonikerFile::CreateBindStatusCallback](#createbindstatuscallback)|구현 하는 COM 개체를 만듭니다 `IBindStatusCallback`합니다.|
|[CAsyncMonikerFile::GetBindInfo](#getbindinfo)|만들려는 바인딩 종류에 대 한 요청 정보 OLE 시스템 라이브러리에서 호출 됩니다.|
|[CAsyncMonikerFile::GetPriority](#getpriority)|바인딩의 우선 순위를 가져오려고 OLE 시스템 라이브러리에서 호출 됩니다.|
|[CAsyncMonikerFile::OnDataAvailable](#ondataavailable)|아직 클라이언트에 비동기 바인딩 작업 중에 데이터를 제공 하기 위해 호출 됩니다.|
|[CAsyncMonikerFile::OnLowResource](#onlowresource)|리소스가 부족 한지 때 호출 됩니다.|
|[CAsyncMonikerFile::OnProgress](#onprogress)|데이터 다운로드 프로세스에 대 한 진행 상황을 나타내기 위해 호출 합니다.|
|[CAsyncMonikerFile::OnStartBinding](#onstartbinding)|바인딩 시작 될 때 호출 됩니다.|
|[CAsyncMonikerFile::OnStopBinding](#onstopbinding)|비동기 전송 중지 되 면 호출 됩니다.|

## <a name="remarks"></a>설명

파생 된 [CMonikerFile](../../mfc/reference/cmonikerfile-class.md)를 차례로에서 파생 된 [COleStreamFile](../../mfc/reference/colestreamfile-class.md), `CAsyncMonikerFile` 사용 하는 [IMoniker](/windows/desktop/api/objidl/nn-objidl-imoniker) 모든 데이터 스트림에 액세스 하는 인터페이스 비동기적으로 URL에서 파일을 비동기적으로 로드를 포함 합니다. 파일에는 ActiveX 컨트롤의 데이터 경로 속성 일 수 있습니다.

비동기 모니커는 파일을 전송 하는 동안 응답성이 뛰어난 사용자 인터페이스를 제공 ActiveX 컨트롤 그리고 인터넷 사용 응용 프로그램에 주로 사용 됩니다. 사용 하는 것이 대표적인 예로 [CDataPathProperty](../../mfc/reference/cdatapathproperty-class.md) ActiveX 컨트롤에 대 한 비동기 속성을 제공 합니다. `CDataPathProperty` 개체 반복적으로 긴 속성 exchange 과정 동안 새 데이터의 가용성을 나타내기 위해 콜백을 받습니다.

인터넷 응용 프로그램에서 비동기 모니커 및 ActiveX 컨트롤을 사용 하는 방법에 대 한 자세한 내용은 다음 문서를 참조 하세요.

- [인터넷 첫 번째 단계: 비동기 모니커](../../mfc/asynchronous-monikers-on-the-internet.md)

- [인터넷 첫 번째 단계: ActiveX 컨트롤](../../mfc/activex-controls-on-the-internet.md)

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

[COleStreamFile](../../mfc/reference/colestreamfile-class.md)

[CMonikerFile](../../mfc/reference/cmonikerfile-class.md)

`CAsyncMonikerFile`

## <a name="requirements"></a>요구 사항

**헤더:** afxole.h

##  <a name="casyncmonikerfile"></a>  CAsyncMonikerFile::CAsyncMonikerFile

`CAsyncMonikerFile` 개체를 생성합니다.

```
CAsyncMonikerFile();
```

### <a name="remarks"></a>설명

문제가 발생 하지 않는 `IBindHost` 인터페이스입니다. `IBindHost` 제공 하는 경우에 사용 되는 `Open` 멤버 함수입니다.

에 대 한 설명은 `IBindHost` 인터페이스, Windows SDK를 참조 하세요.

##  <a name="close"></a>  CAsyncMonikerFile::Close

닫고 모든 리소스를 해제 하려면이 함수를 호출 합니다.

```
virtual void Close();
```

### <a name="remarks"></a>설명

아직 열지 않은 또는 이미 닫힌 파일에서 호출할 수 있습니다.

##  <a name="createbindstatuscallback"></a>  CAsyncMonikerFile::CreateBindStatusCallback

구현 하는 COM 개체를 만듭니다 `IBindStatusCallback`합니다.

```
virtual IUnknown* CreateBindStatusCallback(IUnknown* pUnkControlling);
```

### <a name="parameters"></a>매개 변수

*pUnkControlling*<br/>
제어 알 수 없음에 대 한 포인터 (외부 `IUnknown`) 이거나 집계 사용 되지 않는 경우 NULL입니다.

### <a name="return-value"></a>반환 값

하는 경우 *pUnkControlling* NULL이 아니면 내부 예외에 대 한 포인터를 반환 `IUnknown` 지원 하기 위해 새 COM 개체 `IBindStatusCallback`합니다. 하는 경우 `pUnkControlling` 가 null 인 경우 함수에 대 한 포인터를 반환 합니다.는 `IUnknown` 지원 하기 위해 새 COM 개체 `IBindStatusCallback`합니다.

### <a name="remarks"></a>설명

`CAsyncMonikerFile` 구현 하는 COM 개체가 필요 `IBindStatusCallback`합니다. MFC 이러한 개체를 구현 하 고 집계할 수 있는 것입니다. 재정의할 수 있습니다 `CreateBindStatusCallback` 고유한 COM 개체를 반환 합니다. COM 개체를 호출 하 여 MFC 구현을 집계할 수 `CreateBindStatusCallback` COM 개체의 알 수 없는 제어를 사용 하 여 합니다. COM 개체를 사용 하 여 구현 된 `CCmdTarget` COM 지원을 제어 알 수 없는 사용을 검색할 수 있습니다 `CCmdTarget::GetControllingUnknown`합니다.

또는 COM 개체를 호출 하 여 MFC의 구현에 위임할 수 `CreateBindStatusCallback( NULL )`입니다.

[CAsyncMonikerFile::Open](#open) 호출 `CreateBindStatusCallback`합니다.

비동기 모니커 및 비동기 바인딩에 대 한 자세한 내용은 참조는 [IBindStatusCallback](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/ms775060\(v=vs.85\)) 인터페이스 및 [비동기 바인딩 방법 및 저장소](/windows/desktop/Stg/how-asynchronous-binding-and-storage-work)합니다. 집계의 논의 참조 하세요 [집계](/windows/desktop/com/aggregation)합니다. Windows SDK의 모든 세 가지 항목은입니다.

##  <a name="getbindinfo"></a>  CAsyncMonikerFile::GetBindInfo

바인딩할 좋 어떻게 비동기 모니커를 구별 하는 비동기 모니커 클라이언트에서 호출 됩니다.

```
virtual DWORD GetBindInfo() const;
```

### <a name="return-value"></a>반환 값

에 대 한 설정을 검색 `IBindStatusCallBack`합니다. 에 대 한 설명은 `IBindStatusCallback` 인터페이스, Windows SDK를 참조 하세요.

### <a name="remarks"></a>설명

기본 구현은 저장 매체 (스트림)를 사용 하 고 데이터 밀어넣기 모델을 사용 하 여 비동기가 되도록 바인딩을 설정 합니다. 바인딩의 동작을 변경 하려는 경우이 함수를 재정의 합니다.

이 작업을 수행 하는 한 가지 이유는 데이터 푸시 모델 대신 데이터 끌어오기 모델을 사용 하 여 바인딩할 것입니다. 데이터 끌어오기 모델에서 클라이언트 바인딩 작업을 구동 하 고 모니커를 읽을 때 클라이언트에 데이터만 제공 합니다. 데이터 푸시 모델에서 모니커 비동기 바인딩 작업을 구동 하 고 지속적으로 새 데이터를 사용할 때마다 클라이언트를에 알립니다.

##  <a name="getbinding"></a>  CAsyncMonikerFile::GetBinding

바인딩 비동기 전송에 대 한 포인터를 검색 하려면이 함수를 호출 합니다.

```
IBinding* GetBinding() const;
```

### <a name="return-value"></a>반환 값

에 대 한 포인터를 `IBinding` 비동기 전송이 시작 될 때 제공 하는 인터페이스입니다. 어떤 이유로 든 전송의 경우 NULL을 반환을 비동기적으로 만들 수 없습니다.

### <a name="remarks"></a>설명

데이터 전송 프로세스를 통해 제어할 수 있게이 `IBinding` 연동, 예를 들어 `IBinding::Abort`를 `IBinding::Pause`, 및 `IBinding::Resume`합니다.

에 대 한 설명은 `IBinding` 인터페이스, Windows SDK를 참조 하세요.

##  <a name="getformatetc"></a>  CAsyncMonikerFile::GetFormatEtc

스트림의 데이터의 형식을 검색 하려면이 함수를 호출 합니다.

```
FORMATETC* GetFormatEtc() const;
```

### <a name="return-value"></a>반환 값

Windows 구조에 대 한 포인터 [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) 현재 열린된 스트림에 대 한 합니다. 모니커 바인딩되지 않은, 비동기, 없는 경우 또는 비동기 작업이 아직 시작 되지 않은 경우 NULL을 반환 합니다.

##  <a name="getpriority"></a>  CAsyncMonikerFile::GetPriority

바인딩 프로세스 스레드에 대해 지정 되는 바인딩 작업에 대 한 우선 순위를 수신 하기 시작 하는 대로 비동기 모니커는 클라이언트에서 호출 합니다.

```
virtual LONG GetPriority() const;
```

### <a name="return-value"></a>반환 값

우선 순위는 비동기 전송을 수행 됩니다. 표준 스레드 우선 순위 플래그 중 하나입니다. THREAD_PRIORITY_ABOVE_NORMAL THREAD_PRIORITY_BELOW_NORMAL, THREAD_PRIORITY_HIGHEST, THREAD_PRIORITY_IDLE, THREAD_PRIORITY_LOWEST, THREAD_PRIORITY_NORMAL, 및 THREAD_PRIORITY_TIME_CRITICAL 합니다. Windows 함수를 참조 하십시오 [SetThreadPriority](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-setthreadpriority) 이러한 값에 대 한 합니다.

### <a name="remarks"></a>설명

`GetPriority` 해야 하지 직접 호출할 수 있습니다. THREAD_PRIORITY_NORMAL 기본 구현에 의해 반환 됩니다.

##  <a name="ondataavailable"></a>  CAsyncMonikerFile::OnDataAvailable

호출 하는 비동기 모니커 `OnDataAvailable` 를 사용할 수 있는 클라이언트에 데이터를 제공, 비동기 중 바인딩할 작업 합니다.

```
virtual void OnDataAvailable(DWORD dwSize, DWORD bscfFlag);
```

### <a name="parameters"></a>매개 변수

*dwSize*<br/>
바인딩의 사용할 수 있는 데이터의 누적 양 (메가바이트)입니다. 데이터의 양을 해당 작업과 관련 되지 않거나 특정 양이 없는 나왔을 있는지를 나타내는 0이 될 수 있습니다.

*bscfFlag*<br/>
BSCF 열거형 값입니다. 다음 값 중 하나 이상의 수 있습니다.

- 첫 번째 호출을 식별 하는 BSCF_FIRSTDATANOTIFICATION `OnDataAvailable` 지정 된 바인딩 작업에 대 한 합니다.

- 에 대 한 중간 호출을 식별 하는 BSCF_INTERMEDIATEDATANOTIFICATION `OnDataAvailable` 바인딩 작업에 대 한 합니다.

- 마지막 호출을 식별 하는 BSCF_LASTDATANOTIFICATION `OnDataAvailable` 바인딩 작업에 대 한 합니다.

### <a name="remarks"></a>설명

이 함수의 기본 구현은 아무 작업도 수행하지 않습니다. 샘플 구현에 대 한 다음 예제를 참조 하세요.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWinInet#5](../../mfc/codesnippet/cpp/casyncmonikerfile-class_1.cpp)]

##  <a name="onlowresource"></a>  CAsyncMonikerFile::OnLowResource

리소스가 부족 한 경우 모니커에서 호출 됩니다.

```
virtual void OnLowResource();
```

### <a name="remarks"></a>설명

기본 구현 호출 `GetBinding( )-> Abort( )`합니다.

##  <a name="onprogress"></a>  CAsyncMonikerFile::OnProgress

반복 해 서, 일반적으로 시간이 오래 걸리는 작업을 하는 동안 적절 한 간격으로이 바인딩 작업의 현재 진행률을 나타내는 모니커에서 호출 됩니다.

```
virtual void OnProgress(
    ULONG ulProgress,
    ULONG ulProgressMax,
    ULONG ulStatusCode,
    LPCTSTR szStatusText);
```

### <a name="parameters"></a>매개 변수

*ulProgress*<br/>
에 표시 된 예상된 최대값을 기준으로 바인딩 작업의 현재 진행률을 나타내는 *ulProgressMax*합니다.

*ulProgressMax*<br/>
예상된 최대값을 나타내는 *ulProgress* 에 대 한 호출 기간 동안 `OnProgress` 이 작업에 대 한 합니다.

*ulStatusCode*<br/>
바인딩 작업의 진행률에 대 한 추가 정보를 제공합니다. 유효한 값을 가져옵니다는 `BINDSTATUS` 열거형입니다. 가능한 값에 대 한 설명을 참조 하세요.

*szStatusText*<br/>
값에 따라 현재 진행 상태에 대 한 정보 *ulStatusCode*합니다. 가능한 값에 대 한 설명을 참조 하세요.

### <a name="remarks"></a>설명

가능한 값 *ulStatusCode* (및 *szStatusText* 각 값에 대해) 됩니다.

|||
|-|-|
|BINDSTATUS_FINDINGRESOURCE  |바인딩 작업에 바인딩되는 저장소를 포함 하는 리소스를 찾는 것입니다. 합니다 *szStatusText* 검색 중인 리소스의 표시 이름을 제공 (예: "www.microsoft.com")에 대 한 합니다.  |
|BINDSTATUS_CONNECTING  |바인딩 작업에 바인딩되는 저장소를 포함 하는 리소스에 연결 됩니다. 합니다 *szStatusText* (예: IP 주소)에 연결 중인 리소스의 표시 이름을 제공 합니다.  |
|BINDSTATUS_SENDINGREQUEST|바인딩 작업은 개체 또는 저장소에 바인딩되어 있는 요청입니다. 합니다 *szStatusText* 개체 (예: 파일 이름)의 표시 이름을 제공 합니다.|
|BINDSTATUS_REDIRECTING  |바인딩 작업을 다른 데이터 위치로 리디렉션 되었습니다. 합니다 *szStatusText* 새 데이터 위치로의 표시 이름을 제공 합니다.  |
|BINDSTATUS_USINGCACHEDCOPY  |바인딩 작업은 캐시 된 복사본에서 요청 된 개체 또는 저장소를 검색 합니다. 합니다 *szStatusText* NULL입니다.  |
|BINDSTATUS_BEGINDOWNLOADDATA  |바인딩 작업에 바인딩되는 저장소를 받기 시작 했습니다. 합니다 *szStatusText* 데이터 위치로의 표시 이름을 제공 합니다.|
|BINDSTATUS_DOWNLOADINGDATA  |바인딩 작업 개체 또는 저장소에 바인딩되어 있는 수신을 계속 합니다. 합니다 *szStatusText* 데이터 위치로의 표시 이름을 제공 합니다.  |
|BINDSTATUS_ENDDOWNLOADDATA  |개체 또는 저장소에 바인딩되는 수신 바인딩 작업을 완료 했습니다. 합니다 *szStatusText* 데이터 위치로의 표시 이름을 제공 합니다.  |
|BINDSTATUS_CLASSIDAVAILABLE  |에 바인딩되는 개체의 인스턴스를 방금 만들어야 합니다. 합니다 *szStatusText* 원하는 경우 클라이언트 바인딩 작업을 취소할 수 있는 기회를 허용 하는 문자열 형식으로 새 개체의 CLSID를 제공 합니다.  |

##  <a name="onstartbinding"></a>  CAsyncMonikerFile::OnStartBinding

바인딩 시작 될 때 작업을 수행 하려면 파생된 클래스에서이 함수를 재정의 합니다.

```
virtual void OnStartBinding();
```

### <a name="remarks"></a>설명

이 함수는 모니커가 다시 호출 됩니다. 기본 구현은 아무 작업도 수행하지 않습니다.

##  <a name="onstopbinding"></a>  CAsyncMonikerFile::OnStopBinding

모니커 바인딩 작업의 끝에서 호출 됩니다.

```
virtual void OnStopBinding(HRESULT hresult, LPCTSTR szError);
```

### <a name="parameters"></a>매개 변수

*hresult*<br/>
HRESULT는 오류 또는 경고 값입니다.

*szErrort*<br/>
오류를 설명 하는 문자열입니다.

### <a name="remarks"></a>설명

전송이 중지 되 면 작업을 수행 하려면이 함수를 재정의 합니다. 기본적으로 함수 해제 `IBinding`합니다.

에 대 한 설명은 `IBinding` 인터페이스, Windows SDK를 참조 하세요.

##  <a name="open"></a>  CAsyncMonikerFile::Open

비동기적으로 파일을 열려면이 멤버 함수를 호출 합니다.

```
virtual BOOL Open(
    LPCTSTR lpszURL,
    CFileException* pError = NULL);

virtual BOOL Open(
    IMoniker* pMoniker,
    CFileException* pError = NULL);

virtual BOOL Open(
    LPCTSTR lpszURL,
    IBindHost* pBindHost,
    CFileException* pError = NULL);

virtual BOOL Open(
    IMoniker* pMoniker,
    IBindHost* pBindHost,
    CFileException* pError = NULL);

virtual BOOL Open(
    LPCTSTR lpszURL,
    IServiceProvider* pServiceProvider,
    CFileException* pError = NULL);

virtual BOOL Open(
    IMoniker* pMoniker,
    IServiceProvider* pServiceProvider,
    CFileException* pError = NULL);

virtual BOOL Open(
    LPCTSTR lpszURL,
    IUnknown* pUnknown,
    CFileException* pError = NULL);

virtual BOOL Open(
    IMoniker* pMoniker,
    IUnknown* pUnknown,
    CFileException* pError = NULL);
```

### <a name="parameters"></a>매개 변수

*lpszURL*<br/>
비동기적으로 열 파일에 대 한 포인터입니다. 모든 유효한 URL 또는 파일 이름 파일 수 있습니다.

*pError*<br/>
파일 예외에 대 한 포인터입니다. 오류가 발생 한 원인에 설정 됩니다.

*pMoniker*<br/>
비동기 모니커 인터페이스에 대 한 포인터 `IMoniker`를 정확 하 게 되는 모니커를 사용 하 여 검색할 수 있는 문서의 모니커를 조합 `IOleClientSite::GetMoniker(OLEWHICHMK_CONTAINER)`, 및 경로 이름에서 생성 하는 모니커입니다. 컨트롤을 바인딩하려는 경우이 모니커를 사용할 수 있지만 컨트롤을 저장 해야 하는 모니커 아닙니다. 합니다.

*pBindHost*<br/>
에 대 한 포인터를 `IBindHost` 잠재적으로 상대 경로 이름에서 모니커를 만드는 데 사용할 수 있는 인터페이스입니다. 바인딩 호스트 유효 하지 않거나 모니커를 제공 하지 않습니다, 호출 기본값으로 `Open(lpszFileName,pError)`합니다. 에 대 한 설명은 `IBindHost` 인터페이스, Windows SDK를 참조 하세요.

*pServiceProvider*<br/>
에 대 한 포인터를 `IServiceProvider` 인터페이스입니다. 서비스 공급자가 잘못 되었거나 서비스를 제공 하지 못하면 경우 `IBindHost`, 기본값은 호출 `Open(lpszFileName,pError)`합니다.

*pUnknown*<br/>
에 대 한 포인터를 `IUnknown` 인터페이스입니다. 하는 경우 `IServiceProvider` 발견 되 면에 대 한 함수 쿼리 `IBindHost`합니다. 서비스 공급자가 잘못 되었거나 서비스를 제공 하지 못하면 경우 `IBindHost`, 기본값은 호출 `Open(lpszFileName,pError)`합니다.

### <a name="return-value"></a>반환 값

파일이 성공적으로 열릴 경우 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 호출은 바인딩 프로세스를 시작합니다.

URL 또는 파일 이름을 사용할 수는 *lpszURL* 매개 변수입니다. 예를 들어:

[!code-cpp[NVC_MFCWinInet#6](../../mfc/codesnippet/cpp/casyncmonikerfile-class_2.cpp)]

\- 또는 -

[!code-cpp[NVC_MFCWinInet#7](../../mfc/codesnippet/cpp/casyncmonikerfile-class_3.cpp)]

## <a name="see-also"></a>참고자료

[CMonikerFile 클래스](../../mfc/reference/cmonikerfile-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CMonikerFile 클래스](../../mfc/reference/cmonikerfile-class.md)<br/>
[CDataPathProperty 클래스](../../mfc/reference/cdatapathproperty-class.md)
