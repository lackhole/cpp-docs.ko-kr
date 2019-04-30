---
title: set_unexpected(CRT)
ms.date: 11/04/2016
apiname:
- set_unexpected
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
- set_unexpected
helpviewer_keywords:
- set_unexpected function
- unexpected function
- exception handling, termination
ms.assetid: ebcef032-4771-48e5-88aa-2a1ab8750aa6
ms.openlocfilehash: 6c38421e447ca7b3f263148f51f0ade5c59e2804
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62356403"
---
# <a name="setunexpected-crt"></a>set_unexpected(CRT)

**unexpected**로 호출하는 자체 종료 함수를 설치합니다.

## <a name="syntax"></a>구문

```cpp
unexpected_function set_unexpected( unexpected_function unexpFunction );
```

### <a name="parameters"></a>매개 변수

*unexpFunction*<br/>
대체를 작성 하는 함수에 대 한 포인터를 **예기치 않은** 함수입니다.

## <a name="return-value"></a>반환 값

등록 한 이전 종료 함수에 대 한 포인터를 반환 **_set_unexpected** 이전 함수는 나중에 복원할 수 있도록 합니다. 기본 동작을 복원 하려면 반환 값을 사용할 수 없는 이전 함수가 설정 된 경우 이 값이 있을 **NULL**합니다.

## <a name="remarks"></a>설명

합니다 **set_unexpected** 설치 함수 *unexpFunction* 호출한 함수로 **예기치 않은**합니다. **예기치 않은** 현재에서 사용 되지 않습니다 C++ 예외 처리 구현 합니다. 합니다 **unexpected_function** EH에 형식이 정의 되어 있습니다. 사용자 정의 unexpected 함수 포인터로 H *unexpFunction* 반환 **void**합니다. 사용자 지정 *unexpFunction* 함수 호출자에 게 반환 되어서는 안 됩니다.

```cpp
typedef void ( *unexpected_function )( );
```

기본적으로 **예기치 않은** 호출 **종료**합니다. 하는 자체 종료 함수를 작성 하 고 호출 하 여이 기본 동작을 변경할 수 있습니다 **set_unexpected** 인수로 함수의 이름입니다. **예기치 않은** 인수로 주어진 마지막 함수 호출 **set_unexpected**합니다.

호출 하 여 설치 하는 사용자 지정 종료 함수와 달리 **set_terminate**, 내에서 예외가 throw 될 수 있습니다 *unexpFunction*합니다.

다중 스레드 환경에서 unexpected 함수는 각 스레드에 대해 개별적으로 유지 관리됩니다. 각 새 스레드는 자체 unexpected 함수를 설치해야 합니다. 따라서 각 스레드는 자체 unexpected 처리를 담당합니다.

현재 Microsoft 구현에서 C++ 예외 처리 **예기치 않은** 호출 **종료** 기본적으로 예외 처리 런타임 라이브러리에서 호출 되지 됩니다. 호출에 특별 한 이점은 없으며 방법이 **예기치 않은** 대신 **종료**합니다.

단일 **set_unexpected** 처리기에 대 한 모든 동적으로 연결 된 Dll 또는 Exe; 호출 하는 경우에 **set_unexpected** 처리기 바꿀 수 있습니다 하거나 설정 하는 처리기로 바뀌거나 사용자 다른 DLL 또는 EXE

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**set_unexpected**|\<eh.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[예외 처리 루틴](../../c-runtime-library/exception-handling-routines.md)<br/>
[abort](abort.md)<br/>
[_get_unexpected](get-unexpected.md)<br/>
[set_terminate](set-terminate-crt.md)<br/>
[terminate](terminate-crt.md)<br/>
[unexpected](unexpected-crt.md)<br/>
