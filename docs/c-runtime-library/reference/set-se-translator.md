---
title: _set_se_translator
ms.date: 02/21/2018
apiname:
- _set_se_translator
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
- _set_se_translator
- set_se_translator
helpviewer_keywords:
- set_se_translator function
- exception handling, changing
- _set_se_translator function
ms.assetid: 280842bc-d72a-468b-a565-2d3db893ae0f
ms.openlocfilehash: 18ee500d7b884d1934c29dc91d9bcb03d507680d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62356552"
---
# <a name="setsetranslator"></a>_set_se_translator

Win32 예외 (C 구조적 예외)를 변환 하는 스레드당 콜백 함수 집합을 C++ 예외를 입력 합니다.

## <a name="syntax"></a>구문

```cpp
_se_translator_function _set_se_translator(
    _se_translator_function seTransFunction
);
```

### <a name="parameters"></a>매개 변수

*seTransFunction*<br/>
작성하는 C 구조적 예외 변환기 함수에 대한 포인터입니다.

## <a name="return-value"></a>반환 값

등록 한 이전 변환기 함수에 대 한 포인터를 반환 **_set_se_translator**이전 함수는 나중에 복원할 수 있도록 합니다. 기본 동작을 복원 하려면 반환 값을 사용할 수 없는 이전 함수가 설정 된 경우 이 값은 **nullptr**합니다.

## <a name="remarks"></a>설명

합니다 **_set_se_translator** 함수는 Win32 예외 (C 구조적 예외)를 처리 하는 방법으로 제공 C++ 예외를 입력 합니다. 각 C 예외를 처리 하도록 허용 하는 C++ **catch** 처리기를 먼저 사용 되거나 C 예외가 특정 클래스 형식 특성에서 파생 될 수 있는 C 예외 래퍼 클래스를 정의 합니다. 이 클래스를 사용하려면 C 예외가 발생할 때마다 내부 예외 처리 메커니즘을 통해 호출되는 사용자 지정 C 예외 변환기 함수를 설치합니다. 변환기 함수 내에서 일치 하는 수 있는 모든 형식의 예외를 throw 할 수 있습니다 C++ **catch** 처리기입니다.

사용 해야 합니다 [/EHa](../../build/reference/eh-exception-handling-model.md) 사용 하는 경우 **_set_se_translator**합니다.

사용자 지정 변환 함수를 지정 하려면 호출 **_set_se_translator** 변환 함수의 이름을 인수로 사용 합니다. 작성 하는 변환기 함수에 있는 스택의 각 함수 호출에 대해 한 번씩 호출 됩니다 **시도** 블록입니다. 기본 변환기 함수가 없습니다.

변환기 함수는 C++ 형식의 예외만 발생시켜야 합니다. throw 이외에도 어떤 작업을 수행하는 경우(예: 로그 파일에 쓰기) 변환기 함수가 호출되는 횟수가 플랫폼에 따라 다르므로 프로그램이 예상대로 작동하지 않을 수 있습니다.

다중 스레드 환경에서 변환기 함수는 각 스레드에 대해 개별적으로 유지 관리됩니다. 각 새 스레드는 자체 변환기 함수를 설치해야 합니다. 따라서 각 스레드는 자체 변환 처리를 담당합니다. **_set_se_translator** 는 한 스레드에 관련이 다른 DLL은 다른 변환 함수를 설치할 수 있습니다.

합니다 *seTransFunction* 작성 하는 함수에는 (/clr을 사용 하 여 컴파일되지) 네이티브 컴파일 함수 여야 합니다. 해야 하는 데 대 한 포인터 및 부호 없는 정수로 Win32 **_EXCEPTION_POINTERS** 인수로 구조입니다. 인수는 Win32 API에 대 한 호출의 반환 값 **GetExceptionCode** 하 고 **GetExceptionInformation** 함수를 각각.

```cpp
typedef void (__cdecl *_se_translator_function)(unsigned int, struct _EXCEPTION_POINTERS* );
```

에 대 한 **_set_se_translator**, 동적으로 CRT에 연결 하는 경우 의미를 가지; 프로세스에서 DLL를 호출할 수 있습니다 다른 **_set_se_translator** 자체 처리기 바꿉니다.

사용 하는 경우 **_set_se_translator** 관리 코드 (/clr을 사용 하 여 컴파일된 코드)에서 또는 혼합 된 네이티브 및 관리 코드를 변환기의 네이티브 코드에만 생성 된 예외에 영향을 줍니다. 관리 코드에서 생성된 관리 예외(예: `System::Exception`을 발생시키는 경우)는 변환기 함수를 통해 라우팅되지 않습니다. Win32 함수를 사용 하 여 관리 되는 코드에서 발생 하는 예외 **RaiseException** 또는 0으로 나누기 예외가 변환기를 통해 라우팅됩니다.와 같은 시스템 예외로 인해 발생 합니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_set_se_translator**|\<eh.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```cpp
// crt_settrans.cpp
// compile with: cl /W4 /EHa crt_settrans.cpp
#include <stdio.h>
#include <windows.h>
#include <eh.h>
#include <exception>

class SE_Exception : public std::exception
{
private:
    unsigned int nSE;
public:
    SE_Exception() : nSE{ 0 } {}
    SE_Exception( unsigned int n ) : nSE{ n } {}
    unsigned int getSeNumber() { return nSE; }
};

void SEFunc()
{
    __try
    {
        printf( "In __try, about to force exception\n" );
        int x = 5;
        int y = 0;
        int *p = &y;
        *p = x / *p;
    }
    __finally
    {
        printf( "In __finally\n" );
    }
}

void trans_func(unsigned int u, EXCEPTION_POINTERS*)
{
    throw SE_Exception(u);
}

int main()
{
    auto original = _set_se_translator(trans_func);
    try
    {
        SEFunc();
    }
    catch(SE_Exception& e)
    {
        printf("Caught a __try exception, error %8.8x.\n", e.getSeNumber());
    }
    _set_se_translator(original);
}
```

```Output
In __try, about to force exception
In __finally
Caught a __try exception, error c0000094.
```

## <a name="example"></a>예제

제공 하는 기능 이지만 **_set_se_translator** 는 관리 코드에서 사용할 수 없는, 있기 네이티브 코드가 아래에서 컴파일되는 경우에이 매핑을 네이티브 코드를 사용 하는 **/clr** 네이티브 코드를 사용 하 여 표시 됩니다으로 스위치 `#pragma unmanaged`합니다. 매핑되는 관리 코드에서 throw 되는 구조적된 예외를 생성 하 고 예외를 처리 하는 코드 표시 해야 합니다 `#pragma unmanaged`합니다. 다음 코드에서는 가능한 사용법을 보여 줍니다. 자세한 내용은 [Pragma 지시문 및 __Pragma 키워드](../../preprocessor/pragma-directives-and-the-pragma-keyword.md)를 참조하세요.

```cpp
// crt_set_se_translator_clr.cpp
// compile with: cl /W4 /clr crt_set_se_translator_clr.cpp
#include <windows.h>
#include <eh.h>
#include <assert.h>
#include <stdio.h>
#include <exception>

int thrower_func(int i) {
   int y = 0;
   int *p = &y;
   *p = i / *p;
   return 0;
}

class SE_Exception : public std::exception {
private:
    unsigned int nSE;
public:
    SE_Exception() : nSE{ 0 } {}
    SE_Exception(unsigned int n) : nSE{ n } {}
    unsigned int getSeNumber() { return nSE; }
};

#pragma unmanaged
void my_trans_func(unsigned int u, PEXCEPTION_POINTERS)
{
    throw SE_Exception(u);
}

void DoTest()
{
    try
    {
        thrower_func(10);
    }
    catch(SE_Exception& e)
    {
        printf("Caught SE_Exception, error %8.8x\n", e.getSeNumber());
    }
    catch(...)
    {
        printf("Caught unexpected SEH exception.\n");
    }
}
#pragma managed

int main() {
    auto original = _set_se_translator(my_trans_func);
    DoTest();
    _set_se_translator(original);
}
```

```Output
Caught SE_Exception, error c0000094
```

## <a name="see-also"></a>참고자료

[예외 처리 루틴](../../c-runtime-library/exception-handling-routines.md)<br/>
[set_terminate](set-terminate-crt.md)<br/>
[set_unexpected](set-unexpected-crt.md)<br/>
[terminate](terminate-crt.md)<br/>
[unexpected](unexpected-crt.md)<br/>
