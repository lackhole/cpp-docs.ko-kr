---
title: _CrtSetAllocHook
ms.date: 11/04/2016
apiname:
- _CrtSetAllocHook
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
- _CrtSetAllocHook
- CrtSetAllocHook
helpviewer_keywords:
- _CrtSetAllocHook function
- CrtSetAllocHook function
ms.assetid: 405df37b-2fd1-42c8-83bc-90887f17f29d
ms.openlocfilehash: cfa466ec4bce6034c15a627ccab4ee4bb0ef8f5b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62347404"
---
# <a name="crtsetallochook"></a>_CrtSetAllocHook

클라이언트 정의 할당 함수를 C 런타임 디버그 메모리 할당 프로세스에 연결함으로써 설치합니다(디버그 버전에만 해당).

## <a name="syntax"></a>구문

```C
_CRT_ALLOC_HOOK _CrtSetAllocHook(
   _CRT_ALLOC_HOOK allocHook
);
```

### <a name="parameters"></a>매개 변수

*allocHook*<br/>
C 런타임 디버그 메모리 할당 프로세스에 연결할 새로운 클라이언트 정의 할당 함수입니다.

## <a name="return-value"></a>반환 값

이전에 정의 된 할당 후크 함수를 반환 하거나 **NULL** 경우 *allocHook* 은 **NULL**합니다.

## <a name="remarks"></a>설명

**_CrtSetAllocHook** 응용 프로그램에서 C 런타임 디버그 라이브러리 메모리 할당 프로세스에 고유한 할당 함수를 후크 할 수 있습니다. 결과적으로 메모리 블록을 할당, 재할당 또는 해제하기 위해 디버그 할당 함수를 호출할 때마다 애플리케이션의 후크 함수 호출이 트리거됩니다. **_CrtSetAllocHook** 를 쉽게 테스트 응용 프로그램에서 메모리 부족 상황을 처리 하는 방법에 대 한 할당 패턴 및 기회에 대 한 할당 정보를 나중에 로그를 검사 하는 기능을 사용 하 여 응용 프로그램을 제공 합니다. 분석 합니다. 때 [_DEBUG](../../c-runtime-library/debug.md) 가 정의 되지 않은, 호출 **_CrtSetAllocHook** 전처리 중 제거 됩니다.

합니다 **_CrtSetAllocHook** 함수에 지정 된 새로운 클라이언트 정의 할당 함수를 설치 *allocHook* 하 고 이전에 정의 된 후크 함수를 반환 합니다. 다음 예제에서는 클라이언트 정의 할당 후크가 어떻게 프로토타입화되어야 하는지 보여 줍니다.

```C
int YourAllocHook( int allocType, void *userData, size_t size,
                   int blockType, long requestNumber,
                   const unsigned char *filename, int lineNumber);
```

합니다 **allocType** 인수는 할당 연산의 형식을 지정 합니다. (**_HOOK_ALLOC**에 **_HOOK_REALLOC**, 및 **_HOOK_FREE**)는 할당의 후크 함수에 대 한 호출을 트리거됩니다. 트리거 할당 형식이 표시 되는 경우 **_HOOK_FREE**를 *userData* 해제에 대 한 메모리 블록의 사용자 데이터 섹션에 대 한 포인터입니다. 그러나 트리거 할당 형식이 **_HOOK_ALLOC** 또는 **_HOOK_REALLOC**에 *userData* 됩니다 **NULL** 메모리 차단 하기 때문에 할당 되지 않은 아직 있습니다.

*크기* 메모리의 크기 (바이트)를 차단 지정 *blockType* 메모리 블록의 형식을 나타내는 *requestNumber* 메모리 블록의 개체 할당 순서 번호는 경우 사용 가능한 *filename* 하 고 **lineNumber** 트리거 할당 작업이 시작 된 위치로 소스 파일 이름과 줄 번호를 지정 합니다.

후크 함수에서 프로세스가 완료되면 후크 함수는 부울 값을 반환해야 합니다. 이를 통해 기본 C 런타임 할당 프로세스에 계속 진행하는 방식을 알려 줍니다. 후크 함수에서 기본 할당 프로세스를 계속 진행으로 경우 후크 함수가 호출 되지 했습니다 후크 함수를 반환 해야를 하려는 경우 **TRUE**합니다. 이렇게 하면 원래 트리거 할당 작업이 실행됩니다. 이 구현을 사용하여, 후크 함수는 현재 할당 작업 또는 디버그 힙의 상태를 방해하지 않고 향후 분석을 위해 할당 정보를 수집하고 저장할 수 있습니다.

후크 함수에서 기본 할당 프로세스 트리거 할당 작업이 호출 된 및 실패 했을 경우 후크 함수가 반환할으로 계속 실행 하려는 하는 경우 **FALSE**합니다. 이 구현을 사용하여, 후크 함수는 다양한 메모리 조건 및 디버그 힙 상태를 시뮬레이트하여 애플리케이션에서 각 상황을 처리하는 방법을 테스트할 수 있습니다.

후크 함수를 지우려면 전달 **NULL** 하 **_CrtSetAllocHook**합니다.

방법에 대 한 자세한 내용은 **_CrtSetAllocHook** 내용은 고유한 클라이언트 정의 후크 함수를 작성 하는 방법 또는 다른 메모리 관리 함수를 사용 하 여 사용할 수 있습니다 [디버그 후크 함수 작성](/visualstudio/debugger/debug-hook-function-writing)합니다.

> [!NOTE]
> **_CrtSetAllocHook** 는 지원 되지 않습니다 **/clr: pure**합니다. 합니다 **/clr: pure** 및 **/clr: safe** 컴파일러 옵션은 Visual Studio 2015에서 사용 되지 않으며 Visual Studio 2017에서 제거 합니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_CrtSetAllocHook**|\<crtdbg.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="libraries"></a>라이브러리

[C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)의 디버그 버전만 해당됩니다.

## <a name="example"></a>예제

샘플을 사용 하는 방법에 대 한 **_CrtSetAllocHook**를 참조 하십시오 [crt_dbg2](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/crt_dbg2)합니다.

## <a name="see-also"></a>참고자료

[디버그 루틴](../../c-runtime-library/debug-routines.md)<br/>
[_CrtGetAllocHook](crtgetallochook.md)<br/>
