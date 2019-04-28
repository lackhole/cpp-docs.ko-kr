---
title: _CrtCheckMemory
ms.date: 11/04/2016
apiname:
- _CrtCheckMemory
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
- CrtCheckMemory
- _CrtCheckMemory
helpviewer_keywords:
- _CrtCheckMemory function
- CrtCheckMemory function
ms.assetid: 457cc72e-60fd-4177-ab5c-6ae26a420765
ms.openlocfilehash: cb39a76c140934dabdd1269c02aba6018691f917
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62340393"
---
# <a name="crtcheckmemory"></a>_CrtCheckMemory

디버그 힙에서 할당된 메모리 블록의 무결성을 확인합니다(디버그 버전에만 해당).

## <a name="syntax"></a>구문

```C

int _CrtCheckMemory( void );
```

## <a name="return-value"></a>반환 값

성공 하면 **_CrtCheckMemory** 함수가 FALSE를 반환 합니다. 지 고, 그렇지 않으면 TRUE를 반환 합니다.

## <a name="remarks"></a>설명

합니다 **_CrtCheckMemory** 함수 기초적인 기본 힙을 확인 하 고 모든 메모리 블록을 검사 하 여 디버그 힙 관리자가 할당 된 메모리의 유효성을 검사 합니다. 기초적인 기본 힙, 디버그 헤더 정보 또는 덮어쓰기 버퍼에서 오류 또는 메모리 불일치가 발견 되 면 **_CrtCheckMemory** 오류 조건을 설명 하는 정보를 사용 하 여 디버그 보고서를 생성 합니다. 때 [_DEBUG](../../c-runtime-library/debug.md) 가 정의 되지 않은, 호출 **_CrtCheckMemory** 전처리 중 제거 됩니다.

동작 **_CrtCheckMemory** 의 비트 필드를 설정 하 여 제어할 수 있습니다 합니다 [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md) 플래그를 사용 하는 [_CrtSetDbgFlag](crtsetdbgflag.md) 함수. 설정 합니다 **_CRTDBG_CHECK_ALWAYS_DF** 비트 필드를 **_CrtCheckMemory** 메모리 할당 작업이 요청 될 때마다 호출 되 고 있습니다. 이 메서드는 실행 속도를 늦추지만, 오류를 신속하게 catch하는 데 유용합니다. 설정 된 **_CRTDBG_ALLOC_MEM_DF** 비트 필드를 끄면 **_CrtCheckMemory** 힙을 확인을 즉시 반환 하지 않고 **TRUE**합니다.

이 함수는 **TRUE** 또는 **FALSE**를 반환하므로 이를 [_ASSERT](assert-asserte-assert-expr-macros.md) 매크로 중 하나로 전달하여 간단한 디버깅 오류 처리 메커니즘을 만들 수 있습니다. 다음 예제에서는 힙에서 손상이 검색된 경우 어설션 실패가 발생합니다.

```C
_ASSERTE( _CrtCheckMemory( ) );
```

방법에 대 한 자세한 내용은 **_CrtCheckMemory** 내용은 다른 디버그 함수와 함께 사용할 수 있습니다 [힙 상태 보고 함수](/visualstudio/debugger/crt-debug-heap-details)합니다. 메모리 관리 및 디버그 힙의 개요는 [CRT 디버그 힙 정보](/visualstudio/debugger/crt-debug-heap-details)를 참조하세요.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_CrtCheckMemory**|\<crtdbg.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="libraries"></a>라이브러리

[C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)의 디버그 버전만 해당됩니다.

## <a name="example"></a>예제

샘플을 사용 하는 방법에 대 한 **_CrtCheckMemory**를 참조 하십시오 [crt_dbg1](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/crt_dbg1)합니다.

## <a name="see-also"></a>참고자료

[디버그 루틴](../../c-runtime-library/debug-routines.md)<br/>
[_crtDbgFlag](../../c-runtime-library/crtdbgflag.md)<br/>
[_CrtSetDbgFlag](crtsetdbgflag.md)<br/>
