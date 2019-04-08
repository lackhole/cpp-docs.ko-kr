---
title: 함수 (C/C++)
ms.date: 11/04/2016
f1_keywords:
- function_CPP
- vc-pragma.function
helpviewer_keywords:
- function pragma
- pragmas, function
ms.assetid: cbd1bd60-fabf-4b5a-9c3d-2d9f4b871365
ms.openlocfilehash: c57ff2053b3c1fd52474c7eb0dd598641632f789
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59027261"
---
# <a name="function-cc"></a>함수 (C/C++)
pragma의 인수 목록에서 지정된 함수에 대한 호출이 생성되도록 지정합니다.

## <a name="syntax"></a>구문

```
#pragma function( function1 [, function2, ...] )
```

## <a name="remarks"></a>설명

사용 하는 경우는 `intrinsic` pragma (또는 /Oi) 내장 함수 (내장 함수는 함수 호출이 아니라 인라인 코드로 생성 됨)를 생성 하도록 컴파일러에 게 사용할 수 있습니다 합니다 **함수** pragma를 명시적으로 강제 적용을 함수 호출입니다. function pragma가 표시되면 지정된 내장 함수를 포함하는 첫 번째 함수 정의에서 적용되며, 효과의 모양에 또는 소스 파일의 끝에 계속는 `intrinsic` pragma 동일한 내장 함수를 지정 합니다. 합니다 **함수** pragma는 함수의 외부 에서만 사용할 수 있습니다-전역 수준입니다.

내장 형식을 있는 함수 목록에 대해서 [#pragma 내장](../preprocessor/intrinsic.md)합니다.

## <a name="example"></a>예제

```cpp
// pragma_directive_function.cpp
#include <ctype.h>
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

// use intrinsic forms of memset and strlen
#pragma intrinsic(memset, strlen)

// Find first word break in string, and set remaining
// chars in string to specified char value.
char *set_str_after_word(char *string, char ch) {
   int i;
   int len = strlen(string);  /* NOTE: uses intrinsic for strlen */

   for(i = 0; i < len; i++) {
      if (isspace(*(string + i)))
         break;
   }

   for(; i < len; i++)
      *(string + i) = ch;

   return string;
}

// do not use strlen intrinsic
#pragma function(strlen)

// Set all chars in string to specified char value.
char *set_str(char *string, char ch) {
   // Uses intrinsic for memset, but calls strlen library function
   return (char *) memset(string, ch, strlen(string));
}

int main() {
   char *str = (char *) malloc(20 * sizeof(char));

   strcpy_s(str, sizeof("Now is the time"), "Now is the time");
   printf("str is '%s'\n", set_str_after_word(str, '*'));
   printf("str is '%s'\n", set_str(str, '!'));
}
```

```Output
str is 'Now************'
str is '!!!!!!!!!!!!!!!'
```

## <a name="see-also"></a>참고자료

[Pragma 지시문 및 __Pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)