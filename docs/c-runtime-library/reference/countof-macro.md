---
title: _countof 매크로
ms.date: 03/22/2018
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- _countof
- countof
helpviewer_keywords:
- countof macro
- _countof macro
ms.assetid: 86198767-f7e5-4beb-898d-3cbbf60350a3
ms.openlocfilehash: 60b4350d6cf14a545de67de0bdaee70ee2099006
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62335349"
---
# <a name="countof-macro"></a>_countof 매크로

정적으로 할당 된 배열의 요소 수를 계산합니다.

## <a name="syntax"></a>구문

```C
#define _countof(array) (sizeof(array) / sizeof(array[0]))
```

### <a name="parameters"></a>매개 변수

*array*<br/>
배열 이름입니다.

## <a name="return-value"></a>반환 값

로 표현 된 배열의 요소 수를 **size_t**합니다.

## <a name="remarks"></a>설명

**_countof** 함수와 비슷한 전처리기 매크로로 구현 됩니다. C++ 버전에 대 한 포인터를 정적으로 선언 된 배열 대신 전달 되는 경우 컴파일 시 검색할 추가 템플릿 메커니즘입니다.

했는지 *배열* 가 실제로 배열에 대 한 포인터가 아닌 합니다. C에서는 **_countof** 경우에 잘못 된 결과 생성 *배열* 대 한 포인터입니다. C++를 **_countof** 면 컴파일되지 않습니다 *배열* 대 한 포인터입니다.  배열 함수에 매개 변수로 전달 *포인터로 decays*, 함수 내에서 사용할 수 없다는 의미 **_countof** 배열의 범위를 확인 합니다.

## <a name="requirements"></a>요구 사항

|매크로|필수 헤더|
|-----------|---------------------|
|**_countof**|\<stdlib.h>|

## <a name="example"></a>예제

```cpp
// crt_countof.cpp
#define _UNICODE
#include <stdio.h>
#include <stdlib.h>
#include <tchar.h>

int main( void )
{
   _TCHAR arr[20], *p;
   printf( "sizeof(arr) = %zu bytes\n", sizeof(arr) );
   printf( "_countof(arr) = %zu elements\n", _countof(arr) );
   // In C++, the following line would generate a compile-time error:
   // printf( "%zu\n", _countof(p) ); // error C2784 (because p is a pointer)

   _tcscpy_s( arr, _countof(arr), _T("a string") );
   // unlike sizeof, _countof works here for both narrow- and wide-character strings
}
```

```Output
sizeof(arr) = 40 bytes
_countof(arr) = 20 elements
```

## <a name="see-also"></a>참고자료

[sizeof 연산자](../../cpp/sizeof-operator.md)<br/>
