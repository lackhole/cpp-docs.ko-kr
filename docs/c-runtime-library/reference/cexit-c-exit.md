---
title: _cexit, _c_exit
ms.date: 11/04/2016
apiname:
- _c_exit
- _cexit
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
- _cexit
- c_exit
- _c_exit
- cexit
helpviewer_keywords:
- cleanup operations during processes
- cexit function
- _c_exit function
- _cexit function
- c_exit function
ms.assetid: f3072045-9924-4b1a-9fef-b0dcd6d12663
ms.openlocfilehash: a075e8a8e965a195765b86ffa21fed0915dbf5ab
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62335492"
---
# <a name="cexit-cexit"></a>_cexit, _c_exit

정리 작업을 수행하고 프로세스 종료 없이 반환합니다.

## <a name="syntax"></a>구문

```C
void _cexit( void );
void _c_exit( void );
```

## <a name="remarks"></a>설명

합니다 **_cexit** 마지막-, lifo (후입선출) 순서에 의해 등록 된 함수 호출 함수 **atexit** 하 고 **_onexit**합니다. 그런 다음 **_cexit** 모든 I/O 버퍼를 플러시하고 반환 하기 전에 모든 열린 스트림을 닫습니다. **_c_exit** 같습니다 **_exit** 처리 하지 않고 호출 프로세스로 반환 하지만 **atexit** 하거나 **_onexit** 스트림 버퍼를 플러시하지 또는 합니다. 동작은 **종료**, **_exit**, **_cexit**, 및 **_c_exit** 표에 표시 됩니다.

|함수|동작|
|--------------|--------------|
|**exit**|전체 C 라이브러리 종료 절차를 수행하고, 프로세스를 종료하고, 제공된 상태 코드와 함께 종료됩니다.|
|**_exit**|빠른 C 라이브러리 종료 절차를 수행하고, 프로세스를 종료하고, 제공된 상태 코드와 함께 종료됩니다.|
|**_cexit**|전체 C 라이브러리 종료 절차를 수행하고 호출자에게 반환하지만, 프로세스를 종료하지 않습니다.|
|**_c_exit**|빠른 C 라이브러리 종료 절차를 수행하고 호출자에게 반환하지만, 프로세스를 종료하지 않습니다.|

호출 하는 경우는 **_cexit** 하거나 **_c_exit** 함수 호출 시 존재 하는 임시 또는 자동 개체에 대 한 소멸자가 호출 되지 않습니다. 자동 개체는 개체가 정적으로 선언되지 않은 함수에서 정의된 개체입니다. 임시 개체는 컴파일러에 의해 생성된 개체입니다. 호출 하기 전에 자동 개체 소멸 시킬 **_cexit** 또는 **_c_exit**, 명시적으로 다음과 같은 개체에 대 한 소멸자를 호출 합니다.

```cpp
myObject.myClass::~myClass( );
```

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_cexit**|\<process.h>|
|**_c_exit**|\<process.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[프로세스 및 환경 제어](../../c-runtime-library/process-and-environment-control.md)<br/>
[abort](abort.md)<br/>
[atexit](atexit.md)<br/>
[_exec, _wexec 함수](../../c-runtime-library/exec-wexec-functions.md)<br/>
[exit, _Exit, _exit](exit-exit-exit.md)<br/>
[_onexit, _onexit_m](onexit-onexit-m.md)<br/>
[_spawn, _wspawn 함수](../../c-runtime-library/spawn-wspawn-functions.md)<br/>
[system, _wsystem](system-wsystem.md)<br/>
