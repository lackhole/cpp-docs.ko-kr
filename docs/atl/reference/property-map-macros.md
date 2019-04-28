---
title: 속성 맵 매크로
ms.date: 11/04/2016
f1_keywords:
- atlcom/ATL::BEGIN_PROP_MAP
- atlcom/ATL::PROP_DATA_ENTRY
- atlcom/ATL::PROP_ENTRY_TYPE
- atlcom/ATL::PROP_ENTRY_TYPE_EX
- atlcom/ATL::PROP_PAGE
- atlcom/ATL::END_PROP_MAP
helpviewer_keywords:
- property maps
ms.assetid: 128bc742-2b98-4b97-a243-684dbb83db77
ms.openlocfilehash: 1e2e7235dd924467d9d5e0613a704fedf8340ae4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62197270"
---
# <a name="property-map-macros"></a>속성 맵 매크로

이러한 매크로 속성 맵 및 항목을 정의합니다.

|||
|-|-|
|[BEGIN_PROP_MAP](#begin_prop_map)|ATL 속성 맵에의 시작을 표시 합니다.|
|[PROP_DATA_ENTRY](#prop_data_entry)|범위 또는 ActiveX 컨트롤의 크기를 나타냅니다.|
|[PROP_ENTRY_TYPE](#prop_entry_type)|속성 맵에 속성 설명, DISPID, 속성 및 속성 페이지 CLSID를 입력합니다.|
|[PROP_ENTRY_TYPE_EX](#prop_entry_type_ex)|속성 설명을 DISPID, CLSID, 속성 페이지 속성을 입력 하 고 `IDispatch` 속성 맵에 대 한 IID입니다.|
|[PROP_PAGE](#prop_page)|속성 맵의에 속성 페이지 CLSID를 입력합니다.|
|[END_PROP_MAP](#end_prop_map)|ATL 속성 map의 끝을 표시합니다.|

## <a name="requirements"></a>요구 사항

**헤더:** atlcom.h

##  <a name="begin_prop_map"></a>  BEGIN_PROP_MAP

개체의 속성 맵에의 시작을 표시 합니다.

```
BEGIN_PROP_MAP(theClass)
```

### <a name="parameters"></a>매개 변수

*theClass*<br/>
[in] 속성이 지도 포함 하는 클래스를 지정 합니다.

### <a name="remarks"></a>설명

속성 맵의 속성 설명 속성 Dispid, Clsid, 속성 페이지를 저장 하 고 `IDispatch` Iid입니다. 클래스 [IPerPropertyBrowsingImpl](../../atl/reference/iperpropertybrowsingimpl-class.md)를 [IPersistPropertyBagImpl](../../atl/reference/ipersistpropertybagimpl-class.md)하십시오 [IPersistStreamInitImpl](../../atl/reference/ipersiststreaminitimpl-class.md), 및 [ISpecifyPropertyPagesImpl](../../atl/reference/ispecifypropertypagesimpl-class.md)속성 맵을 사용 하 여 검색 하 고이 정보를 설정 합니다.

ATL 프로젝트 마법사를 사용 하 여 개체를 만들 때 만들어집니다는 빈 속성 맵에 BEGIN_PROP_MAP 뒤를 지정 하 여 [END_PROP_MAP](#end_prop_map)합니다.

없는 범위 해야 하므로 개체는 속성 맵을 사용 하 여이 사용자 인터페이스가 있을 수 있으므로 BEGIN_PROP_MAP 속성 맵의 익스텐트 (차원) 저장 하지 않습니다. 개체는 사용자 인터페이스를 사용 하 여 ActiveX 컨트롤 인 경우 익스텐트가 있습니다. 이 경우 지정 해야 합니다 [PROP_DATA_ENTRY](#prop_data_entry) 속성 맵에 범위를 제공 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Windowing#103](../../atl/codesnippet/cpp/property-map-macros_1.h)]

##  <a name="prop_data_entry"></a>  PROP_DATA_ENTRY

범위 또는 ActiveX 컨트롤의 크기를 나타냅니다.

```
PROP_DATA_ENTRY( szDesc, member, vt)
```

### <a name="parameters"></a>매개 변수

*szDesc*<br/>
[in] 속성 설명입니다.

*member*<br/>
[in] 범위; 포함 된 데이터 멤버 예를 들어 `m_sizeExtent`합니다.

*vt*<br/>
[in] VARIANT 형식의 속성을 지정합니다.

### <a name="remarks"></a>설명

이 매크로 사용 하면 지정된 된 데이터 멤버를 유지 하려면.

마법사 속성 맵 매크로 뒤이 매크로 삽입 ActiveX 컨트롤을 만들면 [BEGIN_PROP_MAP](#begin_prop_map) 전과 속성 맵 매크로 [END_PROP_MAP](#end_prop_map)합니다.

### <a name="example"></a>예제

다음 예제에서는 개체의 범위에서에서 (`m_sizeExtent`) 유지 되 고 됩니다.

[!code-cpp[NVC_ATL_Windowing#131](../../atl/codesnippet/cpp/property-map-macros_2.h)]

[!code-cpp[NVC_ATL_Windowing#132](../../atl/codesnippet/cpp/property-map-macros_3.h)]

##  <a name="prop_entry_type"></a>  PROP_ENTRY_TYPE

이 매크로 사용 하 여 개체의 속성 맵에 속성 설명, DISPID, 속성 및 속성 페이지 CLSID를 입력 합니다.

```
PROP_ENTRY_TYPE( szDesc, dispid, clsid, vt)
```

### <a name="parameters"></a>매개 변수

*szDesc*<br/>
[in] 속성 설명입니다.

*dispid*<br/>
[in] 속성의 DISPID입니다.

*clsid*<br/>
[in] 연결된 속성 페이지의 CLSID입니다. 연결된 속성 페이지를 하지 않은 속성에 대 한 특수 값 CLSID_NULL를 사용 합니다.

*vt*<br/>
[in] 속성의 형식입니다.

### <a name="remarks"></a>설명

PROP_ENTRY 매크로 안전 하지 않은 기능과 사용 되지 않는 경우 PROP_ENTRY_TYPE를 사용 하 여 대체 되었습니다.

합니다 [BEGIN_PROP_MAP](#begin_prop_map) 속성 맵에의 시작을 표시 하는 매크로, [END_PROP_MAP](#end_prop_map) 매크로 끝을 표시 합니다.

### <a name="example"></a>예제

예를 참조 하세요 [BEGIN_PROP_MAP](#begin_prop_map)합니다.

##  <a name="prop_entry_type_ex"></a>  PROP_ENTRY_TYPE_EX

비슷합니다 [PROP_ENTRY_TYPE](#prop_entry_type), 개체가 여러 개의 이중 인터페이스를 지 원하는 경우에 특정 IID를 지정할 수 있습니다.

```
PROP_ENTRY_TYPE_EX( szDesc, dispid, clsid, iidDispatch, vt)
```

### <a name="parameters"></a>매개 변수

*szDesc*<br/>
[in] 속성 설명입니다.

*dispid*<br/>
[in] 속성의 DISPID입니다.

*clsid*<br/>
[in] 연결된 속성 페이지의 CLSID입니다. 연결된 속성 페이지를 하지 않은 속성에 대 한 특수 값 CLSID_NULL를 사용 합니다.

*iidDispatch*<br/>
[in] 속성을 정의 하는 이중 인터페이스의 IID입니다.

*vt*<br/>
[in] 속성의 형식입니다.

### <a name="remarks"></a>설명

PROP_ENTRY_EX 매크로 안전 하지 않은 기능과 사용 되지 않는 경우 PROP_ENTRY_TYPE_EX를 사용 하 여 대체 되었습니다.

합니다 [BEGIN_PROP_MAP](#begin_prop_map) 속성 맵에의 시작을 표시 하는 매크로, [END_PROP_MAP](#end_prop_map) 매크로 끝을 표시 합니다.

### <a name="example"></a>예제

다음 예제에서는 그룹에 대 한 항목이 `IMyDual1` 뒤에 대 한 항목이 `IMyDual2`합니다. 이중 인터페이스에 의해 그룹화에는 성능이 향상 됩니다.

[!code-cpp[NVC_ATL_Windowing#133](../../atl/codesnippet/cpp/property-map-macros_4.h)]

##  <a name="prop_page"></a>  PROP_PAGE

이 매크로 사용 하 여 개체의 속성 맵에 CLSID 속성 페이지를 입력 합니다.

```
PROP_PAGE(clsid)
```

### <a name="parameters"></a>매개 변수

*clsid*<br/>
[in] 속성 페이지의 CLSID입니다.

### <a name="remarks"></a>설명

PROP_PAGE 비슷합니다 [PROP_ENTRY_TYPE](#prop_entry_type), 하지만 속성 설명 또는 DISPID를 필요 하지 않습니다.

> [!NOTE]
>  CLSID PROP_ENTRY_TYPE 사용 하 여 이미 입력 한 경우 또는 [PROP_ENTRY_TYPE_EX](#prop_entry_type_ex), PROP_PAGE 사용 하 여 추가 항목을 확인 해야 합니다.

합니다 [BEGIN_PROP_MAP](#begin_prop_map) 속성 맵에의 시작을 표시 하는 매크로, [END_PROP_MAP](#end_prop_map) 매크로 끝을 표시 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Windowing#134](../../atl/codesnippet/cpp/property-map-macros_5.h)]

##  <a name="end_prop_map"></a>  END_PROP_MAP

개체의 속성 map의 끝을 표시 합니다.

```
END_PROP_MAP()
```

### <a name="remarks"></a>설명

ATL 프로젝트 마법사를 사용 하 여 개체를 만들 때 만들어집니다 빈 속성 지도 지정 하 여 [BEGIN_PROP_MAP](#begin_prop_map) END_PROP_MAP 옵니다.

### <a name="example"></a>예제

예를 참조 하세요 [BEGIN_PROP_MAP](#begin_prop_map)합니다.

## <a name="see-also"></a>참고자료

[매크로](../../atl/reference/atl-macros.md)
