---
title: 개체 맵 매크로
ms.date: 11/04/2016
f1_keywords:
- atlcom/ATL::DECLARE_OBJECT_DESCRIPTION
- atlcom/ATL::OBJECT_ENTRY_AUTO
- atlcom/ATL::OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO
ms.assetid: 680087f4-9894-41dd-a79c-6f337e1f13c1
ms.openlocfilehash: 73dc924527bac8499adefab3d0d6b51afa500a5a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62197382"
---
# <a name="object-map-macros"></a>개체 맵 매크로

이러한 매크로 맵 개체 및 항목을 정의합니다.

|||
|-|-|
|[DECLARE_OBJECT_DESCRIPTION](#declare_object_description)|개체 맵의 입력 클래스 개체의 텍스트 설명을 지정할 수 있습니다.|
|[OBJECT_ENTRY_AUTO](#object_entry_auto)|개체 맵의에 ATL 개체를 입력 하 고 레지스트리를 업데이트 합니다. 개체의 인스턴스를 만듭니다.|
|[OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](#object_entry_non_createable_ex_auto)|개체를 등록하고 초기화해야 하지만 `CoCreateInstance`를 통해 외부적으로 생성할 수 없도록 지정할 수 있습니다.|

## <a name="requirements"></a>요구 사항

**헤더:** atlcom.h

##  <a name="declare_object_description"></a>  DECLARE_OBJECT_DESCRIPTION

클래스 개체에 대 한 텍스트 설명을 지정할 수 있습니다.

```
DECLARE_OBJECT_DESCRIPTION( x )
```

### <a name="parameters"></a>매개 변수

*x*<br/>
[in] 클래스 개체의 설명입니다.

### <a name="remarks"></a>설명

ATL을 통해 개체 맵에이 설명을 입력 합니다 [OBJECT_ENTRY_AUTO](#object_entry_auto) 매크로입니다.

DECLARE_OBJECT_DESCRIPTION 구현 하는 `GetObjectDescription` 함수를 재정의 하는 데 사용할 수 있는 합니다 [CComCoClass::GetObjectDescription](ccomcoclass-class.md#getobjectdescription) 메서드.

합니다 `GetObjectDescription` 함수는 호출한 `IComponentRegistrar::GetComponents`합니다. `IComponentRegistrar` 등록 및 DLL의 개별 구성 요소를 등록 취소할 수 있는 자동화 인터페이스가입니다. ATL 프로젝트 마법사를 사용 하 여 구성 요소 등록자 개체를 만들 때 마법사는 자동으로 구현 된 `IComponentRegistrar` 인터페이스입니다. `IComponentRegistrar` Microsoft Transaction Server에서 주로 사용 됩니다.

ATL 프로젝트 마법사에 대 한 자세한 내용은 문서 참조 [ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Windowing#123](../../atl/codesnippet/cpp/object-map-macros_1.h)]

##  <a name="object_entry_auto"></a>  OBJECT_ENTRY_AUTO

개체 맵의에 ATL 개체를 입력 하 고 레지스트리를 업데이트 합니다. 개체의 인스턴스를 만듭니다.

```
OBJECT_ENTRY_AUTO( clsid, class )
```

### <a name="parameters"></a>매개 변수

*clsid*<br/>
[in] 구현한 COM 클래스의 CLSID는 C++ 라는 클래스 *클래스*합니다.

*class*<br/>
[in] 이름을 합니다 C++ 가 나타내는 COM 클래스를 구현 하는 클래스 *clsid*합니다.

### <a name="remarks"></a>설명

개체 항목 매크로는 클래스 등록, 초기화 및 만들기를 지원하도록 프로젝트의 전역 범위에 배치됩니다.

OBJECT_ENTRY_AUTO 입력 생성자 클래스 및 클래스 팩터리 생성자 클래스의 함수 포인터 `CreateInstance` ATL 개체 자동으로 생성 된 map에이 개체에 대 한 함수입니다. 때 [CAtlComModule::RegisterServer](catlcommodule-class.md#registerserver) 는 개체 맵의 각 개체에 대 한 시스템 레지스트리 업데이트를 호출 합니다.

아래 표에이 매크로에 두 번째 매개 변수로 제공 하는 클래스의 개체 맵에 추가 정보는 가져온 하는 방법을 설명 합니다.

|에 대 한 정보|가져온|
|---------------------|-------------------|
|COM 등록|[레지스트리 매크로](../../atl/reference/registry-macros.md)|
|클래스 팩터리 만들기|[클래스 팩터리 매크로](../../atl/reference/aggregation-and-class-factory-macros.md)|
|인스턴스 만들기|[집계 매크로](../../atl/reference/aggregation-and-class-factory-macros.md)|
|구성 요소 범주 등록|[범주 매크로](../../atl/reference/category-macros.md)|
|클래스 수준 초기화 및 정리|[ObjectMain](ccomobjectrootex-class.md#objectmain)|

##  <a name="object_entry_non_createable_ex_auto"></a>  OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO

개체를 등록하고 초기화해야 하지만 `CoCreateInstance`를 통해 외부적으로 생성할 수 없도록 지정할 수 있습니다.

```
OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO( clsid, class )
```

### <a name="parameters"></a>매개 변수

*clsid*<br/>
[in] 구현한 COM 클래스의 CLSID는 C++ 라는 클래스 *클래스*합니다.

*class*<br/>
[in] 이름을 합니다 C++ 가 나타내는 COM 클래스를 구현 하는 클래스 *clsid*합니다.

### <a name="remarks"></a>설명

개체 항목 매크로는 클래스 등록, 초기화 및 만들기를 지원하도록 프로젝트의 전역 범위에 배치됩니다.

OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO를 사용 하는 개체는 등록 하 고 초기화를 지정할 수 있습니다 (참조 [OBJECT_ENTRY_AUTO](#object_entry_auto) 자세한 내용은)를 통해 여야 하지만 `CoCreateInstance`합니다.

## <a name="see-also"></a>참고자료

[매크로](../../atl/reference/atl-macros.md)
