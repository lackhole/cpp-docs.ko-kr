---
title: _ATL_COM_MODULE70 구조체
ms.date: 11/04/2016
f1_keywords:
- ATL::_ATL_COM_MODULE70
- ATL._ATL_COM_MODULE70
- _ATL_COM_MODULE70
helpviewer_keywords:
- _ATL_COM_MODULE70 structure
- ATL_COM_MODULE70 structure
ms.assetid: 5b0b2fd0-bdeb-4c7e-8870-78fa69ace6e6
ms.openlocfilehash: c6361fc5374ed732cd9ccbfbbd1d3d1c2fc8f1f0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62261041"
---
# <a name="atlcommodule70-structure"></a>_ATL_COM_MODULE70 구조체

Atl에서 COM 관련 코드에 사용

## <a name="syntax"></a>구문

```
struct _ATL_COM_MODULE70 {
    UINT cbSize;
    HINSTANCE m_hInstTypeLib;
    _ATL_OBJMAP_ENTRY** m_ppAutoObjMapFirst;
    _ATL_OBJMAP_ENTRY** m_ppAutoObjMapLast;
    CRITICAL_SECTION m_csObjMap;
};
```

## <a name="members"></a>멤버

`cbSize`<br/>
버전 관리에 사용 되는 구조체의 크기입니다.

`m_hInstTypeLib`<br/>
이 모듈에 대 한 형식 라이브러리에 핸들 인스턴스.

`m_ppAutoObjMapFirst`<br/>
이 모듈에 대 한 개체 맵 항목의 시작 부분을 나타내는 배열 요소의 주소입니다.

`m_ppAutoObjMapLast`<br/>
이 모듈에 대 한 개체 맵 항목의 끝을 나타내는 배열 요소의 주소입니다.

`m_csObjMap`<br/>
개체 맵 항목에 대 한 액세스를 serialize 할 중요 한 섹션입니다. ATL.에서 내부적으로 사용

## <a name="remarks"></a>설명

[_ATL_COM_MODULE](atl-typedefs.md#_atl_com_module) _ATL_COM_MODULE70의 typedef로 정의 됩니다.

## <a name="requirements"></a>요구 사항

**헤더:** atlbase.h

## <a name="see-also"></a>참고자료

[클래스 및 구조체](../../atl/reference/atl-classes.md)
