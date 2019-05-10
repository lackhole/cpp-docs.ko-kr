---
title: HANDLENullTraits 구조체
ms.date: 09/27/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits::Close
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits::GetInvalidValue
helpviewer_keywords:
- Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits structure
- Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits::Close method
- Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits::GetInvalidValue method
ms.assetid: 88a29a14-c516-40cb-a0ca-ee897a668623
ms.openlocfilehash: d70425f414b998eb67e3937c2c126dd3eda0c00d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62398383"
---
# <a name="handlenulltraits-structure"></a>HANDLENullTraits 구조체

초기화 되지 않은 핸들을의 일반적인 특성을 정의합니다.

## <a name="syntax"></a>구문

```cpp
struct HANDLENullTraits;
```

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 Typedefs

이름   | 설명
------ | ---------------------
`Type` | 핸들에 대 한 동의어입니다.

### <a name="public-methods"></a>Public 메서드

이름                                                  | 설명
----------------------------------------------------- | -----------------------------
[HANDLENullTraits::Close](#close)                     | 지정된 된 핸들을 닫습니다.
[HANDLENullTraits::GetInvalidValue](#getinvalidvalue) | 잘못 된 핸들을 나타냅니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`HANDLENullTraits`

## <a name="requirements"></a>요구 사항

**헤더:** corewrappers.h

**네임스페이스:** Microsoft::WRL::Wrappers::HandleTraits

## <a name="close"></a>HANDLENullTraits::Close

지정된 된 핸들을 닫습니다.

```cpp
inline static bool Close(
   _In_ Type h
);
```

### <a name="parameters"></a>매개 변수

*h*<br/>
핸들 닫기입니다.

### <a name="return-value"></a>반환 값

**true** 경우 처리할 *h* 이 고, 그렇지 않으면 닫은 **false**합니다.

## <a name="getinvalidvalue"></a>HANDLENullTraits::GetInvalidValue

잘못 된 핸들을 나타냅니다.

```cpp
inline static Type GetInvalidValue();
```

### <a name="return-value"></a>반환 값

항상 `nullptr`를 반환합니다.
