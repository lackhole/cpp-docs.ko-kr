---
title: InvokeModeOptions 구조체
ms.date: 03/22/2018
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::InvokeModeOptions
helpviewer_keywords:
- InvokeModeOptions structure
- InvokeMode enum
ms.openlocfilehash: ff16c6c5a2ce09313283198fe0b86e95d572e46c
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58785493"
---
# <a name="invokemodeoptions-structure"></a>InvokeModeOptions 구조체

대리자 큐에서 모든 이벤트를 발생 시키는 아니면 오류가 발생 한 후 실행을 중지 하려면를 지정 합니다. 허용 되는 값은 지정 된 `InvokeMode` 열거형입니다.

## <a name="syntax"></a>구문

```cpp
enum InvokeMode
{
   StopOnFirstError = 1,
   FireAll = 2,
};

struct InvokeModeOptions
{
   static const InvokeMode invokeMode = invokeModeValue;
};
```

## <a name="requirements"></a>요구 사항

**헤더:** event.h

**네임스페이스:** Microsoft::WRL

## <a name="see-also"></a>참고 항목

[Microsoft::WRL 네임스페이스](microsoft-wrl-namespace.md)<br/>
[Microsoft::WRL::AgileEventSource 클래스](agileeventsource-class.md)