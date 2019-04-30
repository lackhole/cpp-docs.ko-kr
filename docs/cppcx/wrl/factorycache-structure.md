---
title: FactoryCache 구조체
ms.date: 09/21/2018
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::FactoryCache
- module/Microsoft::WRL::Details::FactoryCache::cookie
- module/Microsoft::WRL::Details::FactoryCache::factory
helpviewer_keywords:
- Microsoft::WRL::Details::FactoryCache structure
- Microsoft::WRL::Details::FactoryCache::cookie data member
- Microsoft::WRL::Details::FactoryCache::factory data member
ms.assetid: 624544e6-0989-47f6-a3e9-edb60e1ee6d4
ms.openlocfilehash: 7196363567dffa43844bbbd1de76934a317302d1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62398500"
---
# <a name="factorycache-structure"></a>FactoryCache 구조체

Windows 런타임을 지 원하는 C++ 템플릿 라이브러리 인프라 하며 코드에서 직접 사용할 수 없습니다.

## <a name="syntax"></a>구문

```cpp
struct FactoryCache;
```

## <a name="remarks"></a>설명

클래스 팩터리와 wrt 등록을 식별 하는 값 또는 COM 클래스 개체의 위치를 포함 합니다.

## <a name="members"></a>멤버

### <a name="public-data-members"></a>공용 데이터 멤버

이름                              | 설명
--------------------------------- | ------------------------------------------------------------------------------------------------------------------------------
[FactoryCache::cookie](#cookie)   | 등록된 된 Windows 런타임 또는 COM 클래스 개체를 식별 하 고 개체 등록을 취소 하려면 나중에 사용 되는 값을 포함 합니다.
[FactoryCache::factory](#factory) | Windows 런타임 또는 COM 클래스 팩터리를 가리킵니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`FactoryCache`

## <a name="requirements"></a>요구 사항

**헤더:** module.h

**네임스페이스:** Microsoft::WRL::Details

## <a name="cookie"></a>FactoryCache::cookie

Windows 런타임을 지 원하는 C++ 템플릿 라이브러리 인프라 하며 코드에서 직접 사용할 수 없습니다.

```cpp
union {
   WINRT_REGISTRATION_COOKIE winrt;
   DWORD com;
} cookie;
```

### <a name="remarks"></a>설명

등록된 된 Windows 런타임 또는 COM 클래스 개체를 식별 하 고 개체 등록을 취소 하려면 나중에 사용 되는 값을 포함 합니다.

## <a name="factory"></a>FactoryCache::factory

Windows 런타임을 지 원하는 C++ 템플릿 라이브러리 인프라 하며 코드에서 직접 사용할 수 없습니다.

```cpp
IUnknown* factory;
```

### <a name="remarks"></a>설명

Windows 런타임 또는 COM 클래스 팩터리를 가리킵니다.
