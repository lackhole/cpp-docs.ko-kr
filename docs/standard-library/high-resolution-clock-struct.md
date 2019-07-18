---
title: high_resolution_clock 구조체 | Microsoft Docs
ms.custom: ''
ms.date: 05/22/2018
ms.technology: cpp-standard-libraries
ms.topic: reference
f1_keywords:
- chrono/std::chrono::high_resolution_clock
dev_langs:
- C++
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0b00b20e7cea4fa24b37ad33d5536eb9844e6953
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68269125"
---
# <a name="steadyclock-struct"></a>steady_clock 구조체

나타냅니다는 *high_resolution* 시계입니다.

## <a name="syntax"></a>구문

```cpp
class high_resolution_clock
```

## <a name="members"></a>멤버

### <a name="typedefs"></a>형식 정의

|이름|Description|
|----------|-----------------|
|`duration`|에 대 한 동의어 `nanoseconds`에 정의 된 \<chrono >.|
|`period`|에 대 한 동의어 `nano`에 정의 된 \<비율 >.|
|`rep`|에 대 한 동의어 **긴** **긴**의 포함 된 인스턴스화에서 클록 틱 수를 나타내는 데 사용 되는 형식을 `duration`합니다.|
|`time_point`|`chrono::time_point<high_resolution_clock>`의 동의어입니다.|

## <a name="functions"></a>함수

|||
|-|-|
|`now`|반환 된 현재 시간을 `time_point` 값입니다.|

## <a name="constants"></a>상수

|이름|Description|
|----------|-----------------|
|`is_steady`|보유 **true**합니다. `high_resolution_clock`은 *지속*입니다.|
