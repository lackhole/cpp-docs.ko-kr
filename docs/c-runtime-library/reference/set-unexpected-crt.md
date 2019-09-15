---
title: set_unexpected(CRT)
ms.date: 11/04/2016
api_name:
- set_unexpected
api_location:
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- set_unexpected
helpviewer_keywords:
- set_unexpected function
- unexpected function
- exception handling, termination
ms.assetid: ebcef032-4771-48e5-88aa-2a1ab8750aa6
ms.openlocfilehash: 77c8f0ae8c64423a656a2ebbe1fe3ef6dbe1b794
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70948299"
---
# <a name="set_unexpected-crt"></a>set_unexpected(CRT)

**unexpected**로 호출하는 자체 종료 함수를 설치합니다.

## <a name="syntax"></a>구문

```cpp
unexpected_function set_unexpected( unexpected_function unexpFunction );
```

### <a name="parameters"></a>매개 변수

*unexpFunction*<br/>
**예기치 않은** 함수를 대체 하기 위해 작성 하는 함수에 대 한 포인터입니다.

## <a name="return-value"></a>반환 값

이전 함수를 나중에 복원할 수 있도록 **_set_unexpected** 에 의해 등록 된 이전 종료 함수에 대 한 포인터를 반환 합니다. 이전 함수를 설정 하지 않은 경우 반환 값을 사용 하 여 기본 동작을 복원할 수 있습니다. 이 값은 **NULL**일 수 있습니다.

## <a name="remarks"></a>설명

**Set_unexpected** 함수는 **예기치 않은**함수를 호출 하 *여 함수를 설치 합니다* . **예기치 않은** 은 현재 C++ 예외 처리 구현에서 사용 되지 않습니다. **Unexpected_function** 형식은 EH에 정의 되어 있습니다. H는 사용자 정의 예기치 않은 함수에 대 한 포인터로 서 **void**를 반환 하는 *unexpfunction 함수* 입니다. 사용자 지정 *함수* 함수는 해당 호출자에 게 반환 되어서는 안 됩니다.

```cpp
typedef void ( *unexpected_function )( );
```

기본적으로 **예기치 않은** 호출은 **종료**됩니다. 사용자 고유의 종료 함수를 작성 하 고 함수 이름을 인수로 사용 하 여 **set_unexpected** 를 호출 하 여이 기본 동작을 변경할 수 있습니다. **set_unexpected**에 대 한 인수로 지정 된 마지막 함수를 **예기치 않게** 호출 합니다.

**Set_terminate**에 대 한 호출로 설치 된 사용자 지정 종료 함수와 달리, *unexpfunction*내에서 예외가 throw 될 수 있습니다.

다중 스레드 환경에서 unexpected 함수는 각 스레드에 대해 개별적으로 유지 관리됩니다. 각 새 스레드는 자체 unexpected 함수를 설치해야 합니다. 따라서 각 스레드는 자체 unexpected 처리를 담당합니다.

현재 예외 처리의 C++ Microsoft 구현에서 **예기치 않은** 호출은 기본적으로 **종료** 되 고 예외 처리 런타임 라이브러리에 의해 호출 되지 않습니다. **종료**하는 것이 아니라 **예기치 않은** 호출에 대 한 특별 한 이점은 없습니다.

동적으로 연결 된 모든 Dll 또는 Exe에 대 한 단일 **set_unexpected** 처리기가 있습니다. **set_unexpected** 를 호출 하는 경우에도 처리기를 다른 것으로 바꾸거나 다른 DLL 또는 EXE로 설정한 처리기를 바꿀 수 있습니다.

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
