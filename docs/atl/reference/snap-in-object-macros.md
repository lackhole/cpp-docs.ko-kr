---
title: 스냅인 개체 매크로
ms.date: 11/04/2016
f1_keywords:
- atlsnap/ATL::BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP
- atlsnap/ATL::BEGIN_SNAPINTOOLBARID_MAP
- atlsnap/ATL::END_EXTENSION_SNAPIN_NODEINFO_MAP
- atlsnap/ATL::END_SNAPINTOOLBARID_MAP
- atlsnap/ATL::EXTENSION_SNAPIN_DATACLASS
- atlsnap/ATL::EXTENSION_SNAPIN_NODEINFO_ENTRY
- atlsnap/ATL::SNAPINMENUID
- atlsnap/ATL::SNAPINTOOLBARID_ENTRY
ms.assetid: 4e9850c0-e395-4929-86c9-584a81828053
ms.openlocfilehash: b75dd04bed4895d722939d1bf9c0a6dfff2126e0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62276200"
---
# <a name="snap-in-object-macros"></a>스냅인 개체 매크로

이러한 매크로 확장 스냅인에 대 한 지원을 제공합니다.

|||
|-|-|
|[BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map)|스냅인 개체 스냅인 확장 데이터 클래스 map의 시작을 표시 합니다.|
|[BEGIN_SNAPINTOOLBARID_MAP](#begin_snapintoolbarid_map)|스냅인 개체의 도구 모음 맵 시작 부분을 표시합니다.|
|[END_EXTENSION_SNAPIN_NODEINFO_MAP](#end_extension_snapin_nodeinfo_map)|스냅인 개체 스냅인 확장 데이터 클래스 map의 끝을 표시합니다.|
|[END_SNAPINTOOLBARID_MAP](#end_snapintoolbarid_map)|스냅인 개체의 도구 모음 map의 끝을 표시합니다.|
|[EXTENSION_SNAPIN_DATACLASS](#extension_snapin_dataclass)|스냅인 확장의 데이터 클래스에 대 한 데이터 멤버를 만듭니다.|
|[EXTENSION_SNAPIN_NODEINFO_ENTRY](#extension_snapin_nodeinfo_entry)|스냅인 개체의 스냅인 확장 데이터 클래스 map에 스냅인 확장 데이터 클래스를 입력합니다.|
|[SNAPINMENUID](#snapinmenuid)|스냅인 개체에서 사용 하는 상황에 맞는 메뉴의 ID를 선언 합니다.|
|[SNAPINTOOLBARID_ENTRY](#snapintoolbarid_entry)|스냅인 개체의 도구 모음 지도에 도구 모음을 입력합니다.|

## <a name="requirements"></a>요구 사항

**헤더:** atlsnap.h

##  <a name="begin_extension_snapin_nodeinfo_map"></a>  BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP

스냅인 확장 데이터 클래스 map의 시작을 표시 합니다.

```
BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP(classname)
```

### <a name="parameters"></a>매개 변수

*classname*<br/>
[in] 스냅인 확장 데이터 클래스의 이름입니다.

### <a name="remarks"></a>설명

스냅인 확장 지도 BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP 매크로 사용 하 여 시작, 스냅인 확장 데이터 형식을 사용 하 여 각 항목을 추가 합니다 [EXTENSION_SNAPIN_NODEINFO_ENTRY](#extension_snapin_nodeinfo_entry) 매크로 합니다 맵으로완료[ END_EXTENSION_SNAPIN_NODEINFO_MAP](#end_extension_snapin_nodeinfo_map) 매크로입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Windowing#105](../../atl/codesnippet/cpp/snap-in-object-macros_1.h)]

##  <a name="begin_snapintoolbarid_map"></a>  BEGIN_SNAPINTOOLBARID_MAP

스냅인 개체에 대 한 도구 모음 ID 매핑 부분을 선언합니다.

```
BEGIN_SNAPINTOOLBARID_MAP(_class)
```

### <a name="parameters"></a>매개 변수

*_class*<br/>
[in] 스냅인 개체 클래스를 지정 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Windowing#106](../../atl/codesnippet/cpp/snap-in-object-macros_2.h)]

##  <a name="end_extension_snapin_nodeinfo_map"></a>  END_EXTENSION_SNAPIN_NODEINFO_MAP

스냅인 확장 데이터 클래스 map의 끝을 표시합니다.

```
END_EXTENSION_SNAPIN_NODEINFO_MAP()
```

### <a name="remarks"></a>설명

스냅인 확장 지도를 시작 합니다 [BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map) 매크로 확장 스냅인 데이터 형식을 사용 하 여 각 항목을 추가 합니다 [EXTENSION_SNAPIN_NODEINFO_ENTRY](#extension_snapin_nodeinfo_entry) 매크로 고 END_EXTENSION_SNAPIN_NODEINFO_MAP 매크로 사용 하 여 맵을 완료 합니다.

### <a name="example"></a>예제

예를 참조 하세요 [BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map)합니다.

##  <a name="end_snapintoolbarid_map"></a>  END_SNAPINTOOLBARID_MAP

스냅인 개체에 대 한 도구 모음 ID map의 끝을 선언합니다.

```
END_SNAPINTOOLBARID_MAP( _class )
```

### <a name="parameters"></a>매개 변수

*_class*<br/>
[in] 스냅인 개체 클래스를 지정 합니다.

### <a name="example"></a>예제

예를 참조 하세요 [BEGIN_SNAPINTOOLBARID_MAP](#begin_snapintoolbarid_map)합니다.

##  <a name="extension_snapin_dataclass"></a>  EXTENSION_SNAPIN_DATACLASS

스냅인 확장 데이터 클래스에 추가 하는 데이터 멤버는 **ISnapInItemImpl**-클래스를 파생 합니다.

```
EXTENSION_SNAPIN_DATACLASS(dataClass )
```

### <a name="parameters"></a>매개 변수

*dataClass*<br/>
[in] 데이터 클래스 확장 스냅인입니다.

### <a name="remarks"></a>설명

이 클래스는 스냅인 확장 데이터 클래스 map에도 입력 해야 합니다. 스냅인 확장 데이터 클래스 지도를 시작 합니다 [BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map) 매크로 스냅인 확장 데이터 형식을 사용 하 여 각 항목을 추가 합니다 [EXTENSION_SNAPIN_NODEINFO_ENTRY](#extension_snapin_nodeinfo_entry)매크로 지도를 완료 합니다 [END_EXTENSION_SNAPIN_NODEINFO_MAP](#end_extension_snapin_nodeinfo_map) 매크로입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Windowing#105](../../atl/codesnippet/cpp/snap-in-object-macros_1.h)]

##  <a name="extension_snapin_nodeinfo_entry"></a>  EXTENSION_SNAPIN_NODEINFO_ENTRY

스냅인 확장 데이터 클래스 맵을 스냅인 확장 데이터 클래스를 추가합니다.

```
EXTENSION_SNAPIN_NODEINFO_ENTRY( dataClass )
```

### <a name="parameters"></a>매개 변수

*dataClass*<br/>
[in] 데이터 클래스 확장 스냅인입니다.

### <a name="remarks"></a>설명

스냅인 확장 데이터 클래스 지도를 시작 합니다 [BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map) 매크로 각 EXTENSION_SNAPIN_NODEINFO_ENTRY 매크로 사용 하 여 스냅인 확장 데이터 형식에 대 한 항목을 추가 하 고 맵을 완료 합니다. 사용 하 여 합니다 [END_EXTENSION_SNAPIN_NODEINFO_MAP](#end_extension_snapin_nodeinfo_map) 매크로입니다.

### <a name="example"></a>예제

예를 참조 하세요 [BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map)합니다.

##  <a name="snapinmenuid"></a>  SNAPINMENUID

이 매크로 사용 하 여 스냅인 개체의 상황에 맞는 메뉴 리소스를 선언 합니다.

```
SNAPINMENUID( id )
```

### <a name="parameters"></a>매개 변수

*ID*<br/>
[in] 스냅인 개체의 상황에 맞는 메뉴를 식별합니다.

##  <a name="snapintoolbarid_entry"></a>  SNAPINTOOLBARID_ENTRY

이 매크로 사용 하 여 스냅인 개체의 도구 모음 ID 맵으로 도구 모음 ID를 입력 합니다.

```
SNAPINTOOLBARID_ENTRY( id )
```

### <a name="parameters"></a>매개 변수

*ID*<br/>
[in] 도구 모음 컨트롤을 식별합니다.

### <a name="remarks"></a>설명

합니다 [BEGIN_SNAPINTOOLBARID_MAP](#begin_snapintoolbarid_map) 도구 모음 ID 매핑의 시작을 표시 하는 매크로, [END_SNAPINTOOLBARID_MAP](#end_snapintoolbarid_map) 매크로 끝을 표시 합니다.

### <a name="example"></a>예제

예를 참조 하세요 [BEGIN_SNAPINTOOLBARID_MAP](#begin_snapintoolbarid_map)합니다.

## <a name="see-also"></a>참고자료

[매크로](../../atl/reference/atl-macros.md)
