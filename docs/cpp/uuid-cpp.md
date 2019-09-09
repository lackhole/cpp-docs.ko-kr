---
title: uuid (C++)
ms.date: 11/04/2016
f1_keywords:
- uuid_cpp
helpviewer_keywords:
- __declspec keyword [C++], uuid
- uuid __declspec keyword
ms.assetid: 9d004621-09bc-4a8d-871b-648f5d5102d7
ms.openlocfilehash: c121ad99dfbe0021a263f324ccdb9a95441bba33
ms.sourcegitcommit: 180f63704f6ddd07a4172a93b179cf0733fd952d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70740455"
---
# <a name="uuid-c"></a>uuid (C++)

**Microsoft 전용**

컴파일러는 **uuid** 특성을 사용 하 여 선언 되거나 정의 된 클래스 또는 구조체 (전체 COM 개체 정의에만 해당)에 GUID를 연결 합니다.

## <a name="syntax"></a>구문

```
__declspec( uuid("ComObjectGUID") ) declarator
```

## <a name="remarks"></a>설명

**Uuid** 특성은 문자열을 인수로 사용 합니다. 이 문자열은 **{}** 구분 기호를 사용 하거나 사용 하지 않고 일반 레지스트리 형식으로 GUID의 이름을 지정 합니다. 예를 들어:

```cpp
struct __declspec(uuid("00000000-0000-0000-c000-000000000046")) IUnknown;
struct __declspec(uuid("{00020400-0000-0000-c000-000000000046}")) IDispatch;
```

재선언에서 이 특성을 적용할 수 있습니다. 이를 통해 시스템 헤더는와 `IUnknown`같은 인터페이스 정의를 제공 하 고, 다른 헤더 ( \<예: comdef. h >)에서 재선언을 사용 하 여 GUID를 제공할 수 있습니다.

[__Uuidof](../cpp/uuidof-operator.md) 키워드는 사용자 정의 형식에 연결 된 상수 GUID를 검색 하는 데 적용할 수 있습니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[__declspec](../cpp/declspec.md)<br/>
[키워드](../cpp/keywords-cpp.md)