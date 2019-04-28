---
title: _ATL_MODULE70 구조체
ms.date: 11/04/2016
f1_keywords:
- _ATL_MODULE70
- ATL::_ATL_MODULE70
- ATL._ATL_MODULE70
helpviewer_keywords:
- ATL_MODULE70 structure
- _ATL_MODULE70 structure
ms.assetid: b059b2c8-dfd1-4ac9-b07d-39df638cc7b3
ms.openlocfilehash: d05683383fab64f027f198d49bfbf42aa593d582
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62260924"
---
# <a name="atlmodule70-structure"></a>_ATL_MODULE70 구조체

모든 ATL 모듈에 의해 사용 되는 데이터를 포함 합니다.

## <a name="syntax"></a>구문

```
struct _ATL_MODULE70 {
    UINT cbSize;
    LONG m_nLockCnt;
    _ATL_TERMFUNC_ELEM* m_pTermFuncs;
    CComCriticalSection m_csStaticDataInitAndTypeInfo;
};
```

## <a name="members"></a>멤버

`cbSize`<br/>
버전 관리에 사용 되는 구조체의 크기입니다.

`m_nLockCnt`<br/>
모듈을 활성 상태로 유지 해야 기간을 확인 하려면 참조 횟수입니다.

`m_pTermFuncs`<br/>
ATL 종료 될 때 호출할에 등록 된 추적 함수입니다.

`m_csStaticDataInitAndTypeInfo`<br/>
다중 스레드 상황에서 내부 데이터에 대 한 액세스를 조정 하는 데 사용 합니다.

## <a name="remarks"></a>설명

[_ATL_MODULE](atl-typedefs.md#_atl_module) 의 typedef로 정의 된 `_ATL_MODULE70`합니다.

## <a name="requirements"></a>요구 사항

**헤더:** atlbase.h

## <a name="see-also"></a>참고자료

[클래스 및 구조체](../../atl/reference/atl-classes.md)
