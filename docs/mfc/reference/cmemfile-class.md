---
title: CMemFile 클래스
ms.date: 11/04/2016
f1_keywords:
- CMemFile
- AFX/CMemFile
- AFX/CMemFile::CMemFile
- AFX/CMemFile::Attach
- AFX/CMemFile::Detach
- AFX/CMemFile::Alloc
- AFX/CMemFile::Free
- AFX/CMemFile::GrowFile
- AFX/CMemFile::Memcpy
- AFX/CMemFile::Realloc
helpviewer_keywords:
- CMemFile [MFC], CMemFile
- CMemFile [MFC], Attach
- CMemFile [MFC], Detach
- CMemFile [MFC], Alloc
- CMemFile [MFC], Free
- CMemFile [MFC], GrowFile
- CMemFile [MFC], Memcpy
- CMemFile [MFC], Realloc
ms.assetid: 20e86515-e465-4f73-b2ea-e49789d63165
ms.openlocfilehash: a57f4e245ca1e93ec0edd454a7f407aeda5beca4
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64341684"
---
# <a name="cmemfile-class"></a>CMemFile 클래스

합니다 [CFile](../../mfc/reference/cfile-class.md)-메모리 파일을 지 원하는 클래스를 파생 합니다.

## <a name="syntax"></a>구문

```
class CMemFile : public CFile
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CMemFile::CMemFile](#cmemfile)|메모리 파일 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CMemFile::Attach](#attach)|메모리 블록을 연결 `CMemFile`합니다.|
|[CMemFile::Detach](#detach)|메모리 블록에 분리 `CMemFile` 분리 하는 메모리 블록에 대 한 포인터를 반환 합니다.|

### <a name="protected-methods"></a>Protected 메서드

|이름|설명|
|----------|-----------------|
|[CMemFile::Alloc](#alloc)|메모리 할당 동작을 수정 하려면 재정의 합니다.|
|[CMemFile::Free](#free)|메모리 할당 취소 동작을 수정 하려면 재정의 합니다.|
|[CMemFile::GrowFile](#growfile)|파일 증가 하는 경우 동작을 수정 하려면 재정의 합니다.|
|[CMemFile::Memcpy](#memcpy)|파일 읽기 및 쓰기 때 메모리 복사 동작을 수정 하려면 재정의 합니다.|
|[CMemFile::Realloc](#realloc)|메모리 재할당 동작을 수정 하려면 재정의 합니다.|

## <a name="remarks"></a>설명

이러한 메모리 파일 RAM 대신 디스크에 저장 되는 점을 제외 하 고 디스크 파일 처럼 동작 합니다. 메모리 파일을 빠른 임시 저장소에 대 한 원시 바이트를 전송 하기 위한 유용한 되었거나 독립 프로세스 간에 개체를 직렬화 합니다.

`CMemFile` 개체 자체 메모리를 자동으로 할당할 수 있습니다 하거나 고유한 메모리 블록을 연결할 수 있습니다 합니다 `CMemFile` 개체를 호출 하 여 [연결](#attach)합니다. 두 경우 모두 메모리 파일의 크기를 자동으로 증가 하는 것에 대 한 메모리에 할당 됩니다 `nGrowBytes`-경우 증가 크기 `nGrowBytes` 0이 아닙니다.

메모리 블록의 소멸 시 자동으로 삭제 됩니다는 `CMemFile` 메모리에서 원래 할당 된 개체는 `CMemFile` 개체에 연결 된 메모리 할당을 취소 하는 일을 담당 하는 고, 그렇지 않으면 개체입니다.

메모리 블록에서 분리 하는 경우 제공 된 포인터를 통해 액세스할 수 있습니다 합니다 `CMemFile` 개체를 호출 하 여 [분리](#detach)합니다.

가장 일반적인 사용 `CMemFile` 를 만드는 것을 `CMemFile` 개체를 호출 하 여 사용할 [CFile](../../mfc/reference/cfile-class.md) 멤버 함수입니다. 생성을 확인를 `CMemFile` 자동으로 열립니다: 호출 하지 마세요 [CFile::Open](../../mfc/reference/cfile-class.md#open), 디스크 파일에만 사용 됩니다. 때문에 `CMemFile` 디스크 파일에 데이터 멤버를 사용 하지 않는 `CFile::m_hFile` 사용 되지 않습니다.

합니다 `CFile` 멤버 함수 [중복](../../mfc/reference/cfile-class.md#duplicate), [LockRange](../../mfc/reference/cfile-class.md#lockrange), 및 [UnlockRange](../../mfc/reference/cfile-class.md#unlockrange) 에 대 한 구현 되지 않은 `CMemFile`합니다. 이러한 함수를 호출 하는 경우는 `CMemFile` 개체를 받을 수는 [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md)합니다.

`CMemFile` 런타임 라이브러리 함수를 사용 하 여 [malloc](../../c-runtime-library/reference/malloc.md)를 [realloc](../../c-runtime-library/reference/realloc.md), 및 [무료](../../c-runtime-library/reference/free.md) 할당할 다시 할당 하 고 메모리 및 내장 할당을 취소 [memcpy](../../c-runtime-library/reference/memcpy-wmemcpy.md) 읽고 쓸 때 블록 복사본 메모리입니다. 이 동작이 나 동작을 변경 하려는 경우 때 `CMemFile` 증가 파일에서 고유한 클래스를 파생 `CMemFile` 하 고 적절 한 함수를 재정의 합니다.

에 대 한 자세한 `CMemFile`, 문서를 참조 하세요 [MFC의 파일](../../mfc/files-in-mfc.md) 및 [메모리 관리 (MFC)](../../mfc/memory-management.md) 내용과 [파일 처리](../../c-runtime-library/file-handling.md) 에 *런타임 라이브러리 참조*합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

`CMemFile`

## <a name="requirements"></a>요구 사항

**헤더:** afx.h

##  <a name="alloc"></a>  CMemFile::Alloc

이 함수를 호출 하 `CMemFile` 멤버 함수입니다.

```
virtual BYTE* Alloc(SIZE_T nBytes);
```

### <a name="parameters"></a>매개 변수

*nBytes*<br/>
할당할 메모리의 바이트 수입니다.

### <a name="return-value"></a>반환 값

할당 된 메모리 블록에 대 한 포인터 또는 할당에 실패 한 경우 NULL입니다.

### <a name="remarks"></a>설명

사용자 지정 메모리 할당을 구현 하려면이 함수를 재정의 합니다. 이 함수를 재정의 하는 경우에 재정의 하려는 아마도 [무료](#free) 하 고 [Realloc](#realloc) 도 합니다.

런타임 라이브러리 함수를 사용 하 여 기본 구현은 [malloc](../../c-runtime-library/reference/malloc.md) 메모리를 할당 합니다.

##  <a name="attach"></a>  CMemFile::Attach

메모리 블록을 연결 하려면이 함수를 호출 `CMemFile`합니다.

```
void Attach(
    BYTE* lpBuffer,
    UINT nBufferSize,
    UINT nGrowBytes = 0);
```

### <a name="parameters"></a>매개 변수

*lpBuffer*<br/>
에 연결 되는 버퍼에 대 한 포인터 `CMemFile`합니다.

*nBufferSize*<br/>
버퍼의 크기를 바이트 단위로 지정 하는 정수입니다.

*nGrowBytes*<br/>
메모리 할당 바이트에서 증가 합니다.

### <a name="remarks"></a>설명

이 인해 `CMemFile` 메모리 파일로 메모리 블록을 사용 하도록 합니다.

하는 경우 *nGrowBytes* 가 0 이면 `CMemFile` 파일 길이를 설정 하는 *nBufferSize*합니다. 즉, 메모리 블록의 데이터에 연결 된 전에 `CMemFile` 파일으로 사용 됩니다. 이 방식으로 만든 메모리 파일을 증가 될 수 없습니다.

파일 증가 수 없으므로, 발생 하지 않도록 주의 해야 `CMemFile` 파일 증가 하려고 합니다. 예를 들어 호출 하지 않습니다는 `CMemFile` 의 재정의 [CFile:Write](../../mfc/reference/cfile-class.md#write) 에 끝을 지난 작성 하거나 호출 하지 마세요 [CFile:SetLength](../../mfc/reference/cfile-class.md#setlength) 이상 길이가 *nBufferSize*.

하는 경우 *nGrowBytes* 가 0 보다 크면 `CMemFile` 연결한 후 메모리 블록의 내용이 무시 됩니다. 메모리 파일의 내용을 사용 하 여 처음부터 작성 해야 합니다 `CMemFile` 재정의할 `CFile::Write`합니다. 파일의 끝을 지난 작성 하거나 호출 하 여 파일을 확장 하려는 경우는 `CMemFile` 재정의할 `CFile::SetLength`, `CMemFile` 메모리를 할당 단위로 증가 *nGrowBytes*합니다. 메모리 블록에 전달 하는 경우 실패 된 메모리 할당을 증가 `Attach` 와 호환 되는 메서드를 사용 하 여 할당 되지 않은 [Alloc](#alloc)합니다. 기본 구현을와 호환 되도록 `Alloc`, 런타임 라이브러리 함수를 사용 하 여 메모리를 할당 해야 합니다 [malloc](../../c-runtime-library/reference/malloc.md) 하거나 [calloc](../../c-runtime-library/reference/calloc.md)합니다.

##  <a name="cmemfile"></a>  CMemFile::CMemFile

첫 번째 오버 로드는 빈 메모리 파일을 엽니다.

```
CMemFile(UINT nGrowBytes = 1024);

CMemFile(
    BYTE* lpBuffer,
    UINT nBufferSize,
    UINT nGrowBytes = 0);
```

### <a name="parameters"></a>매개 변수

*nGrowBytes*<br/>
메모리 할당 바이트에서 증가 합니다.

*lpBuffe*크기의 정보를 받는 버퍼에 대 한 포인터 r *nBufferSize*합니다.

*nBufferSize*<br/>
파일 버퍼의 크기를 바이트 단위로 지정 하는 정수입니다.

### <a name="remarks"></a>설명

생성자에서 해당 파일을 열은 호출 하지 않아야 하며 [CFile::Open](../../mfc/reference/cfile-class.md#open)합니다.

첫 번째 생성자는를 사용 하 고 즉시 호출 하는 경우에 따라 동일 하 게 두 번째 오버 로드 동작 [연결](#attach) 동일한 매개 변수를 사용 합니다. 자세한 내용은 `Attach`를 참조하세요.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCFiles#36](../../atl-mfc-shared/reference/codesnippet/cpp/cmemfile-class_1.cpp)]

##  <a name="detach"></a>  CMemFile::Detach

사용 중인 메모리 블록에 대 한 포인터를 가져오려면이 함수를 호출 `CMemFile`합니다.

```
BYTE* Detach();
```

### <a name="return-value"></a>반환 값

메모리 파일의 내용을 포함 하는 메모리 블록에 대 한 포인터입니다.

### <a name="remarks"></a>설명

이 함수를 닫습니다. 또한 호출 된 `CMemFile`합니다. 메모리 블록 다시 연결할 수 있습니다 `CMemFile` 호출한 [연결](#attach)합니다. 호출 해야 파일을 다시 연결 하 고 그 안에 데이터를 사용 하려는 경우 [CFile::GetLength](../../mfc/reference/cfile-class.md#getlength) 호출 하기 전에 파일의 길이를 가져오는 `Detach`합니다. 메모리 블록을 연결 하는 경우 사용자에 게 유의 `CMemFile` 해당 데이터를 사용할 수 있도록 ( `nGrowBytes` = = 0), 메모리 파일이 증가할 수 없습니다.

##  <a name="free"></a>  CMemFile::Free

이 함수를 호출 하 `CMemFile` 멤버 함수입니다.

```
virtual void Free(BYTE* lpMem);
```

### <a name="parameters"></a>매개 변수

*lpMem*<br/>
메모리 할당 취소에 대 한 포인터입니다.

### <a name="remarks"></a>설명

사용자 지정 메모리 할당 취소를 구현 하려면이 함수를 재정의 합니다. 이 함수를 재정의 하는 경우에 재정의 하려는 아마도 [Alloc](#alloc) 하 고 [Realloc](#realloc) 도 합니다.

##  <a name="growfile"></a>  CMemFile::GrowFile

몇 가지에 의해 호출 되는이 함수는 `CMemFile` 멤버 함수입니다.

```
virtual void GrowFile(SIZE_T dwNewLen);
```

### <a name="parameters"></a>매개 변수

*dwNewLen*<br/>
메모리 파일의 새 크기입니다.

### <a name="remarks"></a>설명

변경 하려는 경우 재정의할 수 있습니다 어떻게 `CMemFile` 해당 파일을 증가 합니다. 기본 구현 호출 [Realloc](#realloc) 기존 블록을 증가 (또는 [Alloc](#alloc) 메모리 블록을 만들려면)의 배수로 메모리를 할당 하는 `nGrowBytes` 생성자에 지정 된 값 또는 [연결](#attach) 호출 합니다.

##  <a name="memcpy"></a>  CMemFile::Memcpy

이 함수를 호출 하는 `CMemFile` 의 재정의 [CFile::Read](../../mfc/reference/cfile-class.md#read) 및 [CFile::Write](../../mfc/reference/cfile-class.md#write) 메모리 파일에서 데이터를 전송 합니다.

```
virtual BYTE* Memcpy(
    BYTE* lpMemTarget,
    const BYTE* lpMemSource,
    SIZE_T nBytes);
```

### <a name="parameters"></a>매개 변수

*lpMemTarget*<br/>
소스 메모리는 복사 된 메모리 블록에 대 한 포인터입니다.

*lpMemSource*<br/>
원본 메모리 블록에 대 한 포인터입니다.

*nBytes*<br/>
복사할 바이트 수입니다.

### <a name="return-value"></a>반환 값

복사본 *lpMemTarget*합니다.

### <a name="remarks"></a>설명

방법을 변경 하려는 경우이 함수를 재정의 하는 `CMemFile` 이러한 메모리 복사 않습니다.

##  <a name="realloc"></a>  CMemFile::Realloc

이 함수를 호출 하 `CMemFile` 멤버 함수입니다.

```
virtual BYTE* Realloc(
    BYTE* lpMem,
    SIZE_T nBytes);
```

### <a name="parameters"></a>매개 변수

*lpMem*<br/>
다시 할당 된 메모리 블록에 대 한 포인터입니다.

*nBytes*<br/>
메모리 블록에 대 한 새 크기입니다.

### <a name="return-value"></a>반환 값

다시 할당 (이동 가능한 경우), 메모리 블록에 대 한 포인터 또는 재할당에 실패 한 경우 NULL입니다.

### <a name="remarks"></a>설명

사용자 지정 메모리 재할당을 구현 하려면이 함수를 재정의 합니다. 이 함수를 재정의 하는 경우에 재정의 하려는 아마도 [Alloc](#alloc) 하 고 [무료](#free) 도 합니다.

## <a name="see-also"></a>참고자료

[CFile 클래스](../../mfc/reference/cfile-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)
