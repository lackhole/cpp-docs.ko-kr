---
title: CSharedFile 클래스
ms.date: 11/04/2016
f1_keywords:
- CSharedFile
- AFXADV/CSharedFile
- AFXADV/CSharedFile::CSharedFile
- AFXADV/CSharedFile::Detach
- AFXADV/CSharedFile::SetHandle
helpviewer_keywords:
- CSharedFile [MFC], CSharedFile
- CSharedFile [MFC], Detach
- CSharedFile [MFC], SetHandle
ms.assetid: 5d000422-9ede-4318-a8c9-f7412b674f39
ms.openlocfilehash: e86e64c1de232aba0c17a0fdfb3600e480567a57
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62324131"
---
# <a name="csharedfile-class"></a>CSharedFile 클래스

합니다 [CMemFile](../../mfc/reference/cmemfile-class.md)-공유 메모리 파일을 지 원하는 클래스를 파생된 합니다.

## <a name="syntax"></a>구문

```
class CSharedFile : public CMemFile
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CSharedFile::CSharedFile](#csharedfile)|`CSharedFile` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CSharedFile::Detach](#detach)|공유 메모리 파일을 닫고 해당 메모리 블록의 핸들을 반환 합니다.|
|[CSharedFile::SetHandle](#sethandle)|공유 메모리 파일을 메모리 블록에 연결합니다.|

## <a name="remarks"></a>설명

RAM 대신 디스크에 저장 되는 점을 제외 하 고 메모리 파일 디스크 파일 처럼 동작 합니다. 메모리 파일을 빠른 임시 저장소에 대 한 원시 바이트를 전송 하기 위한 유용한 되었거나 독립 프로세스 간에 개체를 직렬화 합니다.

다른 메모리 파일에서 공유 메모리 파일 다를 사용 하 여 해당 메모리를 할당 하는 [GlobalAlloc](/windows/desktop/api/winbase/nf-winbase-globalalloc) Windows 함수입니다. 합니다 `CSharedFile` 전역적으로 할당 된 메모리 블록에 데이터를 저장 하는 클래스 (사용 하 여 만든 `GlobalAlloc`), 메모리 블록에이 공유 될 수 있습니다 다른 OLE/COM 단일형 데이터 전송 작업의 경우 예를 들어, DDE, 클립보드를 사용 하 여 사용 하 여 `IDataObject`입니다.

`GlobalAlloc` HGLOBAL 처리에서 반환 된 포인터와 같은 메모리에 대 한 포인터 대신 반환 [malloc](../../c-runtime-library/reference/malloc.md)합니다. HGLOBAL 핸들을 특정 응용 프로그램에 필요 합니다. 예를 들어, 클립보드에 데이터를 저장 하려면 HGLOBAL 핸들을 필요 합니다.

유의 사항: `CSharedFile` 사용 하 여 메모리 매핑된 파일 하지 않으며 프로세스 간에 데이터를 직접 공유할 수 없습니다.

`CSharedFile` 개체 자체 메모리를 자동으로 할당할 수 있습니다 하거나 고유한 메모리 블록을 연결할 수 있습니다 합니다 `CSharedFile` 개체를 호출 하 여 [CSharedFile::SetHandle](#sethandle)합니다. 두 경우 모두 메모리 파일의 크기를 자동으로 증가 하는 것에 대 한 메모리에 할당 됩니다 `nGrowBytes`-경우 증가 크기 `nGrowBytes` 0이 아닙니다.

자세한 내용은 문서를 참조 [MFC의 파일](../../mfc/files-in-mfc.md) 및 [파일 처리](../../c-runtime-library/file-handling.md) 에 *런타임 라이브러리 참조*합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

[CMemFile](../../mfc/reference/cmemfile-class.md)

`CSharedFile`

## <a name="requirements"></a>요구 사항

**헤더:** afxadv.h

##  <a name="csharedfile"></a>  CSharedFile::CSharedFile

생성 된 `CSharedFile` 개체 및 메모리를 할당 합니다.

```
CSharedFile(
    UINT nAllocFlags = GMEM_DDESHARE | GMEM_MOVEABLE,
    UINT nGrowBytes = 4096);
```

### <a name="parameters"></a>매개 변수

*nAllocFlags*<br/>
메모리 할당 되는 방식을 나타내는 플래그입니다. 참조 [GlobalAlloc](/windows/desktop/api/winbase/nf-winbase-globalalloc) 올바른 플래그 값의 목록은 합니다.

*nGrowBytes*<br/>
메모리 할당 바이트에서 증가 합니다.

##  <a name="detach"></a>  CSharedFile::Detach

메모리 파일을 닫고 메모리 블록에서 분리 하려면이 함수를 호출 합니다.

```
HGLOBAL Detach();
```

### <a name="return-value"></a>반환 값

메모리 파일의 내용을 포함 하는 메모리 블록의 핸들입니다.

### <a name="remarks"></a>설명

호출 하 여 다시 열 수 있습니다 [SetHandle](#sethandle)에서 반환 된 핸들을 사용 하 여 **분리**합니다.

##  <a name="sethandle"></a>  CSharedFile::SetHandle

전역 메모리의 블록을 연결 하려면이 함수를 호출 합니다 `CSharedFile` 개체입니다.

```
void SetHandle(
    HGLOBAL hGlobalMemory,
    BOOL bAllowGrow = TRUE);
```

### <a name="parameters"></a>매개 변수

*hGlobalMemory*<br/>
에 연결 되는 전역 메모리에 대 한 핸들을 `CSharedFile`입니다.

*bAllowGrow*<br/>
메모리 블록을 증가할 수 있는지 여부를 지정 합니다.

### <a name="remarks"></a>설명

하는 경우 *bAllowGrow* 파일에서 메모리 블록에 할당 된 것 보다 더 많은 바이트를 쓸 0이 아닌 경우 메모리 블록의 크기 증가 필요할 경우, 예를 들어, 시도 하는 경우 수행 됩니다.

## <a name="see-also"></a>참고자료

[CMemFile 클래스](../../mfc/reference/cmemfile-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CMemFile 클래스](../../mfc/reference/cmemfile-class.md)
