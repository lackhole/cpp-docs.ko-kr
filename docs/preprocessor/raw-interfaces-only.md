---
title: raw_interfaces_only
ms.date: 11/04/2016
f1_keywords:
- raw_interfaces_only
helpviewer_keywords:
- raw_interfaces_only attribute
ms.assetid: 87056c6d-3f34-4248-af58-f5775a35bfb7
ms.openlocfilehash: 48133b85ccb5ddb8de8e6cb614d41cde22dac66b
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59028262"
---
# <a name="rawinterfacesonly"></a>raw_interfaces_only
**C++특정**

오류 처리 래퍼 함수를 생성 하지 않습니다 하 고 [속성](../cpp/property-cpp.md) 해당 래퍼 함수를 사용 하는 선언 합니다.

## <a name="syntax"></a>구문

```
raw_interfaces_only
```

## <a name="remarks"></a>설명

합니다 **raw_interfaces_only** 문제도 발생 하 게 제거할 수 있는 비 속성 함수 명명에 사용 된 기본 접두사가 특성입니다. 접두사는 일반적으로 **raw_** 합니다. 이 특성이 지정되면 형식 라이브러리에서 직접 함수 이름을 가져옵니다.

이 특성을 사용하면 형식 라이브러리의 하위 내용만 노출할 수 있습니다.

**최종 C++ 특정**

## <a name="see-also"></a>참고자료

[#import 특성](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import Directive](../preprocessor/hash-import-directive-cpp.md)