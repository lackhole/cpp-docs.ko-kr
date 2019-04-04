---
title: TerminateMap 함수
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::TerminateMap
helpviewer_keywords:
- TerminateMap function
ms.assetid: 1c314a61-da5d-49bb-ac44-c34ee3c23b66
ms.openlocfilehash: 17d02ea9cade0301798a5d6625f8eb9a568cb2cc
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58784871"
---
# <a name="terminatemap-function"></a>TerminateMap 함수

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

## <a name="syntax"></a>구문

```cpp
inline bool TerminateMap(
   _In_ ModuleBase *module,
   _In_opt_z_ const wchar_t *serverName,
    bool forceTerminate) throw()
```

### <a name="parameters"></a>매개 변수

*module*<br/>
A [모듈](module-class.md)합니다.

*serverName*<br/>
매개 변수에 의해 지정 된 모듈의 클래스 팩터리 하위 집합의 이름을 *모듈*합니다.

*forceTerminate*<br/>
**true** 클래스를 종료 하는 관계 없이 팩터리는 활성; **false** 모든 팩터리 활성화 된 경우 클래스 팩터리를 종료 되지 않습니다.

## <a name="return-value"></a>반환 값

**true 이면** 모든 클래스 팩터리가 고, 그렇지 않으면 종료 되었으면 **false**합니다.

## <a name="remarks"></a>설명

지정된 된 모듈의 클래스 팩터리를 종료합니다.

## <a name="requirements"></a>요구 사항

**헤더:** module.h

**네임스페이스:** Microsoft::WRL::Details

## <a name="see-also"></a>참고 항목

[Microsoft::WRL::Details 네임스페이스](microsoft-wrl-details-namespace.md)