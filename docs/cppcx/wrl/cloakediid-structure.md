---
title: CloakedIid 구조체
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::CloakedIid
helpviewer_keywords:
- CloakedIid structure
ms.assetid: 82e0e377-ca3a-46bc-b850-ae2c46c15bb5
ms.openlocfilehash: 10dc2af1897147045382e8463b6602fa015fc899
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62398721"
---
# <a name="cloakediid-structure"></a>CloakedIid 구조체

에 `RuntimeClass`, `Implements` 및 `ChainInterfaces` 지정된 된 인터페이스 IID 목록에서 액세스할 수 없는 템플릿.

## <a name="syntax"></a>구문

```cpp
template<typename T>
struct CloakedIid : T;
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
인터페이스는 숨겨진 (숨김)입니다.

## <a name="remarks"></a>설명

다음은 방법의 예가 **CloakedIid** 되: `struct MyRuntimeClass : RuntimeClass<CloakedIid<IMyCloakedInterface>> {}`합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`T`

`CloakedIid`

## <a name="requirements"></a>요구 사항

**헤더:** implements.h

**네임스페이스:** Microsoft::WRL

## <a name="see-also"></a>참고자료

[Microsoft::WRL 네임스페이스](microsoft-wrl-namespace.md)