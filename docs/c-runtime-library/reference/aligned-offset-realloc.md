---
title: _aligned_offset_realloc
ms.date: 11/04/2016
apiname:
- _aligned_offset_realloc
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
- api-ms-win-crt-heap-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- aligned_offset_realloc
- _aligned_offset_realloc
helpviewer_keywords:
- aligned_offset_realloc function
- _aligned_offset_realloc function
ms.assetid: e0263533-991e-41b0-acc9-1b8a51ab9ecd
ms.openlocfilehash: d5f87f9bdfff262826b8d4cc4da86069588cf9db
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62341459"
---
# <a name="alignedoffsetrealloc"></a>_aligned_offset_realloc

[_aligned_malloc](aligned-malloc.md) 또는 [_aligned_offset_malloc](aligned-offset-malloc.md)를 사용하여 할당된 메모리 블록의 크기를 변경합니다.

## <a name="syntax"></a>구문

```C
void * _aligned_offset_realloc(
   void *memblock,
   size_t size,
   size_t alignment,
   size_t offset
);
```

### <a name="parameters"></a>매개 변수

*memblock*<br/>
현재 메모리 블록 포인터입니다.

*size*<br/>
메모리 할당의 크기입니다.

*alignment*<br/>
맞춤 값으로 2의 정수 거듭제곱이어야 합니다.

*offset*<br/>
맞춤을 강제하는 메모리 할당으로의 오프셋입니다.

## <a name="return-value"></a>반환 값

**_aligned_offset_realloc** 다시 할당 (그리고 이동 되었을 수 있는) 메모리 블록에 대 한 void 포인터를 반환 합니다. 반환 값은 **NULL** 는 크기가 0이 고 버퍼 인수가 아닙니다 **NULL**, 충분 한 사용 가능한 메모리 블록을 지정 된 크기로 확장할 수 없는 경우 또는 합니다. 첫 번째 경우 원래 블록이 해제됩니다. 두 번째 경우 원래 블록은 변경되지 않습니다. 반환 값은 모든 형식의 개체 스토리지를 위해 적절하게 맞도록 보장되어 있는 스토리지 공간을 가리킵니다. void가 아닌 형식의 포인터를 얻으려면 반환 값에 형식 캐스팅을 사용합니다.

**_aligned_offset_realloc** 표시 됩니다 `__declspec(noalias)` 고 `__declspec(restrict)`는 함수가 전역 변수를 수정할 수 없도록 보장 되는 및 포인터에 별칭이 지정 되지 반환 함을 의미 합니다. 자세한 내용은 [noalias](../../cpp/noalias.md) 및 [restrict](../../cpp/restrict.md)를 참조하세요.

## <a name="remarks"></a>설명

와 같은 [_aligned_offset_malloc](aligned-offset-malloc.md)하십시오 **_aligned_offset_realloc** 는 구조가 구조 내 오프셋에서 정렬 될 수 있도록 합니다.

**_aligned_offset_realloc** 더해서 **malloc**합니다. 사용에 대 한 자세한 내용은 **_aligned_offset_malloc**를 참조 하십시오 [malloc](malloc.md)합니다. 하는 경우 *memblock* 됩니다 **NULL**, 함수 호출 **_aligned_offset_malloc** 내부적으로 합니다.

이 함수를 설정 합니다 **errno** 하 **ENOMEM** 메모리 할당에 실패 하는 경우 또는 요청된 된 크기 보다 큰 되었으면 **_HEAP_MAXREQ**합니다. 에 대 한 자세한 내용은 **errno**를 참조 하십시오 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)합니다. 또한 **_aligned_offset_realloc** 해당 매개 변수 유효성을 검사 합니다. 하는 경우 *맞춤* 2의 거듭제곱이 아닌 경우 *오프셋* 보다 크거나 같음 *크기* 0이 아닌 경우이 함수는 잘못 된 매개 변수 처리기를 호출 에설명된대로[ 매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행을 계속 하도록 허용 된 경우이 함수를 반환 합니다 **NULL** 집합과 **errno** 하 **EINVAL**합니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_aligned_offset_realloc**|\<malloc.h>|

## <a name="example"></a>예제

자세한 내용은 [_aligned_malloc](aligned-malloc.md)를 참조하세요.

## <a name="see-also"></a>참고자료

[데이터 맞춤](../../c-runtime-library/data-alignment.md)<br/>
