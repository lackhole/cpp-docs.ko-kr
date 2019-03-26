---
title: 할당자
ms.date: 03/21/2019
f1_keywords:
- allocator_cpp
helpviewer_keywords:
- __declspec keyword [C++], allocator
- allocator __declspec keyword
ms.openlocfilehash: f9c8de7c8686b89a2ab9570a2558e3f649e545b5
ms.sourcegitcommit: 0064d37467f958dd6a5111f20d7660eaccd53ee9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/25/2019
ms.locfileid: "58419091"
---
# <a name="allocator"></a>할당자

**Microsoft 전용**

합니다 **할당자** 선언 지정자의 할당을 통해 이벤트 추적에 대 한 Windows (ETW) 표시 되도록 사용자 지정 메모리 할당 함수에 적용 될 수 있습니다.

## <a name="syntax"></a>구문

```
   __declspec(allocator) 
```

## <a name="remarks"></a>설명

Visual Studio에서 기본 메모리 프로파일러 할당 런타임 중 내보낸 ETW 이벤트 데이터를 수집 하 여 작동 합니다. CRT 및 Windows SDK의 할당자가 해당 할당 데이터를 캡처할 수 있도록 원본 수준에서 주석이 추가되었습니다. 고유한 할당자를 작성 하는 경우 새로 할당 된 힙 메모리에 대 한 포인터를 반환 하는 모든 함수를 데코 레이트 할 `__declspec(allocator)`myMalloc에 대 한이 예제와 같이:

```cpp
__declspec(allocator) void* myMalloc(size_t size)
```

자세한 내용은 [Visual Studio에서 메모리 사용량을 측정](/visualstudio/profiling/memory-usage) 하 고 [사용자 지정 네이티브 ETW 힙 이벤트](/visualstudio/profiling/custom-native-etw-heap-events)합니다.