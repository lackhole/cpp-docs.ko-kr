---
title: WinModule 전역 함수
ms.date: 11/04/2016
f1_keywords:
- atlbase/ATL::AtlWinModuleAddCreateWndData
- atlbase/ATL::AtlWinModuleExtractCreateWndData
ms.assetid: 8ce45a5b-26a7-491f-9096-c09ceca5f2c2
ms.openlocfilehash: 0e7450ea2a42c0b35dc5a6d1b77dfb0f2acb9520
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62196861"
---
# <a name="winmodule-global-functions"></a>WinModule 전역 함수

이러한 함수에 대 한 지원 `_AtlCreateWndData` 작업을 구성 합니다.

> [!IMPORTANT]
> 다음 표에 나열 된 함수를 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

|||
|-|-|
|[AtlWinModuleAddCreateWndData](#atlwinmoduleaddcreatewnddata)|이 함수는 `_AtlCreateWndData` 구조를 초기화하고 추가하는 데 사용됩니다.|
|[AtlWinModuleExtractCreateWndData](#atlwinmoduleextractcreatewnddata)|기존 `_AtlCreateWndData` 구조를 추출하려면 이 함수를 호출합니다.|

## <a name="requirements"></a>요구 사항

**헤더:** atlbase.h

##  <a name="atlwinmoduleaddcreatewnddata"></a>  AtlWinModuleAddCreateWndData

이 함수는 `_AtlCreateWndData` 구조를 초기화하고 추가하는 데 사용됩니다.

```
ATLINLINE ATLAPI_(void) AtlWinModuleAddCreateWndData(
    _ATL_WIN_MODULE* pWinModule,
    _AtlCreateWndData* pData,
    void* pObject);
```

### <a name="parameters"></a>매개 변수

*pWinModule*<br/>
모듈의에 대 한 포인터 [_ATL_WIN_MODULE70](../../atl/reference/atl-win-module70-structure.md) 구조입니다.

*pData*<br/>
에 대 한 포인터를 [_AtlCreateWndData](../../atl/reference/atlcreatewnddata-structure.md) 구조를 초기화 하 고 현재 모듈에 추가 합니다.

*pObject*<br/>
개체에 대 한 포인터 **이** 포인터입니다.

### <a name="remarks"></a>설명

초기화를 `_AtlCreateWndData` 구조를 저장 하는 데 사용 되는 합니다 **이** 포인터가 클래스 인스턴스를 참조 하는 데 사용 하 고 모듈의 참조 목록에 추가 `_ATL_WIN_MODULE70` 구조입니다. 호출한 [CAtlWinModule::AddCreateWndData](catlwinmodule-class.md#addcreatewnddata)합니다.

##  <a name="atlwinmoduleextractcreatewnddata"></a>  AtlWinModuleExtractCreateWndData

기존 `_AtlCreateWndData` 구조를 추출하려면 이 함수를 호출합니다.

```
ATLINLINE ATLAPI_(void*) AtlWinModuleExtractCreateWndData(_ATL_WIN_MODULE* pWinModule);
```

### <a name="parameters"></a>매개 변수

*pWinModule*<br/>
모듈의에 대 한 포인터 [_ATL_WIN_MODULE70](../../atl/reference/atl-win-module70-structure.md) 구조입니다.

### <a name="return-value"></a>반환 값

에 대 한 포인터를 반환 합니다 [_AtlCreateWndData](../../atl/reference/atlcreatewnddata-structure.md) 구조입니다.

### <a name="remarks"></a>설명

이 함수는 기존 추출 `_AtlCreateWndData` 모듈의 참조 목록에서 구조 `_ATL_WIN_MODULE70` 구조입니다.

## <a name="see-also"></a>참고자료

[함수](../../atl/reference/atl-functions.md)
