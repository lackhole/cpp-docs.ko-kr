---
title: tlbid import 특성
ms.date: 08/29/2019
f1_keywords:
- tlbid
helpviewer_keywords:
- tlbid attribute
ms.assetid: 54b06785-191b-4e77-a9a5-485f2b4acb09
ms.openlocfilehash: 364fb224b0f2769cb0933e71d18ff70768189328
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70216538"
---
# <a name="tlbid-import-attribute"></a>tlbid import 특성

**C++컴퓨터별**

기본 형식 라이브러리 이외의 라이브러리를 로드할 수 있도록 합니다.

## <a name="syntax"></a>구문

> **#import** *형식 라이브러리-dll* **tlbid (** *number* **)**

### <a name="parameters"></a>매개 변수

*수많은*\
형식 *라이브러리 dll*에 있는 형식 라이브러리의 번호입니다.

## <a name="remarks"></a>설명

단일 DLL에 여러 형식 라이브러리가 내장 되어 있는 경우 **tlbid**를 사용 하 여 기본 형식 라이브러리 이외의 라이브러리를 로드할 수 있습니다.

예를 들어:

```cpp
#import <MyResource.dll> tlbid(2)
```

다음과 동일합니다.

```cpp
LoadTypeLib("MyResource.dll\\2");
```

**끝 C++ 특정**

## <a name="see-also"></a>참고자료

[#import 특성](../preprocessor/hash-import-attributes-cpp.md)\
[#import 지시문](../preprocessor/hash-import-directive-cpp.md)
