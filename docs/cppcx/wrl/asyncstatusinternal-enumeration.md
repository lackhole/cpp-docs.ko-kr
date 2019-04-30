---
title: AsyncStatusInternal 열거형
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::Details::AsyncStatusInternal
helpviewer_keywords:
- AsyncStatusInternal enumeration
ms.assetid: b783923f-3f1c-4487-9384-be572cbc62d7
ms.openlocfilehash: f12bf4aafc87e44a6e2fb15ba79de4a9744bea58
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62398786"
---
# <a name="asyncstatusinternal-enumeration"></a>AsyncStatusInternal 열거형

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

## <a name="syntax"></a>구문

```cpp
enum AsyncStatusInternal;
```

## <a name="remarks"></a>설명

비동기 작업의 상태 내부 열거형 사이 매핑을 지정 및 `Windows::Foundation::AsyncStatus` 열거형입니다.

## <a name="members"></a>멤버

`_Created`<br/>
`::Windows::Foundation::AsyncStatus::Created`와 같습니다.

`_Started`<br/>
`::Windows::Foundation::AsyncStatus::Started`와 같습니다.

`_Completed`<br/>
`::Windows::Foundation::AsyncStatus::Completed`와 같습니다.

`_Cancelled`<br/>
`::Windows::Foundation::AsyncStatus::Cancelled`와 같습니다.

`_Error`<br/>
`::Windows::Foundation::AsyncStatus::Error`와 같습니다.

## <a name="requirements"></a>요구 사항

**헤더:** async.h

**네임스페이스:** Microsoft::WRL::Details

## <a name="see-also"></a>참고자료

[Microsoft::WRL::Details 네임스페이스](microsoft-wrl-details-namespace.md)