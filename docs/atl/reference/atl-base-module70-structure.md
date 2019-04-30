---
title: _ATL_BASE_MODULE70 구조체
ms.date: 11/04/2016
f1_keywords:
- ATL::_ATL_BASE_MODULE70
- ATL._ATL_BASE_MODULE70
- _ATL_BASE_MODULE70
helpviewer_keywords:
- ATL_BASE_MODULE70 structure
- _ATL_BASE_MODULE70 structure
ms.assetid: 4539282f-15b8-4d7c-aafa-a85dc56f4980
ms.openlocfilehash: 4fddd4b3af6155d0663b9c01edfab4fcf4a60426
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62260989"
---
# <a name="atlbasemodule70-structure"></a>_ATL_BASE_MODULE70 구조체

ATL.를 사용 하는 모든 프로젝트에서 사용

## <a name="syntax"></a>구문

```
struct _ATL_BASE_MODULE70 {
    UINT cbSize;
    HINSTANCE m_hInst;
    HINSTANCE m_hInstResource;
    bool m_bNT5orWin98;
    DWORD dwAtlBuildVer;
    GUID* pguidVer;
    CRITICAL_SECTION m_csResource;
    CSimpleArray<HINSTANCE> m_rgResourceInstance;
};
```

## <a name="members"></a>멤버

`cbSize`<br/>
버전 관리에 사용 되는 구조체의 크기입니다.

`m_hInst`<br/>
`hInstance` (exe 또는 dll)이이 모듈에 대 한 합니다.

`m_hInstResource`<br/>
기본 인스턴스 리소스 핸들입니다.

`m_bNT5orWin98`<br/>
운영 체제 버전 정보입니다. ATL.에서 내부적으로 사용

`dwAtlBuildVer`<br/>
ATL.의 버전을 저장 현재 0x0700 합니다.

`pguidVer`<br/>
ATL의 내부 GUID입니다.

`m_csResource`<br/>
에 대 한 액세스를 동기화 하는 데는 `m_rgResourceInstance` 배열입니다. ATL.에서 내부적으로 사용

`m_rgResourceInstance`<br/>
ATL은 인식 되는 모든 리소스 인스턴스에 대 한 리소스를 검색 하는 데 사용 하는 배열입니다. ATL.에서 내부적으로 사용

## <a name="remarks"></a>설명

[_ATL_BASE_MODULE](atl-typedefs.md#_atl_base_module) _ATL_BASE_MODULE70의 typedef로 정의 됩니다.

## <a name="requirements"></a>요구 사항

**헤더:** atlcore.h

## <a name="see-also"></a>참고자료

[클래스 및 구조체](../../atl/reference/atl-classes.md)
