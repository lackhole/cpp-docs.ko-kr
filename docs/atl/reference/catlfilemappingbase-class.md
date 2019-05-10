---
title: CAtlFileMappingBase 클래스
ms.date: 11/04/2016
f1_keywords:
- CAtlFileMappingBase
- ATLFILE/ATL::CAtlFileMappingBase
- ATLFILE/ATL::CAtlFileMappingBase::CAtlFileMappingBase
- ATLFILE/ATL::CAtlFileMappingBase::CopyFrom
- ATLFILE/ATL::CAtlFileMappingBase::GetData
- ATLFILE/ATL::CAtlFileMappingBase::GetHandle
- ATLFILE/ATL::CAtlFileMappingBase::GetMappingSize
- ATLFILE/ATL::CAtlFileMappingBase::MapFile
- ATLFILE/ATL::CAtlFileMappingBase::MapSharedMem
- ATLFILE/ATL::CAtlFileMappingBase::OpenMapping
- ATLFILE/ATL::CAtlFileMappingBase::Unmap
helpviewer_keywords:
- CAtlFileMappingBase class
ms.assetid: be555723-2790-4f57-a8fb-be4d68460775
ms.openlocfilehash: d31bc72e485fbb15ed595a7c777c3685a00865c4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62260346"
---
# <a name="catlfilemappingbase-class"></a>CAtlFileMappingBase 클래스

이 클래스는 메모리 매핑된 파일을 나타냅니다.

> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
class CAtlFileMappingBase
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CAtlFileMappingBase::CAtlFileMappingBase](#catlfilemappingbase)|생성자입니다.|
|[CAtlFileMappingBase::~CAtlFileMappingBase](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CAtlFileMappingBase::CopyFrom](#copyfrom)|파일 매핑 개체에서 복사 하는이 메서드를 호출 합니다.|
|[CAtlFileMappingBase::GetData](#getdata)|파일 매핑 개체에서 데이터를 가져오려면이 메서드를 호출 합니다.|
|[CAtlFileMappingBase::GetHandle](#gethandle)|파일 핸들을 반환 하려면이 메서드를 호출 합니다.|
|[CAtlFileMappingBase::GetMappingSize](#getmappingsize)|파일 매핑 개체에서 매핑 크기를 가져오려면이 메서드를 호출 합니다.|
|[CAtlFileMappingBase::MapFile](#mapfile)|파일 매핑 개체를 만들려면이 메서드를 호출 합니다.|
|[CAtlFileMappingBase::MapSharedMem](#mapsharedmem)|모든 프로세스에 대 한 전체 액세스를 허용 하는 파일 매핑 개체를 만들려면이 메서드를 호출 합니다.|
|[CAtlFileMappingBase::OpenMapping](#openmapping)|파일 매핑 개체에 대 한 핸들을 반환 하려면이 메서드를 호출 합니다.|
|[CAtlFileMappingBase::Unmap](#unmap)|파일 매핑 개체 매핑을 해제 하려면이 메서드를 호출 합니다.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[CAtlFileMappingBase::operator =](#operator_eq)|다른 파일 매핑 개체에 현재 파일 매핑 개체를 설정합니다.|

## <a name="remarks"></a>설명

파일 매핑 프로세스의 가상 주소 공간 부분과 파일 내용 연결 하는 것입니다. 이 클래스는 쉽게 액세스 하 여 데이터를 공유 하는 프로그램을 허용 하는 파일 매핑 개체를 만들기 위한 메서드를 제공 합니다.

자세한 내용은 [파일 매핑](/windows/desktop/Memory/file-mapping) Windows SDK에 있습니다.

## <a name="requirements"></a>요구 사항

**헤더:** atlfile.h

##  <a name="catlfilemappingbase"></a>  CAtlFileMappingBase::CAtlFileMappingBase

생성자입니다.

```
CAtlFileMappingBase(CAtlFileMappingBase& orig);
CAtlFileMappingBase() throw();
```

### <a name="parameters"></a>매개 변수

*orig*<br/>
새 개체 만들기를 복사할 원본 파일 매핑 개체입니다.

### <a name="remarks"></a>설명

필요에 따라 기존 개체를 사용 하 여 새 파일 매핑 개체를 만듭니다. 호출 하는 데 여전히 필요한 것 [CAtlFileMappingBase::MapFile](#mapfile) 특정 파일에 대 한 파일 매핑 개체를 만들거나 열 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#71](../../atl/codesnippet/cpp/catlfilemappingbase-class_1.cpp)]

##  <a name="dtor"></a>  CAtlFileMappingBase::~CAtlFileMappingBase

소멸자입니다.

```
~CAtlFileMappingBase() throw();
```

### <a name="remarks"></a>설명

클래스 및 호출에 의해 할당 된 모든 리소스를 해제 합니다 [CAtlFileMappingBase::Unmap](#unmap) 메서드.

##  <a name="copyfrom"></a>  CAtlFileMappingBase::CopyFrom

파일 매핑 개체에서 복사 하는이 메서드를 호출 합니다.

```
HRESULT CopyFrom(CAtlFileMappingBase& orig) throw();
```

### <a name="parameters"></a>매개 변수

*orig*<br/>
복사할 원본 파일 매핑 개체입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

##  <a name="getdata"></a>  CAtlFileMappingBase::GetData

파일 매핑 개체에서 데이터를 가져오려면이 메서드를 호출 합니다.

```
void* GetData() const throw();
```

### <a name="return-value"></a>반환 값

데이터에 대 한 포인터를 반환합니다.

##  <a name="gethandle"></a>  CAtlFileMappingBase::GetHandle

파일 매핑 개체에 대 한 핸들을 반환 하려면이 메서드를 호출 합니다.

```
HANDLE GetHandle() throw ();
```

### <a name="return-value"></a>반환 값

파일 매핑 개체에 대 한 핸들을 반환합니다.

##  <a name="getmappingsize"></a>  CAtlFileMappingBase::GetMappingSize

파일 매핑 개체에서 매핑 크기를 가져오려면이 메서드를 호출 합니다.

```
SIZE_T GetMappingSize() throw();
```

### <a name="return-value"></a>반환 값

매핑 크기를 반환합니다.

### <a name="example"></a>예제

예를 참조 하세요 [CAtlFileMappingBase::CAtlFileMappingBase](#catlfilemappingbase)합니다.

##  <a name="mapfile"></a>  CAtlFileMappingBase::MapFile

지정된 된 파일에 대 한 파일 매핑 개체를 만들거나 열에이 메서드를 호출 합니다.

```
HRESULT MapFile(
    HANDLE hFile,
    SIZE_T nMappingSize = 0,
    ULONGLONG nOffset = 0,
    DWORD dwMappingProtection = PAGE_READONLY,
    DWORD dwViewDesiredAccess = FILE_MAP_READ) throw();
```

### <a name="parameters"></a>매개 변수

*hFile*<br/>
매핑 개체를 만드는 데 사용할 파일에 대 한 핸들입니다. *hFile* 유효 해야 하며 INVALID_HANDLE_VALUE로 설정할 수 없습니다.

*nMappingSize*<br/>
매핑 크기입니다. 파일 매핑 개체의 최대 크기는 구분 파일의 현재 크기와 같은 0 인 경우 *hFile 합니다.*

*nOffset*<br/>
시작 하려면 매핑 인 파일 오프셋입니다. 오프셋된 값을 시스템의 메모리 할당 세분성의 배수 여야 합니다.

*dwMappingProtection*<br/>
파일을 매핑할 때 파일 보기에 대 한 필요한 보호 합니다. 참조 *flProtect* 에 [CreateFileMapping](/windows/desktop/api/winbase/nf-winbase-createfilemappinga) Windows SDK에 있습니다.

*dwViewDesiredAccess*<br/>
파일 보기 및 따라서 파일에서 매핑된 페이지 보호에 대 한 액세스 형식을 지정 합니다. 참조 *dwDesiredAccess* 에 [mapviewoffileex가](/windows/desktop/api/memoryapi/nf-memoryapi-mapviewoffileex) Windows SDK에 있습니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

### <a name="remarks"></a>설명

파일 매핑 개체;의 크기는 파일 매핑 개체를 만든 후 파일의 크기를 초과할 수 없습니다. 이 경우 파일의 내용 중 일부만 공유를 위해 제공 됩니다. 자세한 내용은 참조 하세요. [CreateFileMapping](/windows/desktop/api/winbase/nf-winbase-createfilemappinga) 하 고 [mapviewoffileex가](/windows/desktop/api/memoryapi/nf-memoryapi-mapviewoffileex) Windows sdk에서입니다.

### <a name="example"></a>예제

예를 참조 하세요 [CAtlFileMappingBase::CAtlFileMappingBase](#catlfilemappingbase)합니다.

##  <a name="mapsharedmem"></a>  CAtlFileMappingBase::MapSharedMem

모든 프로세스에 대 한 전체 액세스를 허용 하는 파일 매핑 개체를 만들려면이 메서드를 호출 합니다.

```
HRESULT MapSharedMem(
    SIZE_T nMappingSize,
    LPCTSTR szName,
    BOOL* pbAlreadyExisted = NULL,
    LPSECURITY_ATTRIBUTES lpsa = NULL,
    DWORD dwMappingProtection = PAGE_READWRITE,
    DWORD dwViewDesiredAccess = FILE_MAP_ALL_ACCESS) throw();
```

### <a name="parameters"></a>매개 변수

*nMappingSize*<br/>
매핑 크기입니다. 파일 매핑 개체의 최대 크기는 식별 되는 파일 매핑 개체의 현재 크기와 같은 0 인 경우 *szName*합니다.

*szName*<br/>
매핑 개체의 이름입니다.

*pbAlreadyExisted*<br/>
가 있으면 TRUE로 설정 된 매핑 개체 이미 나타내는 부울 값을 가리키는 존재 합니다.

*lpsa*<br/>
에 대 한 포인터를 `SECURITY_ATTRIBUTES` 반환된 된 핸들이 자식 프로세스로 상속 될 수 있는지 여부를 결정 하는 구조체. 참조 *lpAttributes* 에 [CreateFileMapping](/windows/desktop/api/winbase/nf-winbase-createfilemappinga) Windows SDK에 있습니다.

*dwMappingProtection*<br/>
파일을 매핑할 때 파일 보기의 경우 필요한 보호 합니다. 참조 *flProtect* 에서 `CreateFileMapping` Windows SDK에 있습니다.

*dwViewDesiredAccess*<br/>
파일 보기 및 따라서 파일에서 매핑된 페이지 보호에 대 한 액세스 형식을 지정 합니다. 참조 *dwDesiredAccess* 에 [mapviewoffileex가](/windows/desktop/api/memoryapi/nf-memoryapi-mapviewoffileex) Windows SDK에 있습니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

### <a name="remarks"></a>설명

`MapShareMem` 만든 기존 파일 매핑 개체를 사용 하면 [CreateFileMapping](/windows/desktop/api/winbase/nf-winbase-createfilemappinga)를 프로세스 간에 공유할 수 있습니다.

##  <a name="openmapping"></a>  CAtlFileMappingBase::OpenMapping

지정된 된 파일에 대 한 명명 된 파일 매핑 개체를이 메서드를 호출 합니다.

```
HRESULT OpenMapping(
    LPCTSTR szName,
    SIZE_T nMappingSize,
    ULONGLONG nOffset = 0,
    DWORD dwViewDesiredAccess = FILE_MAP_ALL_ACCESS) throw();
```

### <a name="parameters"></a>매개 변수

*szName*<br/>
매핑 개체의 이름입니다. 이 이름으로 파일 매핑 개체에 열린 핸들이 있고 매핑 개체의 보안 설명자를 사용 하 여 충돌 하지 않는 경우는 *dwViewDesiredAccess* 매개 변수 열기 작업이 성공 합니다.

*nMappingSize*<br/>
매핑 크기입니다. 파일 매핑 개체의 최대 크기는 식별 되는 파일 매핑 개체의 현재 크기와 같은 0 인 경우 *szName*합니다.

*nOffset*<br/>
시작 하려면 매핑 인 파일 오프셋입니다. 오프셋된 값을 시스템의 메모리 할당 세분성의 배수 여야 합니다.

*dwViewDesiredAccess*<br/>
파일 보기 및 따라서 파일에서 매핑된 페이지 보호에 대 한 액세스 형식을 지정 합니다. 참조 *dwDesiredAccess* 에 [mapviewoffileex가](/windows/desktop/api/memoryapi/nf-memoryapi-mapviewoffileex) Windows SDK에 있습니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

### <a name="remarks"></a>설명

디버그 빌드에서 입력된 매개 변수가 유효 하지 않으면 어설션 오류가 발생 합니다.

##  <a name="operator_eq"></a>  CAtlFileMappingBase::operator =

다른 파일 매핑 개체에 현재 파일 매핑 개체를 설정합니다.

```
CAtlFileMappingBase& operator=(CAtlFileMappingBase& orig);
```

### <a name="parameters"></a>매개 변수

*orig*<br/>
현재 파일 매핑 개체입니다.

### <a name="return-value"></a>반환 값

현재 개체에 대 한 참조를 반환합니다.

##  <a name="unmap"></a>  CAtlFileMappingBase::Unmap

파일 매핑 개체 매핑을 해제 하려면이 메서드를 호출 합니다.

```
HRESULT Unmap() throw();
```

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

### <a name="remarks"></a>설명

참조 [unmapviewoffile이](/windows/desktop/api/memoryapi/nf-memoryapi-unmapviewoffile) 대 한 자세한 내용은 Windows SDK에 있습니다.

## <a name="see-also"></a>참고자료

[CAtlFileMapping 클래스](../../atl/reference/catlfilemapping-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
