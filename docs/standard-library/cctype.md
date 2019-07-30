---
title: '&lt;cctype&gt;'
ms.date: 11/04/2016
f1_keywords:
- <cctype>
helpviewer_keywords:
- cctype header
ms.assetid: 3fd18bfd-c414-4def-bac1-c362e1fe8b71
ms.openlocfilehash: d1d69b5fe125372c489965949b2b59c4012fdec9
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68449841"
---
# <a name="ltcctypegt"></a>&lt;cctype&gt;

표준 C 라이브러리 헤더 \<ctype.h>를 포함하고 `std` 네임스페이스에 연결된 이름을 추가합니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<cctype >

**네임스페이스:** std

## <a name="remarks"></a>설명

이 헤더를 포함하는 경우 표준 C 라이브러리 헤더의 외부 링크를 사용하여 선언한 이름이 `std` 네임스페이스에도 선언됩니다.

## <a name="functions"></a>함수

```cpp
int isalnum(int c);
int isalpha(int c);
int isblank(int c);
int iscntrl(int c);
int isdigit(int c);
int isgraph(int c);
int islower(int c);
int isprint(int c);
int ispunct(int c);
int isspace(int c);
int isupper(int c);
int isxdigit(int c);
int tolower(int c);
int toupper(int c);
```

## <a name="see-also"></a>참고자료

[헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)\
[C++ 표준 라이브러리 개요](../standard-library/cpp-standard-library-overview.md)\
[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)
