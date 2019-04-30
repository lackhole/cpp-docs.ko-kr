---
title: _CrtSetDumpClient
ms.date: 11/04/2016
apiname:
- _CrtSetDumpClient
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
- _CrtSetDumpClient
- CrtSetDumpClient
helpviewer_keywords:
- _CrtSetDumpClient function
- CrtSetDumpClient function
ms.assetid: f3dd06d0-c331-4a12-b68d-25378d112033
ms.openlocfilehash: 09f319f6298dbec6b229b2923bd86fc9b50314de
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64342991"
---
# <a name="crtsetdumpclient"></a>_CrtSetDumpClient

덤프는 응용 프로그램 정의 함수를 설치 **_CLIENT_BLOCK** 형식 메모리 블록 (디버그 버전에만 해당).

## <a name="syntax"></a>구문

```C
_CRT_DUMP_CLIENT _CrtSetDumpClient( _CRT_DUMP_CLIENT dumpClient );
```

### <a name="parameters"></a>매개 변수

*dumpClient*<br/>
C 런타임 디버그 메모리 덤프 프로세스에 연결할 새로운 클라이언트 정의 메모리 덤프 함수입니다.

## <a name="return-value"></a>반환 값

이전에 정의된 클라이언트 블록 덤프 함수를 반환합니다.

## <a name="remarks"></a>설명

합니다 **_CrtSetDumpClient** 함수를 사용 하면 응용 프로그램에 저장 된 덤프 개체에는 자체 함수를 후크 **_CLIENT_BLOCK** 메모리 블록의 C 런타임 디버그 메모리 덤프 프로세스입니다. 결과적으로, 매번 디버그 덤프 함수가 같은 [_CrtMemDumpAllObjectsSince](crtmemdumpallobjectssince.md) 하거나 [_CrtDumpMemoryLeaks](crtdumpmemoryleaks.md) 덤프를 **_CLIENT_BLOCK** 메모리 블록, 응용 프로그램의 덤프 함수 에서도 호출 됩니다. **_CrtSetDumpClient** 메모리 누수를 탐지 및 유효성 검사 또는 저장 된 데이터의 내용을 보고에 대 한 응용 프로그램을 쉽게 메서드로 제공 **_CLIENT_BLOCK** 블록입니다. 때 [_DEBUG](../../c-runtime-library/debug.md) 가 정의 되지 않은, 호출 **_CrtSetDumpClient** 전처리 중 제거 됩니다.

합니다 **_CrtSetDumpClient** 함수에 지정 된 새 응용 프로그램 정의 덤프 함수를 설치 *dumpClient* 하 고 이전에 정의 된 덤프 함수를 반환 합니다. 클라이언트 블록 덤프 함수의 예제는 다음과 같습니다.

```C
void DumpClientFunction( void *userPortion, size_t blockSize );
```

합니다 *userPortion* 인수는 메모리 블록의 사용자 데이터 부분의 시작 부분에 대 한 포인터 및 *blockSize* 바이트에서 블록 할당된 된 메모리의 크기를 지정 합니다. 클라이언트 블록 덤프 함수를 반환 해야 합니다 **void**합니다. 에 전달 되는 클라이언트 덤프 함수에 대 한 포인터 **_CrtSetDumpClient** 유형의 **_CRT_DUMP_CLIENT**Crtdbg.h에 정의 된 대로:

```C
typedef void (__cdecl *_CRT_DUMP_CLIENT)( void *, size_t );
```

작동 하는 함수에 대 한 자세한 내용은 **_CLIENT_BLOCK** 형식 메모리 블록을 참조 하십시오 [클라이언트 블록 후크 함수](/visualstudio/debugger/client-block-hook-functions)합니다. [_CrtReportBlockType](crtreportblocktype.md) 함수는 블록 형식과 하위 형식에 대한 정보를 반환하는 데 사용할 수 있습니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_CrtSetDumpClient**|\<crtdbg.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="libraries"></a>라이브러리

[C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)의 디버그 버전만 해당됩니다.

## <a name="see-also"></a>참조

[디버그 루틴](../../c-runtime-library/debug-routines.md)<br/>
[_CrtReportBlockType](crtreportblocktype.md)<br/>
[_CrtGetDumpClient](crtgetdumpclient.md)<br/>
