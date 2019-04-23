---
title: setlocale
ms.date: 11/04/2016
f1_keywords:
- setlocale_CPP
- vc-pragma.setlocale
helpviewer_keywords:
- pragmas, setlocale
- setlocale pragma
ms.assetid: e60b43d9-fbdf-4c4e-ac85-805523a13b86
ms.openlocfilehash: b2f28a14b4d4585575a39dd9a936a56a84eeddc4
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59022427"
---
# <a name="setlocale"></a>setlocale

와이드 문자 상수와 문자열 리터럴을 변환할 때 사용되는 로캘(국가/지역 및 언어)을 정의합니다.

## <a name="syntax"></a>구문

```
#pragma setlocale( "[locale-string]" )
```

## <a name="remarks"></a>설명

멀티바이트 문자를 와이드 문자로 변환하는 알고리즘이 로캘에 따라 다를 수 있으며 실행 파일이 실행될 로캘과 다른 로캘에서 컴파일이 발생할 수 있기 때문에 이 pragma는 컴파일 타임에 대상 로캘을 지정하는 방법을 제공합니다. 이 방법을 사용하면 와이드 문자 문자열이 올바른 형식으로 저장됩니다.

기본값 *로캘 문자열* 는 ""입니다.

"C" 로캘에서 해당 값으로 문자열의 각 문자를 매핑하는 **wchar_t** (부호 없는 short)입니다. 에 유효한 다른 값 `setlocale` 에 있는 항목의 [언어 문자열](../c-runtime-library/language-strings.md) 목록입니다. 예를 들어 다음을 실행할 수 있습니다.

```cpp
#pragma setlocale("dutch")
```

언어 문자열을 실행할 수 있는지 여부는 코드 페이지와 컴퓨터의 언어 ID 지원에 따라 결정됩니다.

## <a name="see-also"></a>참고자료

[Pragma 지시문 및 __Pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)