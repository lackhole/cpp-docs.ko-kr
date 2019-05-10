---
title: CreatorMap 구조체
ms.date: 09/21/2018
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::CreatorMap
- implements/Microsoft::WRL::Details::CreatorMap
- module/Microsoft::WRL::Details::CreatorMap::activationId
- module/Microsoft::WRL::Details::CreatorMap::factoryCache
- module/Microsoft::WRL::Details::CreatorMap::factoryCreator
- module/Microsoft::WRL::Details::CreatorMap::serverName
helpviewer_keywords:
- Microsoft::WRL::Details::CreatorMap structure
- Microsoft::WRL::Details::CreatorMap::activationId data member
- Microsoft::WRL::Details::CreatorMap::factoryCache data member
- Microsoft::WRL::Details::CreatorMap::factoryCreator data member
- Microsoft::WRL::Details::CreatorMap::serverName data member
ms.assetid: 94e40927-90c3-4107-bca3-3ad2dc4beda9
ms.openlocfilehash: 44d06f317661059bea92d8c6f27955606a964bb7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62398617"
---
# <a name="creatormap-structure"></a>CreatorMap 구조체

Windows 런타임을 지 원하는 C++ 템플릿 라이브러리 인프라 하며 코드에서 직접 사용할 수 없습니다.

## <a name="syntax"></a>구문

```cpp
struct CreatorMap;
```

## <a name="remarks"></a>설명

초기화, 등록 및 개체의 등록을 취소 하는 방법에 대 한 정보를 포함 합니다.

`CreatorMap`에는 다음 정보가 포함되어 있습니다.

- 초기화, 등록 및 개체의 등록을 취소 하는 방법.

- 클래식 COM 또는 Windows 런타임 팩터리에 따라 정품 인증 데이터를 비교 하는 방법입니다.

- 인터페이스에 대 한 팩터리 캐시 및 서버 이름에 대 한 정보입니다.

## <a name="members"></a>멤버

### <a name="public-data-members"></a>공용 데이터 멤버

이름                                          | 설명
--------------------------------------------- | ------------------------------------------------------------------------------------------------------
[CreatorMap::activationId](#activationid)     | 클래식 COM 클래스 ID 또는 Windows 런타임 이름을 식별 되는 개체 ID를 나타냅니다.
[CreatorMap::factoryCache](#factorycache)     | 에 대 한 팩터리 캐시에 대 한 포인터를 저장 합니다 `CreatorMap`합니다.
[CreatorMap::factoryCreator](#factorycreator) | 지정 된 팩터리를 만듭니다 `CreatorMap`합니다.
[CreatorMap::serverName](#servername)         | 에 대 한 서버 이름을 저장 합니다 `CreatorMap`합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`CreatorMap`

## <a name="requirements"></a>요구 사항

**헤더:** module.h

**네임스페이스:** Microsoft::WRL::Details

## <a name="activationid"></a>CreatorMap::activationId

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
union {
   const IID* clsid;
   const wchar_t* (*getRuntimeName)();
} activationId;
```

### <a name="parameters"></a>매개 변수

*clsid*<br/>
인터페이스 ID입니다.

*getRuntimeName*<br/>
Windows 런타임 개체의 이름을 검색 하는 함수입니다.

### <a name="remarks"></a>설명

클래식 COM 클래스 ID 또는 Windows 런타임 이름을 식별 되는 개체 ID를 나타냅니다.

## <a name="factorycache"></a>CreatorMap::factoryCache

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
FactoryCache* factoryCache;
```

### <a name="remarks"></a>설명

에 대 한 팩터리 캐시에 대 한 포인터를 저장 합니다 `CreatorMap`합니다.

## <a name="factorycreator"></a>CreatorMap::factoryCreator

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
HRESULT (*factoryCreator)(
   unsigned int* currentflags,
   const CreatorMap* entry,
   REFIID iidClassFactory,
IUnknown** factory);
```

### <a name="parameters"></a>매개 변수

*currentflags*<br/>
중 하나는 [RuntimeClassType](runtimeclasstype-enumeration.md) 열거자입니다.

*entry*<br/>
CreatorMap 합니다.

*iidClassFactory*<br/>
인터페이스 ID 클래스 팩터리입니다.

*factory*<br/>
작업이 완료 되 면 클래스 팩터리의 주소입니다.

### <a name="return-value"></a>반환 값

성공하면 S_OK이고, 그렇지 않으면 오류를 나타내는 HRESULT입니다.

### <a name="remarks"></a>설명

지정 된 CreatorMap에 대 한 팩터리를 만듭니다.

## <a name="servername"></a>CreatorMap::serverName

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
const wchar_t* serverName;
```

### <a name="remarks"></a>설명

CreatorMap는 서버 이름을 저장합니다.
