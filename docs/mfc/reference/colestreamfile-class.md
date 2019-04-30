---
title: COleStreamFile 클래스
ms.date: 11/04/2016
f1_keywords:
- COleStreamFile
- AFXOLE/COleStreamFile
- AFXOLE/COleStreamFile::COleStreamFile
- AFXOLE/COleStreamFile::Attach
- AFXOLE/COleStreamFile::CreateMemoryStream
- AFXOLE/COleStreamFile::CreateStream
- AFXOLE/COleStreamFile::Detach
- AFXOLE/COleStreamFile::GetStream
- AFXOLE/COleStreamFile::OpenStream
helpviewer_keywords:
- COleStreamFile [MFC], COleStreamFile
- COleStreamFile [MFC], Attach
- COleStreamFile [MFC], CreateMemoryStream
- COleStreamFile [MFC], CreateStream
- COleStreamFile [MFC], Detach
- COleStreamFile [MFC], GetStream
- COleStreamFile [MFC], OpenStream
ms.assetid: e4f93698-e17c-4a18-a7c0-4b4df8eb4d93
ms.openlocfilehash: 2bc943c74f456302b13db77bf28b6e4b21a5524b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62373516"
---
# <a name="colestreamfile-class"></a>COleStreamFile 클래스

OLE 구조적 스토리지의 일부로 복합 파일의 데이터 스트림(`IStream`)을 나타냅니다.

## <a name="syntax"></a>구문

```
class COleStreamFile : public CFile
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[COleStreamFile::COleStreamFile](#colestreamfile)|`COleStreamFile` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[COleStreamFile::Attach](#attach)|개체를 사용 하 여 스트림을 연결 합니다.|
|[COleStreamFile::CreateMemoryStream](#creatememorystream)|전역 메모리에서 스트림을 만들고 개체를 사용 하 여 연결 합니다.|
|[COleStreamFile::CreateStream](#createstream)|스트림을 만들고 개체를 사용 하 여 연결 합니다.|
|[COleStreamFile::Detach](#detach)|스트림을 개체에서 연결을 끊습니다.|
|[COleStreamFile::GetStream](#getstream)|현재 스트림을 반환합니다.|
|[COleStreamFile::OpenStream](#openstream)|안전 하 게 되는 스트림을 엽니다 및 개체와 연결 합니다.|

## <a name="remarks"></a>설명

`IStorage` 열거나 아니면 메모리 스트림을 만든 스트림의 수 전에 개체가 존재 해야 합니다.

`COleStreamFile` 개체와 똑같이 조작 [CFile](../../mfc/reference/cfile-class.md) 개체입니다.

스트림 및 저장소를 조작 하는 방법에 대 한 자세한 내용은 문서를 참조 하세요. [컨테이너: 복합 파일](../../mfc/containers-compound-files.md)...

자세한 내용은 [IStream](/windows/desktop/api/objidl/nn-objidl-istream) 하 고 [IStorage](/windows/desktop/api/objidl/nn-objidl-istorage) Windows SDK의 합니다.

## <a name="inheritance-hierarchy"></a>상속 계층

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

`COleStreamFile`

## <a name="requirements"></a>요구 사항

**헤더:** afxole.h

##  <a name="attach"></a>  COleStreamFile::Attach

제공 된 OLE 스트림을 사용 하 여 연결 된 `COleStreamFile` 개체입니다.

```
void Attach(LPSTREAM lpStream);
```

### <a name="parameters"></a>매개 변수

*lpStream*<br/>
OLE 스트림 가리키는 (`IStream`) 개체와 연결 되도록 합니다. NULL일 수 없습니다.

### <a name="remarks"></a>설명

개체가 이미 아니어야 OLE 스트림과 함께 연결 합니다.

자세한 내용은 [IStream](/windows/desktop/api/objidl/nn-objidl-istream) Windows SDK에 있습니다.

##  <a name="colestreamfile"></a>  COleStreamFile::COleStreamFile

`COleStreamFile` 개체를 만듭니다.

```
COleStreamFile(LPSTREAM lpStream = NULL);
```

### <a name="parameters"></a>매개 변수

*lpStream*<br/>
개체와 연결 될 OLE 스트림에 대 한 포인터입니다.

### <a name="remarks"></a>설명

하는 경우 *lpStream* 가 null 인 경우 개체는 OLE 스트림과 연결 되지, 제공 된 OLE 스트림과 연결 된 개체가 고, 그렇지 합니다.

자세한 내용은 [IStream](/windows/desktop/api/objidl/nn-objidl-istream) Windows SDK에 있습니다.

##  <a name="creatememorystream"></a>  COleStreamFile::CreateMemoryStream

안전 하 게 여기서 오류는 일반적으로 필요한 조건을 전역 공유 메모리에서 새 스트림을 만듭니다.

```
BOOL CreateMemoryStream(CFileException* pError = NULL);
```

### <a name="parameters"></a>매개 변수

*pError*<br/>
가리키는 [CFileException](../../mfc/reference/cfileexception-class.md) 개체 또는 만들기 작업의 완료 상태를 나타내는 NULL입니다. 스트림을 만들기를 시도 하 여 생성 가능한 예외를 모니터링 하려는 경우이 매개 변수를 제공 합니다.

### <a name="return-value"></a>반환 값

스트림이 성공적으로 만들어지면 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

메모리는 OLE 하위 시스템에 의해 할당 됩니다.

자세한 내용은 [CreateStreamOnHGlobal](/windows/desktop/api/combaseapi/nf-combaseapi-createstreamonhglobal) Windows SDK에 있습니다.

##  <a name="createstream"></a>  COleStreamFile::CreateStream

여기서 오류는 일반적으로 필요한 조건을 제공 되는 저장소 개체의 새 스트림을 안전 하 게 만듭니다.

```
BOOL CreateStream(
    LPSTORAGE lpStorage,
    LPCTSTR lpszStreamName,
    DWORD nOpenFlags = modeReadWrite|shareExclusive|modeCreate,
    CFileException* pError = NULL);
```

### <a name="parameters"></a>매개 변수

*lpStorage*<br/>
만들려는 stream을 포함 하는 OLE 저장소 개체를 가리킵니다. NULL일 수 없습니다.

*lpszStreamName*<br/>
만들 스트림의 이름입니다. NULL일 수 없습니다.

*nOpenFlags*<br/>
스트림을 열 때 사용할 액세스 모드입니다. 단독, 읽기/쓰기가 가능 하며 모드 만들기 기본적으로 사용 됩니다. 사용 가능한 모드의 전체 목록은 참조 하세요. [CFile::CFile](../../mfc/reference/cfile-class.md#cfile)합니다.

*pError*<br/>
가리키는 [CFileException](../../mfc/reference/cfileexception-class.md) 개체 또는 NULL입니다. 스트림을 만들기를 시도 하 여 생성 가능한 예외를 모니터링 하려는 경우이 매개 변수를 제공 합니다.

### <a name="return-value"></a>반환 값

스트림이 성공적으로 만들어지면 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

열기에 실패 하는 경우 파일 예외가 throw 됩니다 하 고 *pError* NULL이 아닙니다.

자세한 내용은 [IStorage::CreateStream](/windows/desktop/api/objidl/nf-objidl-istorage-createstream) Windows SDK에 있습니다.

##  <a name="detach"></a>  COleStreamFile::Detach

스트림을 닫지 않고 스트림에 개체의 연결을 끊습니다.

```
LPSTREAM Detach();
```

### <a name="return-value"></a>반환 값

스트림에 대 한 포인터 (`IStream`) 된 개체와 연결 합니다.

### <a name="remarks"></a>설명

프로그램을 종료 하기 전에 스트림은 다른 방식으로 닫아야 합니다.

자세한 내용은 [IStream](/windows/desktop/api/objidl/nn-objidl-istream) Windows SDK에 있습니다.

##  <a name="getstream"></a>  COleStreamFile::GetStream

현재 스트림에 대 한 포인터를 반환 하려면이 함수를 호출 합니다.

```
IStream* GetStream() const;
```

### <a name="return-value"></a>반환 값

현재 스트림 인터페이스에 대 한 포인터 ( [IStream](/windows/desktop/api/objidl/nn-objidl-istream)).

##  <a name="openstream"></a>  COleStreamFile::OpenStream

기존 스트림을 엽니다.

```
BOOL OpenStream(
    LPSTORAGE lpStorage,
    LPCTSTR lpszStreamName,
    DWORD nOpenFlags = modeReadWrite|shareExclusive,
    CFileException* pError = NULL);
```

### <a name="parameters"></a>매개 변수

*lpStorage*<br/>
열려는 스트림이 포함 된 OLE 저장소 개체를 가리킵니다. NULL일 수 없습니다.

*lpszStreamName*<br/>
열 스트림의 이름입니다. NULL일 수 없습니다.

*nOpenFlags*<br/>
스트림을 열 때 사용할 액세스 모드입니다. 전용 및 읽기/쓰기 모드는 기본적으로 사용 됩니다. 사용 가능한 모드의 전체 목록은 참조 하세요 [CFile::CFile](../../mfc/reference/cfile-class.md#cfile)합니다.

*pError*<br/>
가리키는 [CFileException](../../mfc/reference/cfileexception-class.md) 개체 또는 NULL입니다. 스트림을 여는 데 시도 하 여 생성 가능한 예외를 모니터링 하려는 경우이 매개 변수를 제공 합니다.

### <a name="return-value"></a>반환 값

스트림이 성공적으로 열리는 경우 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

열기에 실패 하는 경우 파일 예외가 throw 됩니다 하 고 *pError* NULL이 아닙니다.

자세한 내용은 [IStorage::OpenStream](/windows/desktop/api/objidl/nf-objidl-istorage-openstream) Windows SDK에 있습니다.

## <a name="see-also"></a>참고자료

[CFile 클래스](../../mfc/reference/cfile-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)
