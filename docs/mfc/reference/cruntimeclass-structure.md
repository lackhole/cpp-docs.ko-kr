---
title: CRuntimeClass 구조체
ms.date: 11/04/2016
f1_keywords:
- CRuntimeClass
helpviewer_keywords:
- CRuntimeClass structure [MFC]
- dynamic class information [MFC]
- runtime [MFC], class information
- run-time class [MFC], CRuntimeClass structure
ms.assetid: de62b6ef-90d4-420f-8c70-f58b36976a2b
ms.openlocfilehash: 92979a10c18d9759e0ecc9f0785e56a97c0f0642
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62372051"
---
# <a name="cruntimeclass-structure"></a>CRuntimeClass 구조체

각 클래스에서 파생 `CObject` 연관 된를 `CRuntimeClass` 런타임에 개체 또는 해당 기본 클래스에 대 한 정보를 가져오는 데 사용할 수 있는 구조입니다.

## <a name="syntax"></a>구문

```
struct CRuntimeClass
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CRuntimeClass::CreateObject](#createobject)|런타임 중 개체를 만듭니다.|
|[CRuntimeClass::FromName](#fromname)|친숙 한 클래스 이름을 사용 하 여 런타임에 개체를 만듭니다.|
|[CRuntimeClass::IsDerivedFrom](#isderivedfrom)|클래스는 지정된 된 클래스에서 파생 된 경우를 결정 합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CRuntimeClass::m_lpszClassName](#m_lpszclassname)|클래스의 이름입니다.|
|[CRuntimeClass::m_nObjectSize](#m_nobjectsize)|개체의 크기(바이트)입니다.|
|[CRuntimeClass::m_pBaseClass](#m_pbaseclass)|에 대 한 포인터를 `CRuntimeClass` 구조의 기본 클래스입니다.|
|[CRuntimeClass::m_pfnCreateObject](#m_pfncreateobject)|동적으로 개체를 생성 하는 함수에 대 한 포인터입니다.|
|[CRuntimeClass::m_pfnGetBaseClass](#m_pfngetbaseclass)|반환 된 `CRuntimeClass` (연결 때 동적으로 사용할 수)만 구조체입니다.|
|[CRuntimeClass::m_wSchema](#m_wschema)|클래스의 스키마 수입니다.|

## <a name="remarks"></a>설명

`CRuntimeClass` 구조체 이며 따라서 기본 클래스를 포함 하지 않습니다.

런타임 시 개체의 클래스를 결정 하는 기능 추가 형식 함수 인수 검사가 필요한 경우 또는 개체의 클래스를 기반으로 하는 특수 한 용도의 코드를 작성 해야 하는 경우에 유용 합니다. 런타임 클래스 정보로 직접 지원 되지 않습니다는 C++ 언어입니다.

`CRuntimeClass` 관련 정보를 제공 합니다. C++ 에 대 한 포인터 등의 개체를 `CRuntimeClass` 기본 클래스 및 관련된 클래스의 ASCII 클래스 이름입니다. 이 구조는 또한 동적으로 개체를 친숙 한 이름을 사용 하 고 관련된 클래스는 특정 클래스에서 파생 된 경우를 결정 하 여 개체의 형식 지정을 만드는 데 사용할 수 있는 다양 한 기능을 구현 합니다.

사용 하 여 대 한 자세한 내용은 `CRuntimeClass`, 문서를 참조 하세요 [런타임 클래스 정보 액세스](../../mfc/accessing-run-time-class-information.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`CRuntimeClass`

## <a name="requirements"></a>요구 사항

**헤더:** afx.h

##  <a name="createobject"></a>  CRuntimeClass::CreateObject

런타임에 지정된 된 클래스를 동적으로 만들려면이 함수를 호출 합니다.

```
CObject* CreateObject();

static CObject* PASCAL CreateObject(LPCSTR lpszClassName);

static CObject* PASCAL CreateObject(LPCWSTR lpszClassName);
```

### <a name="parameters"></a>매개 변수

*lpszClassName*<br/>
만들 클래스의 친숙 한 이름입니다.

### <a name="return-value"></a>반환 값

새로 만든된 개체 또는 클래스 이름이 없거나 개체를 만드는 메모리가 부족 한 경우 NULL 포인터입니다.

### <a name="remarks"></a>설명

클래스에서 파생 된 `CObject` 런타임에 지정된 된 클래스의 개체를 만들 수 있는 동적 생성을 지원할 수 있습니다. 문서, 뷰 및 프레임 클래스, 예를 들어 해야 동적 생성을 지원 합니다. 동적 만들기에 대 한 자세한 내용은 및 `CreateObject` 멤버를 참조 하세요 [CObject 클래스](../../mfc/using-cobject.md) 고 [CObject 클래스: 기능 수준 지정](../../mfc/specifying-levels-of-functionality.md)합니다.

### <a name="example"></a>예제

  예를 참조 하세요 [IsDerivedFrom](#isderivedfrom)합니다.

##  <a name="fromname"></a>  CRuntimeClass::FromName

검색 하려면이 함수를 호출 합니다 `CRuntimeClass` 친숙 한 이름과 연결 된 구조입니다.

```
static CRuntimeClass* PASCAL FromName(LPCSTR lpszClassName);

static CRuntimeClass* PASCAL FromName(LPCWSTR lpszClassName);
```

### <a name="parameters"></a>매개 변수

*lpszClassName*<br/>
파생 된 클래스의 친숙 한 이름이 `CObject`합니다.

### <a name="return-value"></a>반환 값

에 대 한 포인터를 `CRuntimeClass` 이름에 해당 하는 전달 된 개체 *lpszClassName*합니다. 일치 하는 클래스 이름을 찾지 못했습니다 경우 함수가 NULL을 반환 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCCObjectSample#17](../../mfc/codesnippet/cpp/cruntimeclass-structure_1.cpp)]

##  <a name="isderivedfrom"></a>  CRuntimeClass::IsDerivedFrom

호출 하는 클래스에 지정 된 클래스에서 파생 됩니다 확인 하려면이 함수를 호출 합니다 *pBaseClass* 매개 변수입니다.

```
BOOL IsDerivedFrom(const CRuntimeClass* pBaseClass) const;
```

### <a name="parameters"></a>매개 변수

*pBaseClass*<br/>
파생 된 클래스의 친숙 한 이름이 `CObject`합니다.

### <a name="return-value"></a>반환 값

TRUE 이면 클래스 호출 `IsDerivedFrom` 기본에서 파생 된 클래스 `CRuntimeClass` 구조체가 매개 변수로 지정 된, 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

관계 "를 검색 하 여" 체인 멤버의 클래스를 파생 클래스에서 위쪽으로 결정 됩니다. 이 함수는 기본 클래스에 대 한 일치 항목이 없을 경우만 FALSE를 반환 합니다.

> [!NOTE]
>  사용 하 여 `CRuntimeClass` 구조 런타임 개체 정보를 검색 하려는 클래스의 구현에서 IMPLEMENT_DYNAMIC, IMPLEMENT_DYNCREATE, 또는 IMPLEMENT_SERIAL 매크로 포함 해야 합니다.

사용 하 여 대 한 자세한 내용은 `CRuntimeClass`, 문서를 참고 [CObject 클래스: 런타임 클래스 정보 액세스](../../mfc/accessing-run-time-class-information.md)합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCCObjectSample#18](../../mfc/codesnippet/cpp/cruntimeclass-structure_2.cpp)]

##  <a name="m_lpszclassname"></a>  CRuntimeClass::m_lpszClassName

ASCII 클래스 이름을 포함 하는 null 종료 문자열입니다.

### <a name="remarks"></a>설명

이 이름을 사용 하 여 클래스의 인스턴스를 만드는 데 사용할 수는 `FromName` 멤버 함수입니다.

### <a name="example"></a>예제

  예를 참조 하세요 [IsDerivedFrom](#isderivedfrom)합니다.

##  <a name="m_nobjectsize"></a>  CRuntimeClass::m_nObjectSize

크기 (바이트)는 개체입니다.

### <a name="remarks"></a>설명

개체에 데이터 멤버가 할당 된 메모리를 가리키는 경우 해당 메모리의 크기를 포함 되지 않습니다.

### <a name="example"></a>예제

  예를 참조 하세요 [IsDerivedFrom](#isderivedfrom)합니다.

##  <a name="m_pbaseclass"></a>  CRuntimeClass::m_pBaseClass

응용 프로그램이 정적으로 MFC에 링크 하는 경우이 데이터 멤버에 대 한 포인터를 포함 합니다 `CRuntimeClass` 구조의 기본 클래스입니다.

### <a name="remarks"></a>설명

응용 프로그램은 동적으로 MFC 라이브러리에 링크를 참조 [m_pfnGetBaseClass](#m_pfngetbaseclass)합니다.

### <a name="example"></a>예제

  예를 참조 하세요 [IsDerivedFrom](#isderivedfrom)합니다.

##  <a name="m_pfncreateobject"></a>  CRuntimeClass::m_pfnCreateObject

클래스의 개체를 만드는 기본 생성자 함수 포인터입니다.

### <a name="remarks"></a>설명

이 포인터가 유효 클래스 동적 생성을 지 원하는 경우 그렇지 않으면 함수는 NULL을 반환합니다.

##  <a name="m_pfngetbaseclass"></a>  CRuntimeClass::m_pfnGetBaseClass

이 데이터 멤버를 반환 하는 함수를 가리키는 경우 응용 프로그램에서는 MFC 라이브러리를 공유 DLL로는 `CRuntimeClass` 구조의 기본 클래스입니다.

### <a name="remarks"></a>설명

응용 프로그램은 정적으로 MFC 라이브러리에 링크를 참조 [m_pBaseClass](#m_pbaseclass)합니다.

### <a name="example"></a>예제

  예를 참조 하세요 [IsDerivedFrom](#isderivedfrom)합니다.

##  <a name="m_wschema"></a>  CRuntimeClass::m_wSchema

스키마 (직렬화 할 수 없는 클래스에 대 한-1) 수입니다.

### <a name="remarks"></a>설명

스키마 숫자에 대 한 자세한 내용은 참조는 [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) 매크로입니다.

### <a name="example"></a>예제

  예를 참조 하세요 [IsDerivedFrom](#isderivedfrom)합니다.

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CObject::GetRuntimeClass](../../mfc/reference/cobject-class.md#getruntimeclass)<br/>
[CObject::IsKindOf](../../mfc/reference/cobject-class.md#iskindof)<br/>
[RUNTIME_CLASS](run-time-object-model-services.md#runtime_class)<br/>
[IMPLEMENT_DYNAMIC](run-time-object-model-services.md#implement_dynamic)<br/>
[IMPLEMENT_DYNCREATE](run-time-object-model-services.md#implement_dyncreate)<br/>
[IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial)
