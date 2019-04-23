---
title: IConvertTypeImpl 클래스
ms.date: 11/04/2016
f1_keywords:
- ATL.IConvertTypeImpl<T>
- IConvertTypeImpl
- ATL.IConvertTypeImpl
- ATL::IConvertTypeImpl
- ATL::IConvertTypeImpl<T>
- IConvertTypeImpl.CanConvert
- CanConvert
- IConvertTypeImpl::CanConvert
helpviewer_keywords:
- IConvertTypeImpl class
- CanConvert method
ms.assetid: 7f81e79e-7d3f-4cbe-b93c-d632a94b15f6
ms.openlocfilehash: 546a5a007f9e4c1c2a0e581eff2e7984947bdbb5
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59023726"
---
# <a name="iconverttypeimpl-class"></a>IConvertTypeImpl 클래스

구현을 제공 합니다 [IConvertType](/previous-versions/windows/desktop/ms715926(v=vs.85)) 인터페이스입니다.

## <a name="syntax"></a>구문

```cpp
template <class T>
class ATL_NO_VTABLE IConvertTypeImpl
   : public IConvertType, public CConvertHelper
```

### <a name="parameters"></a>매개 변수

*T*<br/>
클래스에서 파생 된 `IConvertTypeImpl`합니다.

## <a name="requirements"></a>요구 사항

**헤더:** atldb.h

## <a name="members"></a>멤버

### <a name="interface-methods"></a>인터페이스 메서드

|||
|-|-|
|[CanConvert](#canconvert)|명령 또는 행 집합에서 형식 변환의 가용성에 대 한 정보를 제공합니다.|

## <a name="remarks"></a>설명

이 인터페이스는 명령, 행 집합 및 인덱스 행 집합에 필수입니다. `IConvertTypeImpl` OLE DB에서 제공 된 변환 개체에 위임 하 여 인터페이스를 구현 합니다.

## <a name="canconvert"></a> IConvertTypeImpl::CanConvert

명령 또는 행 집합에서 형식 변환의 가용성에 대 한 정보를 제공합니다.

### <a name="syntax"></a>구문

```cpp
STDMETHOD(CanConvert)(DBTYPE wFromType,
   DBTYPE wToType,
   DBCONVERTFLAGS dwConvertFlags);
```

#### <a name="parameters"></a>매개 변수

참조 [IConvertType::CanConvert](/previous-versions/windows/desktop/ms711224(v=vs.85)) 에 *OLE DB Programmer's Reference*합니다.

### <a name="remarks"></a>설명

OLE DB 데이터 변환을 사용 하 여 `MSADC.DLL`입니다.

## <a name="see-also"></a>참고자료

[OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)