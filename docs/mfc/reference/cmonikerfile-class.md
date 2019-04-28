---
title: CMonikerFile 클래스
ms.date: 11/04/2016
f1_keywords:
- CMonikerFile
- AFXOLE/CMonikerFile
- AFXOLE/CMonikerFile::CMonikerFile
- AFXOLE/CMonikerFile::Close
- AFXOLE/CMonikerFile::Detach
- AFXOLE/CMonikerFile::GetMoniker
- AFXOLE/CMonikerFile::Open
- AFXOLE/CMonikerFile::CreateBindContext
helpviewer_keywords:
- CMonikerFile [MFC], CMonikerFile
- CMonikerFile [MFC], Close
- CMonikerFile [MFC], Detach
- CMonikerFile [MFC], GetMoniker
- CMonikerFile [MFC], Open
- CMonikerFile [MFC], CreateBindContext
ms.assetid: 87be5966-f4f7-4235-bce2-1fa39e9417de
ms.openlocfilehash: ecffdb3a6f44f60004cf4f039bdab9c98e212ce1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62338040"
---
# <a name="cmonikerfile-class"></a>CMonikerFile 클래스

데이터 스트림을 나타냅니다 ( [IStream](/windows/desktop/api/objidl/nn-objidl-istream))로 명명 한 [IMoniker](/windows/desktop/api/objidl/nn-objidl-imoniker)합니다.

## <a name="syntax"></a>구문

```
class CMonikerFile : public COleStreamFile
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CMonikerFile::CMonikerFile](#cmonikerfile)|`CMonikerFile` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CMonikerFile::Close](#close)|분리 및 스트림을 해제 하 고 모니커를 해제 합니다.|
|[CMonikerFile::Detach](#detach)|분리 된 `IMoniker` 이 `CMonikerFile` 개체입니다.|
|[CMonikerFile::GetMoniker](#getmoniker)|현재 모니커를 반환합니다.|
|[CMonikerFile::Open](#open)|한 스트림을 가져올 수 지정 된 파일을 엽니다.|

### <a name="protected-methods"></a>Protected 메서드

|이름|설명|
|----------|-----------------|
|[CMonikerFile::CreateBindContext](#createbindcontext)|바인드 컨텍스트에 가져옵니다 또는 초기화 하는 기본 바인딩 컨텍스트를 만듭니다.|

## <a name="remarks"></a>설명

모니커를 사용 하면 파일에 대 한 경로 이름 마찬가지로 정보가 있습니다. 모니커 개체의 경우 `IMoniker` 인터페이스 파일을 실제로 있는 위치에 대 한 기타 관련 정보를 하지 않고도 식별된 된 파일에 대 한 액세스를 가져올 수 있습니다.

파생 된 `COleStreamFile`, `CMonikerFile` 모니커를 수 있도록 문자열 표현이 나 모니커를 사용 하 고는 모니커는 이름이 있는 스트림에 바인딩합니다. 그런 다음 읽기 하 고 해당 스트림에 쓸 수 있습니다. 실제 목적 `CMonikerFile` 에 대 한 간단한 액세스를 제공 하는 것 `IStream`s로 명명 `IMoniker`s 스트림을 직접 바인딩할 필요가 없습니다 있도록 아직 `CFile` 스트림에 기능입니다.

`CMonikerFile` 스트림 이외의 값으로 바인딩할 사용할 수 없습니다. 저장소 또는 개체에 바인딩할 경우 사용 해야는 `IMoniker` 직접 인터페이스입니다.

모니커 및 스트림에 대 한 자세한 내용은 참조 하세요. [COleStreamFile](../../mfc/reference/colestreamfile-class.md) 에 *MFC 참조* 및 [IStream](/windows/desktop/api/objidl/nn-objidl-istream) 및 [IMoniker](/windows/desktop/api/objidl/nn-objidl-imoniker) 에 Windows SDK입니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

[COleStreamFile](../../mfc/reference/colestreamfile-class.md)

`CMonikerFile`

## <a name="requirements"></a>요구 사항

**헤더:** afxole.h

##  <a name="close"></a>  CMonikerFile::Close

분리 스트림을 해제 하 고 모니커를 해제 하려면이 함수를 호출 합니다.

```
virtual void Close();
```

### <a name="remarks"></a>설명

아직 열지 않은 또는 이미 닫힌 스트림에 대해 호출할 수 있습니다.

##  <a name="cmonikerfile"></a>  CMonikerFile::CMonikerFile

`CMonikerFile` 개체를 생성합니다.

```
CMonikerFile();
```

##  <a name="createbindcontext"></a>  CMonikerFile::CreateBindContext

초기화 하는 기본 바인딩 컨텍스트를 생성 하려면이 함수를 호출 합니다.

```
IBindCtx* CreateBindContext(CFileException* pError);
```

### <a name="parameters"></a>매개 변수

*pError*<br/>
파일 예외에 대 한 포인터입니다. 오류가 발생 한 원인에 설정 됩니다.

### <a name="return-value"></a>반환 값

바인드 컨텍스트에 대 한 포인터로 [IBindCtx](/windows/desktop/api/objidl/nn-objidl-ibindctx) 바인딩할 성공 하면 NULL입니다. 인스턴스를 사용 하 여 열린 경우는 `IBindHost` 인터페이스를 바인드 컨텍스트에에서 검색 되는 `IBindHost`합니다. 없는 경우 없는 `IBindHost` 인터페이스 또는 인터페이스 반환 되지 않으면 바인딩 컨텍스트, 바인딩 컨텍스트가 만들어집니다. 에 대 한 설명은 합니다 [IBindHost](https://msdn.microsoft.com/library/ie/ms775076) 인터페이스, Windows SDK를 참조 하세요.

### <a name="remarks"></a>설명

바인딩 컨텍스트는 특정 모니커 바인딩 작업에 대 한 정보를 저장 하는 개체입니다. 사용자 지정 바인딩 컨텍스트를 제공 하려면이 함수를 재정의할 수 있습니다.

##  <a name="detach"></a>  CMonikerFile::Detach

스트림을 닫으려면이 함수를 호출 합니다.

```
BOOL Detach(CFileException* pError = NULL);
```

### <a name="parameters"></a>매개 변수

*pError*<br/>
파일 예외에 대 한 포인터입니다. 오류가 발생 한 원인에 설정 됩니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

##  <a name="getmoniker"></a>  CMonikerFile::GetMoniker

현재 모니커에 대 한 포인터를 검색 하려면이 함수를 호출 합니다.

```
IMoniker* GetMoniker() const;
```

### <a name="return-value"></a>반환 값

현재 모니커 인터페이스에 대 한 포인터 ( [IMoniker](/windows/desktop/api/objidl/nn-objidl-imoniker)).

### <a name="remarks"></a>설명

이후 `CMonikerFile` , 인터페이스가 아닙니다. 반환 된 포인터 참조 횟수를 증가 하지 않습니다 (통해 [AddRef](/windows/desktop/api/unknwn/nf-unknwn-iunknown-addref)), 모니커를 놓으면 때는 `CMonikerFile` 개체가 해제 되는 합니다. 모니커를 점유 하거나 직접 해제 하려는 경우 해야 `AddRef` 것입니다.

##  <a name="open"></a>  CMonikerFile::Open

파일 또는 모니커 개체를이 멤버 함수를 호출 합니다.

```
virtual BOOL Open(
    LPCTSTR lpszURL,
    CFileException* pError = NULL);

virtual BOOL Open(
    IMoniker* pMoniker,
    CFileException* pError = NULL);
```

### <a name="parameters"></a>매개 변수

*lpszURL*<br/>
URL 또는 열려는 파일의 이름입니다.

*pError*<br/>
파일 예외에 대 한 포인터입니다. 오류가 발생 한 원인에 설정 됩니다.

*pMoniker*<br/>
모니커 인터페이스에 대 한 포인터 `IMoniker` 한 스트림을 가져올 하는 데 있습니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

합니다 *lpszURL* Macintosh에서 매개 변수를 사용할 수 없습니다. 만 *pMoniker* 형태의 `Open` Macintosh에서 사용할 수 있습니다.

URL 또는 파일 이름을 사용할 수는 *lpszURL* 매개 변수입니다. 예를 들어:

[!code-cpp[NVC_MFCWinInet#6](../../mfc/codesnippet/cpp/cmonikerfile-class_1.cpp)]

\- 또는 -

[!code-cpp[NVC_MFCWinInet#7](../../mfc/codesnippet/cpp/cmonikerfile-class_2.cpp)]

## <a name="see-also"></a>참고자료

[COleStreamFile 클래스](../../mfc/reference/colestreamfile-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CAsyncMonikerFile 클래스](../../mfc/reference/casyncmonikerfile-class.md)
