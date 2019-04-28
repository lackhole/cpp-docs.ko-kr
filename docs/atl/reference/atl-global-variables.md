---
title: ATL 전역 변수
ms.date: 12/06/2017
f1_keywords:
- ATLBASE/_pAtlModule
helpviewer_keywords:
- global variables, ATL
- _pAtlModule
ms.assetid: e881a319-99ca-4f5d-8a0b-34b3dcd0f37f
ms.openlocfilehash: 4f98b31d2454b7c6e903e5b5b87bceb4ddcb6961
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62248162"
---
# <a name="atl-global-variables"></a>ATL 전역 변수

## <a name="patlmodule"></a>_pAtlModule

현재 모듈에 대 한 포인터를 저장 하는 전역 변수입니다.

```cpp
__declspec(selectany) CAtlModule * _pAtlModule
```

### <a name="remarks"></a>설명

CComModule (이제 사용 되지 않음) 클래스는 시각적 개체에 제공 하는 기능을 제공 하도록이 전역 변수에서 메서드를 사용할 수 C++ 6.0.

### <a name="example"></a>예제

```cpp
LONG lLocks = _pAtlModule->GetLockCount();
```

### <a name="requirements"></a>요구 사항

**헤더:** atlbase.h
