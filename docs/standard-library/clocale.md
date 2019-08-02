---
title: '&lt;clocale&gt;'
ms.date: 11/04/2016
f1_keywords:
- <clocale>
helpviewer_keywords:
- clocale header
ms.assetid: 5bde3e01-cf67-4f1f-a383-447ec814d00e
ms.openlocfilehash: 60d15795328de567a8ba626f5344b2fb08e57aa7
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68459346"
---
# <a name="ltclocalegt"></a>&lt;clocale&gt;

표준 C 라이브러리 헤더 \<locale.h>를 포함하고 `std` 네임스페이스에 연결된 이름을 추가합니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<clocale >

**네임스페이스:** std

## <a name="remarks"></a>설명

이 헤더를 포함하는 경우 표준 C 라이브러리 헤더의 외부 링크를 사용하여 선언한 이름이 `std` 네임스페이스에도 선언됩니다.

## <a name="constants"></a>상수

```cpp
#define NULL see below
#define LC_ALL see below
#define LC_COLLATE see below
#define LC_CTYPE see below
#define LC_MONETARY see below
#define LC_NUMERIC see below
#define LC_TIME see below
```

## <a name="structures"></a>구조체

```cpp
struct lconv;
```

## <a name="functions"></a>함수

```cpp
char* setlocale(int category, const char* locale);
lconv* localeconv();
```

## <a name="see-also"></a>참고자료

[헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)\
[C++ 표준 라이브러리 개요](../standard-library/cpp-standard-library-overview.md)\
[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)
