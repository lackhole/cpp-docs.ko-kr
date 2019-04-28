---
title: CAtlTemporaryFile 클래스
ms.date: 11/04/2016
f1_keywords:
- CAtlTemporaryFile
- ATLFILE/ATL::CAtlTemporaryFile
- ATLFILE/ATL::CAtlTemporaryFile::CAtlTemporaryFile
- ATLFILE/ATL::CAtlTemporaryFile::Close
- ATLFILE/ATL::CAtlTemporaryFile::Create
- ATLFILE/ATL::CAtlTemporaryFile::Flush
- ATLFILE/ATL::CAtlTemporaryFile::GetPosition
- ATLFILE/ATL::CAtlTemporaryFile::GetSize
- ATLFILE/ATL::CAtlTemporaryFile::HandsOff
- ATLFILE/ATL::CAtlTemporaryFile::HandsOn
- ATLFILE/ATL::CAtlTemporaryFile::LockRange
- ATLFILE/ATL::CAtlTemporaryFile::Read
- ATLFILE/ATL::CAtlTemporaryFile::Seek
- ATLFILE/ATL::CAtlTemporaryFile::SetSize
- ATLFILE/ATL::CAtlTemporaryFile::TempFileName
- ATLFILE/ATL::CAtlTemporaryFile::UnlockRange
- ATLFILE/ATL::CAtlTemporaryFile::Write
helpviewer_keywords:
- CAtlTemporaryFile class
ms.assetid: 05f0f2a5-94f6-4594-8dae-b114292ff5f9
ms.openlocfilehash: c1da5037deb0143c6d05009baccc8c1553616028
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62246904"
---
# <a name="catltemporaryfile-class"></a>CAtlTemporaryFile 클래스

이 클래스는 만들고 임시 파일을 사용 하기 위한 메서드를 제공합니다.

> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
class CAtlTemporaryFile
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile)|생성자입니다.|
|[CAtlTemporaryFile::~CAtlTemporaryFile](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CAtlTemporaryFile::Close](#close)|임시 파일을 닫으려면이 메서드를 호출 하 고 해당 콘텐츠를 삭제 하거나 또는 지정 된 파일 이름으로 저장 합니다.|
|[CAtlTemporaryFile::Create](#create)|임시 파일을 만들려면이 메서드를 호출 합니다.|
|[CAtlTemporaryFile::Flush](#flush)|임시 파일에 쓸 파일 버퍼에 남아 있는 데이터를 적용 하려면이 메서드를 호출 합니다.|
|[CAtlTemporaryFile::GetPosition](#getposition)|현재 파일 포인터 위치를 가져오려면이 메서드를 호출 합니다.|
|[CAtlTemporaryFile::GetSize](#getsize)|임시 파일의 바이트에서 크기를 가져오려면이 메서드를 호출 합니다.|
|[CAtlTemporaryFile::HandsOff](#handsoff)|파일에이 메서드를 호출 합니다 `CAtlTemporaryFile` 개체입니다.|
|[CAtlTemporaryFile::HandsOn](#handson)|기존 임시 파일을 열고 파일의 끝에 포인터를이 메서드를 호출 합니다.|
|[CAtlTemporaryFile::LockRange](#lockrange)|다른 프로세스에 액세스 하지 못하도록 파일에 영역을 잠그려는이 메서드를 호출 합니다.|
|[CAtlTemporaryFile::Read](#read)|파일 포인터에 의해 표시 되는 위치에서 시작 하 여 임시 파일에서 데이터를 읽기 위해이 메서드를 호출 합니다.|
|[CAtlTemporaryFile::Seek](#seek)|임시 파일의 파일 포인터를 이동 하려면이 메서드를 호출 합니다.|
|[CAtlTemporaryFile::SetSize](#setsize)|임시 파일의 크기를 설정 하려면이 메서드를 호출 합니다.|
|[CAtlTemporaryFile::TempFileName](#tempfilename)|임시 파일의 이름을 반환 하려면이 메서드를 호출 합니다.|
|[CAtlTemporaryFile::UnlockRange](#unlockrange)|임시 파일의 영역을 잠금 해제 하려면이 메서드를 호출 합니다.|
|[CAtlTemporaryFile::Write](#write)|파일 포인터에 의해 표시 되는 위치에서 시작 하 여 임시 파일에 데이터를 쓸이 메서드를 호출 합니다.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[CAtlTemporaryFile::operator 핸들](#operator_handle)|임시 파일에 대 한 핸들을 반환합니다.|

## <a name="remarks"></a>설명

`CAtlTemporaryFile` 쉽게 만들고 임시 파일을 사용 합니다. 파일은 자동으로 명명 된, 열, 닫히고 삭제 합니다. 파일 콘텐츠 파일을 닫은 후 필요한 경우 지정 된 이름의 새 파일에 저장할 수 있습니다.

## <a name="requirements"></a>요구 사항

**헤더:** atlfile.h

## <a name="example"></a>예제

예를 참조 하세요 [CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile)합니다.

##  <a name="catltemporaryfile"></a>  CAtlTemporaryFile::CAtlTemporaryFile

생성자입니다.

```
CAtlTemporaryFile() throw();
```

### <a name="remarks"></a>설명

파일을 실제로 열려 있지는 호출 될 때까지 [CAtlTemporaryFile::Create](#create)합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#73](../../atl/codesnippet/cpp/catltemporaryfile-class_1.cpp)]

##  <a name="dtor"></a>  CAtlTemporaryFile::~CAtlTemporaryFile

소멸자입니다.

```
~CAtlTemporaryFile() throw();
```

### <a name="remarks"></a>설명

소멸자 호출 [CAtlTemporaryFile::Close](#close)합니다.

##  <a name="close"></a>  CAtlTemporaryFile::Close

임시 파일을 닫으려면이 메서드를 호출 하 고 해당 콘텐츠를 삭제 하거나 또는 지정 된 파일 이름으로 저장 합니다.

```
HRESULT Close(LPCTSTR szNewName = NULL) throw();
```

### <a name="parameters"></a>매개 변수

*szNewName*<br/>
임시 파일의 내용을 저장 하려면 새 파일의 이름입니다. 이 인수가 NULL 인 경우에 임시 파일의 내용이 삭제 됩니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

### <a name="example"></a>예제

예를 참조 하세요 [CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile)합니다.

##  <a name="create"></a>  CAtlTemporaryFile::Create

임시 파일을 만들려면이 메서드를 호출 합니다.

```
HRESULT Create(LPCTSTR pszDir = NULL, DWORD dwDesiredAccess = GENERIC_WRITE) throw();
```

### <a name="parameters"></a>매개 변수

*pszDir*<br/>
임시 파일의 경로입니다. 이 NULL 이면 [GetTempPath](/windows/desktop/api/fileapi/nf-fileapi-gettemppatha) 경로 할당 하도록 호출 됩니다.

*dwDesiredAccess*<br/>
원하는 액세스 합니다. 참조 *dwDesiredAccess* 에 [CreateFile](/windows/desktop/api/fileapi/nf-fileapi-createfilea) Windows SDK에 있습니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

### <a name="example"></a>예제

예를 참조 하세요 [CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile)합니다.

##  <a name="flush"></a>  CAtlTemporaryFile::Flush

임시 파일에 쓸 파일 버퍼에 남아 있는 데이터를 적용 하려면이 메서드를 호출 합니다.

```
HRESULT Flush() throw();
```

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

### <a name="remarks"></a>설명

비슷합니다 [CAtlTemporaryFile::HandsOff](#handsoff)를 제외 하 고 파일을 닫을 수 없습니다.

### <a name="example"></a>예제

예를 참조 하세요 [CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile)합니다.

##  <a name="getposition"></a>  CAtlTemporaryFile::GetPosition

현재 파일 포인터 위치를 가져오려면이 메서드를 호출 합니다.

```
HRESULT GetPosition(ULONGLONG& nPos) const throw();
```

### <a name="parameters"></a>매개 변수

*nPos*<br/>
바이트 위치입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

### <a name="remarks"></a>설명

파일 포인터 위치를 변경 하려면 사용 하 여 [CAtlTemporaryFile::Seek](#seek)합니다.

##  <a name="getsize"></a>  CAtlTemporaryFile::GetSize

임시 파일의 바이트에서 크기를 가져오려면이 메서드를 호출 합니다.

```
HRESULT GetSize(ULONGLONG& nLen) const throw();
```

### <a name="parameters"></a>매개 변수

*nLen*<br/>
파일의 바이트 수입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

##  <a name="handsoff"></a>  CAtlTemporaryFile::HandsOff

파일에이 메서드를 호출 합니다 `CAtlTemporaryFile` 개체입니다.

```
HRESULT HandsOff() throw();
```

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

### <a name="remarks"></a>설명

`HandsOff` 및 [CAtlTemporaryFile::HandsOn](#handson) 개체에서 파일 및 필요한 경우 다시 연결 하는 데 사용 됩니다. `HandsOff` 임시 파일에 쓸 파일 버퍼에 남아 있는 데이터를 적용 한 다음 파일을 닫습니다. 닫고 파일을 영구적으로 삭제 하려는 경우 또는 닫습니다 이름이 지정 된 파일의 내용을 보존 하 고 사용 하려는 경우 [CAtlTemporaryFile::Close](#close)합니다.

##  <a name="handson"></a>  CAtlTemporaryFile::HandsOn

기존 임시 파일을 열고 파일의 끝에 포인터를이 메서드를 호출 합니다.

```
HRESULT HandsOn() throw();
```

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

### <a name="remarks"></a>설명

[CAtlTemporaryFile::HandsOff](#handsoff) 고 `HandsOn` 개체에서 파일 및 필요한 경우 다시 연결 하는 데 사용 됩니다.

##  <a name="lockrange"></a>  CAtlTemporaryFile::LockRange

다른 프로세스에 액세스 하지 않도록 하려면 임시 파일의 영역을 잠그려는이 메서드를 호출 합니다.

```
HRESULT LockRange(ULONGLONG nPos, ULONGLONG nCount) throw();
```

### <a name="parameters"></a>매개 변수

*nPos*<br/>
잠금을 시작 해야 하는 파일의 위치입니다.

*nCount*<br/>
잠글 바이트 범위의 길이입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

### <a name="remarks"></a>설명

파일의 바이트를 잠그면 다른 프로세스에서 해당 바이트에 액세스할 수 없습니다. 파일의 둘 이상의 영역을 잠글 수 있습니다 하지만 없습니다 겹치는 영역을 사용할 수는 있습니다. 성공적으로 잠금 해제는 영역을 사용 하 여 [CAtlTemporaryFile::UnlockRange](#unlockrange), 이전에 잠근 지역으로 정확 하 게 해당 바이트 범위를 확인 합니다. `LockRange` 인접 한 지역을 선택 합니다; 병합 하지 않습니다. 잠긴된 두 영역이 인접 한 경우 잠금을 해제 해야 각각 개별적으로 합니다.

##  <a name="operator_handle"></a>  CAtlTemporaryFile::operator HANDLE

임시 파일에 대 한 핸들을 반환합니다.

```
operator HANDLE() throw();
```

##  <a name="read"></a>  CAtlTemporaryFile::Read

파일 포인터에 의해 표시 되는 위치에서 시작 하 여 임시 파일에서 데이터를 읽기 위해이 메서드를 호출 합니다.

```
HRESULT Read(
    LPVOID pBuffer,
    DWORD nBufSize,
    DWORD& nBytesRead) throw();
```

### <a name="parameters"></a>매개 변수

*pBuffer*<br/>
파일에서 읽은 데이터를 받을 버퍼에 대 한 포인터입니다.

*nBufSize*<br/>
버퍼 크기(바이트)입니다.

*nBytesRead*<br/>
읽은 바이트 수입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

### <a name="remarks"></a>설명

호출 [CAtlFile::Read](../../atl/reference/catlfile-class.md#read)합니다. 파일 포인터의 위치를 변경 하려면 호출 [CAtlTemporaryFile::Seek](#seek)합니다.

### <a name="example"></a>예제

예를 참조 하세요 [CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile)합니다.

##  <a name="seek"></a>  CAtlTemporaryFile::Seek

임시 파일의 파일 포인터를 이동 하려면이 메서드를 호출 합니다.

```
HRESULT Seek(LONGLONG nOffset, DWORD dwFrom = FILE_CURRENT) throw();
```

### <a name="parameters"></a>매개 변수

*nOffset*<br/>
오프셋 (바이트)를 제공한 시작 점에서 *dwFrom 합니다.*

*dwFrom*<br/>
시작 지점 (FILE_BEGIN, FILE_CURRENT, 또는 FILE_END)입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

### <a name="remarks"></a>설명

호출 [CAtlFile::Seek](../../atl/reference/catlfile-class.md#seek)합니다. 현재 파일 포인터 위치를 가져오려면, 호출 [CAtlTemporaryFile::GetPosition](#getposition)합니다.

### <a name="example"></a>예제

예를 참조 하세요 [CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile)합니다.

##  <a name="setsize"></a>  CAtlTemporaryFile::SetSize

임시 파일의 크기를 설정 하려면이 메서드를 호출 합니다.

```
HRESULT SetSize(ULONGLONG nNewLen) throw();
```

### <a name="parameters"></a>매개 변수

*nNewLen*<br/>
새 길이 (바이트)에서 파일입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

### <a name="remarks"></a>설명

호출 [CAtlFile::SetSize](../../atl/reference/catlfile-class.md#setsize)합니다. 반환이 파일 포인터가 파일 끝에 배치 됩니다.

##  <a name="tempfilename"></a>  CAtlTemporaryFile::TempFileName

임시 파일의 이름을 반환 하려면이 메서드를 호출 합니다.

```
LPCTSTR TempFileName() throw();
```

### <a name="return-value"></a>반환 값

파일 이름을 가리키는 LPCTSTR을 반환 합니다.

### <a name="remarks"></a>설명

파일 이름에서 생성 됩니다 [CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile) 에 대 한 호출을 사용 하 여 합니다 [GetTempFile](/windows/desktop/api/fileapi/nf-fileapi-gettempfilenamea)Windows SDK 함수입니다. 파일 확장명은 항상 "TFR" 임시 파일입니다.

##  <a name="unlockrange"></a>  CAtlTemporaryFile::UnlockRange

임시 파일의 영역을 잠금 해제 하려면이 메서드를 호출 합니다.

```
HRESULT UnlockRange(ULONGLONG nPos, ULONGLONG nCount) throw();
```

### <a name="parameters"></a>매개 변수

*nPos*<br/>
잠금 해제를 시작 해야 하는 파일의 위치입니다.

*nCount*<br/>
바이트 범위 잠금이 해제 되도록의 길이입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

### <a name="remarks"></a>설명

호출 [CAtlFile::UnlockRange](../../atl/reference/catlfile-class.md#unlockrange)합니다.

##  <a name="write"></a>  CAtlTemporaryFile::Write

파일 포인터에 의해 표시 되는 위치에서 시작 하 여 임시 파일에 데이터를 쓸이 메서드를 호출 합니다.

```
HRESULT Write(
    LPCVOID pBuffer,
    DWORD nBufSize,
    DWORD* pnBytesWritten = NULL) throw();
```

### <a name="parameters"></a>매개 변수

*pBuffer*<br/>
파일에 쓸 데이터가 포함 된 버퍼입니다.

*nBufSize*<br/>
버퍼에서 전송할 바이트 수입니다.

*pnBytesWritten*<br/>
쓰여진 바이트 수입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

### <a name="remarks"></a>설명

호출 [CAtlFile::Write](../../atl/reference/catlfile-class.md#write)합니다.

### <a name="example"></a>예제

예를 참조 하세요 [CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile)합니다.

## <a name="see-also"></a>참고자료

[클래스 개요](../../atl/atl-class-overview.md)<br/>
[CAtlFile 클래스](../../atl/reference/catlfile-class.md)
