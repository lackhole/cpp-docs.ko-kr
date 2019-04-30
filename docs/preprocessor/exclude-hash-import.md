---
title: exclude (#import)
ms.date: 10/18/2018
f1_keywords:
- exclude
helpviewer_keywords:
- exclude attribute
ms.assetid: 0883248a-d4bf-420e-9848-807b28fa976e
ms.openlocfilehash: d6a320089d5954b2cf1d0d96ae1f37656f2ddd58
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62389322"
---
# <a name="exclude-import"></a>제외 (\#가져오기)

**C++특정**

생성되는 형식 라이브러리 헤더 파일에서 항목을 제외시킵니다.

## <a name="syntax"></a>구문

```
exclude("Name1"[, "Name2",...])
```

### <a name="parameters"></a>매개 변수

*Name1*<br/>
제외시킬 첫 번째 항목입니다.

*Name2*<br/>
필요할 경우 제외시킬 두 번째 항목입니다.

## <a name="remarks"></a>설명

형식 라이브러리가 시스템 헤더 또는 다른 형식 라이브러리에 정의된 항목 정의를 포함할 수 있습니다. 이 특성은 여러 개의 인수를 가질 수 있으며, 최고 수준의 형식 라이브러리 항목은 제외됩니다.

**최종 C++ 특정**

## <a name="see-also"></a>참고자료

[#import 특성](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import Directive](../preprocessor/hash-import-directive-cpp.md)