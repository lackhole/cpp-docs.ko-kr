---
title: 심각한 오류 C1189
ms.date: 04/27/2018
f1_keywords:
- C1189
helpviewer_keywords:
- C1189
ms.assetid: 2e5c8a78-edd4-411c-b619-558a96be148a
ms.openlocfilehash: 06d42316a0109ac063bba43cefebd9aab71c2e72
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62229061"
---
# <a name="fatal-error-c1189"></a>심각한 오류 C1189

> **\#오류:** *사용자가 제공한 오류 메시지*

## <a name="remarks"></a>설명

C1189에서 생성 되는 `#error` 지시문입니다. 지시문을 코딩 하는 개발자는 오류 메시지의 텍스트를 지정 합니다. 자세한 내용은 [#error 지시문 (C /C++)](../../preprocessor/hash-error-directive-c-cpp.md)합니다.

## <a name="example"></a>예제

다음 샘플 C1189를 생성합니다. 이 샘플에서는 개발자 문제를 사용자 지정 오류 메시지 때문에 `_WIN32` 식별자가 정의 되지 않습니다.

```cpp
// C1189.cpp
#undef _WIN32
#if !defined(_WIN32)
#error _WIN32 must be defined   // C1189
#endif
```

## <a name="see-also"></a>참고자료

[#define 지시문(C/C++)](../../preprocessor/hash-define-directive-c-cpp.md)