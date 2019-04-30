---
title: HANDLETraits 구조체
ms.date: 09/27/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits::Close
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits::GetInvalidValue
helpviewer_keywords:
- Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits structure
- Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits::Close method
- Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits::GetInvalidValue method
ms.assetid: 22963e88-d857-4624-9182-7c986daff722
ms.openlocfilehash: 4dd2cde62d36c46926e703e6fb649e2ae4ef7811
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62398370"
---
# <a name="handletraits-structure"></a>HANDLETraits 구조체

핸들의 공통 된 특징을 정의합니다.

## <a name="syntax"></a>구문

```cpp
struct HANDLETraits;
```

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 Typedefs

이름   | 설명
------ | ---------------------
`Type` | 핸들에 대 한 동의어입니다.

### <a name="public-methods"></a>Public 메서드

이름                                              | 설명
------------------------------------------------- | -----------------------------
[HANDLETraits::Close](#close)                     | 지정된 된 핸들을 닫습니다.
[HANDLETraits::GetInvalidValue](#getinvalidvalue) | 잘못 된 핸들을 나타냅니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`HANDLETraits`

## <a name="requirements"></a>요구 사항

**헤더:** corewrappers.h

**네임스페이스:** Microsoft::WRL::Wrappers::HandleTraits

## <a name="close"></a>HANDLETraits::Close

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

## <a name="getinvalidvalue"></a>HANDLETraits::GetInvalidValue

잘못 된 핸들을 나타냅니다.

```cpp
inline static HANDLE GetInvalidValue();
```

### <a name="return-value"></a>반환 값

항상 INVALID_HANDLE_VALUE를 반환합니다. (INVALID_HANDLE_VALUE Windows에서 정의 됩니다.)
