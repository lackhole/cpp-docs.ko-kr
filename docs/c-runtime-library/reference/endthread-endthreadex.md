---
title: _endthread, _endthreadex
ms.date: 11/04/2016
api_name:
- _endthread
- _endthreadex
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
- api-ms-win-crt-runtime-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _endthread
- endthreadex
- _endthreadex
- endthread
helpviewer_keywords:
- _endthread function
- endthread function
- terminating threads
- endthreadex function
- _endthreadex function
- threading [C++], terminating threads
ms.assetid: 18a91f2f-659e-40b4-b266-ec12dcf2abf5
ms.openlocfilehash: c9dd4a49e534e8fa3e0f5ac735faccb4b0f65af5
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70937729"
---
# <a name="_endthread-_endthreadex"></a>_endthread, _endthreadex

스레드를 종료 합니다. **_endthread** 는 **_beginthread** 에서 만든 스레드를 종료 하 고 **_endthreadex** 는 **_beginthreadex**에서 만든 스레드를 종료 합니다.

## <a name="syntax"></a>구문

```C
void _endthread( void );
void _endthreadex(
   unsigned retval
);
```

### <a name="parameters"></a>매개 변수

*retval*<br/>
스레드 종료 코드입니다.

## <a name="remarks"></a>설명

**_Endthread** 또는 **_endthreadex** 를 명시적으로 호출 하 여 스레드를 종료할 수 있습니다. 그러나 **_endthread** 또는 **_endthreadex** 는 스레드가 매개 변수로 전달 된 루틴에서 반환 될 때 **_beginthread** 또는 **_beginthreadex**에 자동으로 호출 됩니다. **Endthread** 또는 **_endthreadex** 를 호출 하 여 스레드를 종료 하면 스레드에 할당 된 리소스의 적절 한 복구를 보장 하는 데 도움이 됩니다.

> [!NOTE]
> Libcmt.lib로 연결된 실행 파일의 경우 런타임 시스템이 할당된 리소스를 회수하지 않도록 Win32 [ExitThread](/windows/win32/api/processthreadsapi/nf-processthreadsapi-exitthread) API를 호출하지 마세요. **_endthread** 및 **_endthreadex** 는 할당 된 스레드 리소스를 회수 한 다음 **exitthread**를 호출 합니다.

**_endthread** 는 스레드 핸들을 자동으로 닫습니다. 이 동작은 Win32 **Exitthread** API와 다릅니다. 따라서 **_beginthread** 및 **_endthread**를 사용 하는 경우 Win32 [CloseHandle](/windows/win32/api/handleapi/nf-handleapi-closehandle) API를 호출 하 여 스레드 핸들을 명시적으로 닫지 마세요.

Win32 **exitthread** API와 마찬가지로 **_endthreadex** 는 스레드 핸들을 닫지 않습니다. 따라서 **_beginthreadex** 및 **_endthreadex**를 사용할 때는 Win32 **CloseHandle** API를 호출 하 여 스레드 핸들을 닫아야 합니다.

> [!NOTE]
> **_endthread** 및 **_endthreadex** 를 C++ 호출 하면 스레드에서 보류 중인 소멸자가 호출 되지 않습니다.

## <a name="requirements"></a>요구 사항

|기능|필수 헤더|
|--------------|---------------------|
|**_endthread**|\<process.h>|
|**_endthreadex**|\<process.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="libraries"></a>라이브러리

다중 스레드 버전의 유일한 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md) 입니다.

## <a name="example"></a>예제

[_beginthread](beginthread-beginthreadex.md)에 대한 예를 참조하세요.

## <a name="see-also"></a>참고자료

[프로세스 및 환경 제어](../../c-runtime-library/process-and-environment-control.md)<br/>
[_beginthread, _beginthreadex](beginthread-beginthreadex.md)<br/>
