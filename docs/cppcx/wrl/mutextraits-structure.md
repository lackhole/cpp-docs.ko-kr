---
title: MutexTraits 구조체
ms.date: 09/27/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::MutexTraits
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::MutexTraits::Unlock
helpviewer_keywords:
- Microsoft::WRL::Wrappers::HandleTraits::MutexTraits structure
- Microsoft::WRL::Wrappers::HandleTraits::MutexTraits::Unlock method
ms.assetid: 6582df80-b9ba-4892-948f-d572a3b23d54
ms.openlocfilehash: 9bc4071e5699610a664cbf01ca3e7d36d7effc5e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62379183"
---
# <a name="mutextraits-structure"></a>MutexTraits 구조체

일반적인 특성을 정의 합니다 [뮤텍스](mutex-class.md) 클래스입니다.

## <a name="syntax"></a>구문

```cpp
struct MutexTraits : HANDLENullTraits;
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

이름                           | 설명
------------------------------ | ------------------------------------------------
[MutexTraits::Unlock](#unlock) | 공유 리소스의 한 독점적인 제어권을 해제합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`HANDLENullTraits`

`MutexTraits`

## <a name="requirements"></a>요구 사항

**헤더:** corewrappers.h

**네임스페이스:** Microsoft::WRL::Wrappers::HandleTraits

## <a name="unlock"></a>Mutextraits:: Unlock 메서드

공유 리소스의 한 독점적인 제어권을 해제합니다.

```cpp
inline static void Unlock(
   _In_ Type h
);
```

### <a name="parameters"></a>매개 변수

*h*<br/>
뮤텍스 개체에 대 한 핸들입니다.
