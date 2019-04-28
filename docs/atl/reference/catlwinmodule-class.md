---
title: CAtlWinModule 클래스
ms.date: 11/04/2016
f1_keywords:
- CAtlWinModule
- ATLBASE/ATL::CAtlWinModule
- ATLBASE/ATL::CAtlWinModule::CAtlWinModule
- ATLBASE/ATL::CAtlWinModule::AddCreateWndData
- ATLBASE/ATL::CAtlWinModule::ExtractCreateWndData
helpviewer_keywords:
- CAtlWinModule class
ms.assetid: 7ec844af-0f68-4a34-b0c8-9de50a025df0
ms.openlocfilehash: d0bc98fa48f84e67ab38106dea3fe22d5ad1757d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62246826"
---
# <a name="catlwinmodule-class"></a>CAtlWinModule 클래스

이 클래스는 ATL windowing 구성 요소에 대 한 지원을 제공합니다.

> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
class CAtlWinModule : public _ATL_WIN_MODULE
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CAtlWinModule::CAtlWinModule](#catlwinmodule)|생성자입니다.|
|[CAtlWinModule::~CAtlWinModule](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CAtlWinModule::AddCreateWndData](#addcreatewnddata)|데이터 개체를 추가합니다.|
|[CAtlWinModule::ExtractCreateWndData](#extractcreatewnddata)|Window 모듈 데이터 개체에 대 한 포인터를 반환합니다.|

## <a name="remarks"></a>설명

이 클래스는 창 작업 기능을 필요로 하는 모든 ATL 클래스에 대 한 지원을 제공 합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[_ATL_WIN_MODULE](atl-typedefs.md#_atl_win_module)

`CAtlWinModule`

## <a name="requirements"></a>요구 사항

**헤더:** atlbase.h

##  <a name="addcreatewnddata"></a>  CAtlWinModule::AddCreateWndData

이 메서드를 초기화 하 고 추가 `_AtlCreateWndData` 구조입니다.

```
void AddCreateWndData(_AtlCreateWndData* pData, void* pObject);
```

### <a name="parameters"></a>매개 변수

*pData*<br/>
에 대 한 포인터를 `_AtlCreateWndData` 구조를 초기화 하 고 현재 모듈에 추가 합니다.

*pObject*<br/>
개체에 대 한 포인터 **이** 포인터입니다.

### <a name="remarks"></a>설명

이 메서드를 호출 [AtlWinModuleAddCreateWndData](winmodule-global-functions.md#atlwinmoduleaddcreatewnddata) 는 초기화 된 [_AtlCreateWndData](../../atl/reference/atlcreatewnddata-structure.md) 구조입니다. 이 구조는 저장 된 **이** 창 프로시저에서 클래스 인스턴스를 가져오는 데 포인터입니다.

##  <a name="catlwinmodule"></a>  CAtlWinModule::CAtlWinModule

생성자입니다.

```
CAtlWinModule();
```

### <a name="remarks"></a>설명

초기화에 실패 하면를 **EXCEPTION_NONCONTINUABLE** 예외가 발생 합니다.

##  <a name="dtor"></a>  CAtlWinModule::~CAtlWinModule

소멸자입니다.

```
~CAtlWinModule();
```

### <a name="remarks"></a>설명

할당 된 모든 리소스를 해제합니다.

##  <a name="extractcreatewnddata"></a>  CAtlWinModule::ExtractCreateWndData

이 메서드가 반환에 대 한 포인터는 `_AtlCreateWndData` 구조입니다.

```
void* ExtractCreateWndData();
```

### <a name="return-value"></a>반환 값

에 대 한 포인터를 반환 합니다 `_AtlCreateWndData` 구조를 사용 하 여 이전에 추가한 [CAtlWinModule::AddCreateWndData](#addcreatewnddata), 또는 개체가 사용할 수 없으면 NULL.

## <a name="see-also"></a>참고자료

[_ATL_WIN_MODULE](atl-typedefs.md#_atl_win_module)<br/>
[클래스 개요](../../atl/atl-class-overview.md)<br/>
[모듈 클래스](../../atl/atl-module-classes.md)
