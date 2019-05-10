---
title: 'Platform:: recreateexception 메서드'
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Exception
helpviewer_keywords:
- Platform::Exception Class
ms.assetid: fa73d1ab-86e4-4d26-a7d9-81938c1c7e77
ms.openlocfilehash: 9e167efc54352d125e849956a2da8d8e8cad4ed6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62330325"
---
# <a name="platformrecreateexception-method"></a>Platform::ReCreateException 메서드

이 메서드는 내부 전용이며 사용자 코드에서는 사용되지 않습니다. Exception:: createexception 메서드를 대신 사용 합니다.

## <a name="syntax"></a>구문

```cpp
static Exception^ ReCreateException(int hr)
```

### <a name="parameters"></a>매개 변수

*hr*

### <a name="property-valuereturn-value"></a>속성 값/반환 값

지정된 HRESULT에 따라 새 Platform::Exception^을 반환합니다.
