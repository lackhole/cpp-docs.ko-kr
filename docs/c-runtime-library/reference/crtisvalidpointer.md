---
title: _CrtIsValidPointer
ms.date: 11/04/2016
apiname:
- _CrtIsValidPointer
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
- CrtlsValidPointer
- _CrtIsValidPointer
helpviewer_keywords:
- CrtIsValidPointer function
- _CrtIsValidPointer function
ms.assetid: 91c35590-ea5e-450f-a15d-ad8d62ade1fa
ms.openlocfilehash: 64197d460cdb7dd26d22196c08151be09df48573
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62339327"
---
# <a name="crtisvalidpointer"></a>_CrtIsValidPointer

포인터가 null이 아닌지 확인합니다. Visual Studio 2010 이전 버전의 C 런타임 라이브러리에서 지정된 메모리 범위가 읽기 및 쓰기(디버그 버전에만 해당)에 유효한지 확인합니다.

## <a name="syntax"></a>구문

```C
int _CrtIsValidPointer(
   const void *address,
   unsigned int size,
   int access
);
```

### <a name="parameters"></a>매개 변수

*address*<br/>
유효성 테스트를 위한 메모리 범위의 시작 부분을 가리킵니다.

*size*<br/>
지정된 메모리 범위의 크기입니다(바이트).

*access*<br/>
메모리 범위 확인을 위한 읽기/쓰기 접근성입니다.

## <a name="return-value"></a>반환 값

**_CrtIsValidPointer** 는 지정된 된 포인터가 null이 아닌 경우 TRUE를 반환 합니다. Visual Studio 2010 이전의 CRT 라이브러리 버전에서, 메모리 범위가 지정된 작업에 유효한 경우 TRUE가 반환됩니다. 그렇지 않은 경우 이 함수는 FALSE를 반환합니다.

## <a name="remarks"></a>설명

Visual Studio 2010의 CRT 라이브러리를 사용 하 여 시작 합니다 *크기* 및 *액세스* 매개 변수가 무시 됩니다 및 **_CrtIsValidPointer** 확인만 지정된 *주소* null이 아닙니다. 이 테스트는 직접 수행하기 쉽기 때문에, 이 함수를 사용하지 않는 것이 좋습니다. Visual Studio 2010 이전 버전에서는 함수 확인에 시작 하는 메모리 범위 *주소* 되는데 *크기* 바이트는 지정 된 액세스 가능 작업에 유효 합니다. 때 *액세스* 가 TRUE로 설정 하는 메모리 범위 읽기와 쓰기에 대 한 확인 합니다. 때 *액세스* 은 FALSE, 메모리 범위가 읽기에 대 한 유효성 검사만 수행 합니다. 때 [_DEBUG](../../c-runtime-library/debug.md) 가 정의 되지 않은, 호출 **_CrtIsValidPointer** 전처리 중 제거 됩니다.

이 함수는 TRUE 또는 FALSE를 반환하므로 이를 [_ASSERT](assert-asserte-assert-expr-macros.md) 매크로 중 하나로 전달하여 간단한 디버깅 오류 처리 메커니즘을 만들 수 있습니다. 다음 예제에서는 메모리 범위가 읽기 및 쓰기 작업 둘 다에 대해 유효하지 않은 경우 어설션 실패를 발생하게 합니다.

```C
_ASSERTE( _CrtIsValidPointer( address, size, TRUE ) );
```

방법에 대 한 자세한 내용은 **_CrtIsValidPointer** 내용은 다른 디버그 함수 및 매크로 함께 사용할 수 있습니다 [보고서 매크로](/visualstudio/debugger/macros-for-reporting)합니다. 기본 힙의 디버그 버전에서 메모리 블록을 할당, 초기화 및 관리하는 방법에 대한 자세한 내용은 [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details)를 참조하세요.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_CrtIsValidPointer**|\<crtdbg.h>|

**_CrtIsValidPointer** Microsoft 확장입니다. 호환성에 대한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="libraries"></a>라이브러리

[C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)의 디버그 버전만 해당됩니다.

## <a name="example"></a>예제

[_CrtIsValidHeapPointer](crtisvalidheappointer.md) 항목에 대한 예제를 참조하세요.

## <a name="see-also"></a>참고자료

[디버그 루틴](../../c-runtime-library/debug-routines.md)<br/>
