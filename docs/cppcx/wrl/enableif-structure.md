---
title: EnableIf 구조체
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::EnableIf
helpviewer_keywords:
- EnableIf structure
ms.assetid: 7825b283-e6b2-4f39-a4b9-c03bcd431b8e
ms.openlocfilehash: daaba919acaa35615af56831f9458831c3d35427
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62398526"
---
# <a name="enableif-structure"></a>EnableIf 구조체

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

## <a name="syntax"></a>구문

```cpp
template <bool b, typename T = void>
struct EnableIf;

template <typename T>
struct EnableIf<true, T>;
```

### <a name="parameters"></a>매개 변수

*T*<br/>
형식입니다.

*b*<br/>
부울 식입니다.

## <a name="remarks"></a>설명

첫 번째 템플릿 매개 변수를 평가 하는 경우 두 번째 템플릿 매개 변수로 지정 된 형식의 데이터 멤버를 정의 **true**합니다.

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 Typedefs

|이름|설명|
|----------|-----------------|
|`type`|경우 템플릿 매개 변수 *b* 로 평가 **true**, 데이터 멤버를 정의 하는 부분 특수화 `type` 형식으로 `T`입니다.|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`EnableIf`

## <a name="requirements"></a>요구 사항

**헤더:** internal.h

**네임스페이스:** Microsoft::WRL::Details

## <a name="see-also"></a>참고자료

[Microsoft::WRL::Details 네임스페이스](microsoft-wrl-details-namespace.md)