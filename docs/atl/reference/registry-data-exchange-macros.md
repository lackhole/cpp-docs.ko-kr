---
title: 레지스트리 데이터 교환 매크로
ms.date: 11/04/2016
f1_keywords:
- atlplus/ATL::BEGIN_RDX_MAP
- atlplus/ATL::END_RDX_MAP
- atlplus/ATL::RDX_BINARY
- atlplus/ATL::RDX_CSTRING_TEXT
- atlplus/ATL::RDX_DWORD
- atlplus/ATL::RDX_TEXT
helpviewer_keywords:
- RegistryDataExchange function, macros
ms.assetid: c1bc5e79-2307-43d2-9d10-3a62ffadf473
ms.openlocfilehash: 69b823cbcd85ebaaeb05979283ea4f8fea80f4b6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62197486"
---
# <a name="registry-data-exchange-macros"></a>레지스트리 데이터 교환 매크로

이러한 매크로 레지스트리 데이터 교환 작업을 수행 합니다.

|||
|-|-|
|[BEGIN_RDX_MAP](#begin_rdx_map)|레지스트리 데이터 교환 구조의 시작 부분을 표시합니다.|
|[END_RDX_MAP](#end_rdx_map)|레지스트리 데이터 교환 map의 끝을 표시합니다.|
|[RDX_BINARY](#rdx_binary)|BYTE 형식의 지정 된 멤버 변수를 사용 하 여 지정 된 레지스트리 항목을 연결합니다.|
|[RDX_CSTRING_TEXT](#rdx_cstring_text)|CString 형식의 지정 된 멤버 변수를 사용 하 여 지정 된 레지스트리 항목을 연결합니다.|
|[RDX_DWORD](#rdx_dword)|DWORD 형식의 지정 된 멤버 변수를 사용 하 여 지정 된 레지스트리 항목을 연결합니다.|
|[RDX_TEXT](#rdx_text)|TCHAR 형식의 지정 된 멤버 변수를 사용 하 여 지정 된 레지스트리 항목을 연결합니다.|

## <a name="requirements"></a>요구 사항

**헤더:** atlplus.h

##  <a name="begin_rdx_map"></a>  BEGIN_RDX_MAP

레지스트리 데이터 교환 구조의 시작 부분을 표시합니다.

```
BEGIN_RDX_MAP
```

### <a name="remarks"></a>설명

다음 매크로를 시스템 레지스트리에 항목을 읽고 레지스트리 데이터 교환 구조 내에서 사용 됩니다.

|매크로|설명|
|-----------|-----------------|
|[RDX_BINARY](#rdx_binary)|BYTE 형식의 지정 된 멤버 변수를 사용 하 여 지정 된 레지스트리 항목을 연결합니다.|
|[RDX_DWORD](#rdx_dword)|DWORD 형식의 지정 된 멤버 변수를 사용 하 여 지정 된 레지스트리 항목을 연결합니다.|
|[RDX_CSTRING_TEXT](#rdx_cstring_text)|CString 형식의 지정 된 멤버 변수를 사용 하 여 지정 된 레지스트리 항목을 연결합니다.|
|[RDX_TEXT](#rdx_text)|TCHAR 형식의 지정 된 멤버 변수를 사용 하 여 지정 된 레지스트리 항목을 연결합니다.|

전역 함수인 [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange), 또는 코드를 시스템 레지스트리에 간에 데이터를 교환 해야 할 때마다 BEGIN_RDX_MAP 및 END_RDX_MAP 매크로로 만들어 동일한 이름의 멤버 함수를 사용 해야 하며 RDX 맵에서 지정 된 변수입니다.

##  <a name="end_rdx_map"></a>  END_RDX_MAP

레지스트리 데이터 교환 map의 끝을 표시합니다.

```
END_RDX_MAP
```

##  <a name="rdx_binary"></a>  RDX_BINARY

BYTE 형식의 지정 된 멤버 변수를 사용 하 여 지정 된 레지스트리 항목을 연결합니다.

```
RDX_BINARY(
    rootkey,
    subkey,
    valuename,
    member,
    member_size )
```

### <a name="parameters"></a>매개 변수

*rootkey*<br/>
레지스트리 키 루트입니다.

*subkey*<br/>
레지스트리 하위 키입니다.

*valuename*<br/>
레지스트리 키입니다.

*member*<br/>
멤버 변수를 지정 된 레지스트리 항목 연결입니다.

*member_size*<br/>
멤버 변수를 바이트 단위로 크기입니다.

### <a name="remarks"></a>설명

이 매크로 멤버 변수를 지정 된 레지스트리 항목을 연결할 BEGIN_RDX_MAP 및 END_RDX_MAP 매크로와 함께에서 사용 됩니다. 전역 함수인 [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange), 또는 BEGIN_RDX_MAP 및 END_RDX_MAP 매크로로 만들어 동일한 이름의 멤버 함수는 시스템 레지스트리와 멤버 변수 간에 데이터를 교환 하는 데 사용 해야 RDX 구조의 합니다.

##  <a name="rdx_cstring_text"></a>  RDX_CSTRING_TEXT

CString 형식의 지정 된 멤버 변수를 사용 하 여 지정 된 레지스트리 항목을 연결합니다.

```
RDX_CSTRING_TEXT(
    rootkey,
    subkey,
    valuename,
    member,
    member_size )
```

### <a name="parameters"></a>매개 변수

*rootkey*<br/>
레지스트리 키 루트입니다.

*subkey*<br/>
레지스트리 하위 키입니다.

*valuename*<br/>
레지스트리 키입니다.

*member*<br/>
멤버 변수를 지정 된 레지스트리 항목 연결입니다.

*member_size*<br/>
멤버 변수를 바이트 단위로 크기입니다.

### <a name="remarks"></a>설명

이 매크로 멤버 변수를 지정 된 레지스트리 항목을 연결할 BEGIN_RDX_MAP 및 END_RDX_MAP 매크로와 함께에서 사용 됩니다. 전역 함수인 [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange), 또는 BEGIN_RDX_MAP 및 END_RDX_MAP 매크로로 만들어 동일한 이름의 멤버 함수는 시스템 레지스트리와 멤버 변수 간에 데이터를 교환 하는 데 사용 해야 RDX 구조의 합니다.

##  <a name="rdx_dword"></a>  RDX_DWORD

DWORD 형식의 지정 된 멤버 변수를 사용 하 여 지정 된 레지스트리 항목을 연결합니다.

```
RDX_DWORD(
    rootkey,
    subkey,
    valuename,
    member,
    member_size )
```

### <a name="parameters"></a>매개 변수

*rootkey*<br/>
레지스트리 키 루트입니다.

*subkey*<br/>
레지스트리 하위 키입니다.

*valuename*<br/>
레지스트리 키입니다.

*member*<br/>
멤버 변수를 지정 된 레지스트리 항목 연결입니다.

*member_size*<br/>
멤버 변수를 바이트 단위로 크기입니다.

### <a name="remarks"></a>설명

이 매크로 멤버 변수를 지정 된 레지스트리 항목을 연결할 BEGIN_RDX_MAP 및 END_RDX_MAP 매크로와 함께에서 사용 됩니다. 전역 함수인 [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange), 또는 BEGIN_RDX_MAP 및 END_RDX_MAP 매크로로 만들어 동일한 이름의 멤버 함수는 시스템 레지스트리와 멤버 변수 간에 데이터를 교환 하는 데 사용 해야 RDX 구조의 합니다.

##  <a name="rdx_text"></a>  RDX_TEXT

TCHAR 형식의 지정 된 멤버 변수를 사용 하 여 지정 된 레지스트리 항목을 연결합니다.

```
RDX_TEXT(
    rootkey,
    subkey,
    valuename,
    member,
    member_size )
```

### <a name="parameters"></a>매개 변수

*rootkey*<br/>
레지스트리 키 루트입니다.

*subkey*<br/>
레지스트리 하위 키입니다.

*valuename*<br/>
레지스트리 키입니다.

*member*<br/>
멤버 변수를 지정 된 레지스트리 항목 연결입니다.

*member_size*<br/>
멤버 변수를 바이트 단위로 크기입니다.

### <a name="remarks"></a>설명

이 매크로 멤버 변수를 지정 된 레지스트리 항목을 연결할 BEGIN_RDX_MAP 및 END_RDX_MAP 매크로와 함께에서 사용 됩니다. 전역 함수인 [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange), 또는 BEGIN_RDX_MAP 및 END_RDX_MAP 매크로로 만들어 동일한 이름의 멤버 함수는 시스템 레지스트리와 멤버 변수 간에 데이터를 교환 하는 데 사용 해야 RDX 구조의 합니다.

## <a name="see-also"></a>참고자료

[매크로](../../atl/reference/atl-macros.md)<br/>
[RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange)
