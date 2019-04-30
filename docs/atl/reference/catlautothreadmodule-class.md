---
title: CAtlAutoThreadModule 클래스
ms.date: 11/04/2016
f1_keywords:
- CAtlAutoThreadModule
- atlbase/ATL::CAtlAutoThreadModule
helpviewer_keywords:
- CAtlAutoThreadModule class
ms.assetid: 3be834aa-55ef-403e-94ae-41979691b15f
ms.openlocfilehash: 1ec66bf77d8dd705cb2e1e93f70a885ab96420a6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62247299"
---
# <a name="catlautothreadmodule-class"></a>CAtlAutoThreadModule 클래스

이 클래스는 스레드 풀 아파트 모델 COM 서버를 구현합니다.

> [!IMPORTANT]
> 이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
class CAtlAutoThreadModule : public CAtlAutoThreadModuleT<CAtlAutoThreadModule>
```

## <a name="remarks"></a>설명

`CAtlAutoThreadModule` 파생 [CAtlAutoThreadModuleT](../../atl/reference/catlautothreadmodulet-class.md) 스레드 풀링, 아파트 모델 COM 서버를 구현 합니다. `CAtlAutoThreadModule` 사용 하 여 [CComApartment](../../atl/reference/ccomapartment-class.md) 모듈에서 각 스레드에 대 한 아파트를 관리 합니다.

사용 해야 합니다는 [DECLARE_CLASSFACTORY_AUTO_THREAD](aggregation-and-class-factory-macros.md#declare_classfactory_auto_thread) 지정 하 여 개체의 클래스 정의에서 매크로 [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md) 클래스 팩터리로 합니다. 파생 된 클래스의 단일 인스턴스를 추가 해야 `CAtlAutoThreadModuleT` 와 같은 `CAtlAutoThreadModule`합니다. 예를 들어:

`CAtlAutoThreadModule _AtlAutoModule; // name is immaterial.`

> [!NOTE]
> 이 클래스는 사용 되지 않는 대체 [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md) 클래스입니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`IAtlAutoThreadModule`

[CAtlAutoThreadModuleT](../../atl/reference/catlautothreadmodulet-class.md)

`CAtlAutoThreadModule`

## <a name="requirements"></a>요구 사항

**헤더:** atlbase.h

## <a name="see-also"></a>참고자료

[CAtlAutoThreadModuleT 클래스](../../atl/reference/catlautothreadmodulet-class.md)<br/>
[IAtlAutoThreadModule 클래스](../../atl/reference/iatlautothreadmodule-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)<br/>
[모듈 클래스](../../atl/atl-module-classes.md)
