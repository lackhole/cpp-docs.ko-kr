---
title: assert Macro, _assert, _wassert
ms.date: 11/04/2016
apiname:
- assert
- _assert
- _wassert
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- assert
- _assert
- _wassert
- assert/_wassert
helpviewer_keywords:
- aborting programs
- assert function
- assert macro
ms.assetid: a9ca031a-648b-47a6-bdf1-65fc7399dd40
ms.openlocfilehash: 7ac299213ba3de878f7cf2dc99b44c45273bc3b2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62341368"
---
# <a name="assert-macro-assert-wassert"></a>assert Macro, _assert, _wassert

식을 계산, 결과가 **false**진단 메시지를 출력 하 고 프로그램을 중단 합니다.

## <a name="syntax"></a>구문

```C
assert(
   expression
);
void _assert(
   char const* message,
   char const* filename,
   unsigned line
);
void _wassert(
   wchar_t const* message,
   wchar_t const* filename,
   unsigned line
);
```

### <a name="parameters"></a>매개 변수

*expression*<br/>
에 0이 아닌 값을 평가 하는 스칼라 식 (포인터 식 포함) (**true**) 또는 0 (**false**).

*message*<br/>
표시할 메시지입니다.

*filename*<br/>
어설션이 실패한 소스 파일의 이름입니다.

*line*<br/>
실패한 어설션의 소스 파일에 있는 줄 번호입니다.

## <a name="remarks"></a>설명

합니다 **assert** 매크로 일반적으로 프로그램을 개발 하는 동안 논리 오류를 식별 하는 데 사용 됩니다. 구현 하 여 예기치 않은 조건이 발생할 때 프로그램 실행을 중지 하는 데 사용할 합니다 *식을* 인수를 평가 하 **false** 만 프로그램은 잘못 작동할 때. 어설션 검사 해제할 수 있습니다 컴파일 시간에 매크로 정의 하 여 **NDEBUG**합니다. 해제할 수 있습니다 합니다 **assert** 매크로 사용 하 여 소스 파일을 수정 하지 않고는 **/DNDEBUG** 명령줄 옵션입니다. 해제할 수 있습니다는 **assert** 를 사용 하 여 소스 코드에서 매크로 `#define NDEBUG` 전에 지시문 \<r t. h > 포함 됩니다.

**assert** 매크로가 진단 메시지를 출력 될 때 *식* 로 **false** (0) 및 호출 [중단](abort.md) 프로그램 종료 실행 합니다. 아무 작업도 수행 하는 경우 *식을* 됩니다 **true** (0이 아님). 진단 메시지에는 실패한 식, 소스 파일의 이름 및 어설션이 실패한 줄의 번호가 포함됩니다.

진단 메시지는 와이드 문자로 출력됩니다. 따라서 식에 유니코드 문자가 있어도 예상대로 작동합니다.

진단 메시지의 대상은 루틴을 호출한 애플리케이션의 형식에 따라 달라집니다. 콘솔 응용 프로그램을 통해 메시지를 항상 받을 **stderr**합니다. Windows 기반 응용 프로그램에서는 **assert** 는 Windows를 호출 [MessageBox](/windows/desktop/api/winuser/nf-winuser-messagebox) 와 함께 메시지를 표시 하는 메시지 상자를 만드는 함수를 **확인** 단추입니다. 사용자가 **확인**을 클릭하면 프로그램이 즉시 중단됩니다.

응용 프로그램 런타임 라이브러리의 디버그 버전과 연결 된 경우 **assert** 세 개의 단추를 사용 하 여 메시지 상자를 만듭니다. **Abort**, **다시 시도**, 및 **무시**합니다. 사용자가 **중단**을 클릭하면 프로그램이 즉시 중단됩니다. 사용자가 **다시 시도**를 클릭하면 디버거가 호출되고 JIT(Just-In-Time) 디버깅을 사용하는 경우 사용자가 프로그램을 디버깅할 수 있습니다. 클릭 하면 **무시**, **assert** 정상적인 실행이 계속: 메시지 상자를 사용 하 여 만들며 합니다 **확인** 단추입니다. 오류 조건이 있을 때 **무시** 를 클릭하면 정의되지 않은 동작이 발생할 수 있습니다.

CRT 디버깅에 대한 자세한 내용은 [CRT 디버깅 기술](/visualstudio/debugger/crt-debugging-techniques)을 참조하세요.

합니다 **_assert** 하 고 **_wassert** 함수는 내부 CRT 함수입니다. 이를 통해 어설션을 지원하기 위해 개체 파일에 필요한 코드를 최소화할 수 있습니다. 이들 함수는 직접 호출하지 않는 것이 좋습니다.

**assert** 매크로 C 런타임 라이브러리의 디버그 및 릴리스 버전 모두에서 활성화 된 경우 **NDEBUG** 정의 되어 있지 않습니다. 때 **NDEBUG** 는 정의 된 매크로 사용할 수 있지만 해당 인수를 평가 하지 않습니다 영향을 주지 않습니다. 를 사용 하는 경우는 **assert** 매크로 호출 **_wassert** 해당 구현에 대 한 합니다. 기타 어셜션 매크로 [_ASSERT](assert-asserte-assert-expr-macros.md), [_ASSERTE](assert-asserte-assert-expr-macros.md) 및 [_ASSERT_EXPR](assert-asserte-assert-expr-macros.md)도 사용할 수 있지만 어설션 매크로는 [_DEBUG](../../c-runtime-library/debug.md) 매크로가 정의되고 어설션 매크로가 C 런타임 라이브러리의 디버그 버전과 연결된 코드에 있을 때만 어설션 매크로에 전달되는 식을 계산합니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**assert**, **_wassert**|\<assert.h>|

서명의 합니다 **_assert** 헤더 파일에 함수를 사용할 수 없습니다. 서명의 합니다 **_wassert** 함수 때만 사용할 수는 **NDEBUG** 매크로가 정의 되지 않았습니다.

## <a name="example"></a>예제

이 프로그램에는 **analyze_string** 함수는 **assert** 문자열 및 길이 관련 된 여러 조건을 테스트 하는 매크로입니다. 조건 중 하나라도 실패하면 프로그램이 실패의 원인을 나타내는 메시지를 출력합니다.

```C
// crt_assert.c
// compile by using: cl /W4 crt_assert.c
#include <stdio.h>
#include <assert.h>
#include <string.h>

void analyze_string( char *string );   // Prototype

int main( void )
{
   char  test1[] = "abc", *test2 = NULL, test3[] = "";

   printf ( "Analyzing string '%s'\n", test1 ); fflush( stdout );
   analyze_string( test1 );
   printf ( "Analyzing string '%s'\n", test2 ); fflush( stdout );
   analyze_string( test2 );
   printf ( "Analyzing string '%s'\n", test3 ); fflush( stdout );
   analyze_string( test3 );
}

// Tests a string to see if it is NULL,
// empty, or longer than 0 characters.
void analyze_string( char * string )
{
   assert( string != NULL );        // Cannot be NULL
   assert( *string != '\0' );       // Cannot be empty
   assert( strlen( string ) > 2 );  // Length must exceed 2
}
```

프로그램에서 다음 출력이 생성됩니다.

```Output
Analyzing string 'abc'
Analyzing string '(null)'
Assertion failed: string != NULL, file crt_assert.c, line 25
```

어설션 실패 후에는 운영 체제 및 런타임 라이브러리의 버전에 따라 다음과 같은 내용이 포함된 메시지 상자가 표시될 수 있습니다.

```Output
A problem caused the program to stop working correctly. Windows will close the program and notify you if a solution is available.
```

디버거가 설치되어 있으면 **디버그** 단추를 선택하여 디버거를 시작하거나, **프로그램을 닫아** 종료합니다.

## <a name="see-also"></a>참고자료

[오류 처리](../../c-runtime-library/error-handling-crt.md)<br/>
[프로세스 및 환경 제어](../../c-runtime-library/process-and-environment-control.md)<br/>
[abort](abort.md)<br/>
[raise](raise.md)<br/>
[signal](signal.md)<br/>
[_ASSERT, _ASSERTE, _ASSERT_EXPR 매크로](assert-asserte-assert-expr-macros.md)<br/>
[_DEBUG](../../c-runtime-library/debug.md)<br/>
