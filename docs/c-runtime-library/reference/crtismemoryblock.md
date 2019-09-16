---
title: _CrtIsMemoryBlock
ms.date: 11/04/2016
api_name:
- _CrtIsMemoryBlock
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
- CrtlsMemoryBlock
- _CrtIsMemoryBlock
helpviewer_keywords:
- _CrtIsMemoryBlock function
- CrtIsMemoryBlock function
ms.assetid: f7cbbc60-3690-4da0-a07b-68fd7f250273
ms.openlocfilehash: f29745acd06f6f5b3fa96367444e800bdc3e8e3a
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70938730"
---
# <a name="_crtismemoryblock"></a>_CrtIsMemoryBlock

지정된 메모리 블록이 로컬 힙 내에 있고 유효한 디버그 힙 블록 형식 식별자를 포함하는지 확인합니다(디버그 버전에만 해당).

## <a name="syntax"></a>구문

```C
int _CrtIsMemoryBlock(
   const void *userData,
   unsigned int size,
   long *requestNumber,
   char **filename,
   int *linenumber
);
```

### <a name="parameters"></a>매개 변수

*userData*<br/>
확인할 메모리 블록의 시작 부분에 대한 포인터입니다.

*size*<br/>
지정된 블록의 크기(바이트)입니다.

*requestNumber*<br/>
블록의 할당 번호 또는 **NULL**에 대 한 포인터입니다.

*filename*<br/>
블록 또는 **NULL**을 요청한 소스 파일의 이름에 대 한 포인터입니다.

*linenumber*<br/>
소스 파일의 줄 번호 또는 **NULL**에 대 한 포인터입니다.

## <a name="return-value"></a>반환 값

**_CrtIsMemoryBlock** 는 지정 된 메모리 블록이 로컬 힙 내에 있고 유효한 디버그 힙 블록 형식 식별자를 포함 하는 경우 **TRUE** 를 반환 합니다. 그렇지 않으면 함수는 **FALSE**를 반환 합니다.

## <a name="remarks"></a>설명

**_CrtIsMemoryBlock** 함수는 지정 된 메모리 블록이 응용 프로그램의 로컬 힙 내에 있고 유효한 블록 형식 식별자를 포함 하는지 확인 합니다. 또한 이 함수는 메모리 블록 할당이 원래 요청된 경우 개체 할당 순서 번호 및 소스 파일 이름/줄 번호를 가져오는 데도 사용할 수 있습니다. *Requestnumber*, *filename*또는 *linenumber* 매개 변수에**NULL** 이 아닌 값을 전달 하면 **_CrtIsMemoryBlock** 에서 다음 매개 변수를 메모리 블록의 디버그 헤더에 있는 값으로 설정 합니다. 로컬 힙. [_Debug](../../c-runtime-library/debug.md) 가 정의 되지 않은 경우 전처리 중에 **_CrtIsMemoryBlock** 에 대 한 호출이 제거 됩니다.

**_CrtIsMemoryBlock** 가 실패 하면 **FALSE** 를 반환 하 고 출력 매개 변수가 기본값으로 초기화 됩니다. *requestnumber* 와 **lineNumber** 는 0으로 설정 되 고 *filename* 은 **NULL**로 설정 됩니다.

이 함수는 **TRUE** 또는 **FALSE**를 반환하므로 이를 [_ASSERT](assert-asserte-assert-expr-macros.md) 매크로 중 하나로 전달하여 간단한 디버깅 오류 처리 메커니즘을 만들 수 있습니다. 다음 예제에서는 지정된 주소가 로컬 힙 내에 없을 경우 어설션 오류가 발생하는 경우를 보여 줍니다.

```C
_ASSERTE( _CrtIsMemoryBlock( userData, size, &requestNumber,
          &filename, &linenumber ) );
```

다른 디버그 함수 및 매크로와 함께 **_CrtIsMemoryBlock** 를 사용 하는 방법에 대 한 자세한 내용은 [보고 매크로](/visualstudio/debugger/macros-for-reporting)를 참조 하세요. 기본 힙의 디버그 버전에서 메모리 블록을 할당, 초기화 및 관리하는 방법에 대한 자세한 내용은 [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details)를 참조하세요.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_CrtIsMemoryBlock**|\<crtdbg.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="libraries"></a>라이브러리

[C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)의 디버그 버전만 해당됩니다.

## <a name="example"></a>예제

[_CrtIsValidHeapPointer](crtisvalidheappointer.md) 항목에 대한 예제를 참조하세요.

## <a name="see-also"></a>참고자료

[디버그 루틴](../../c-runtime-library/debug-routines.md)<br/>
