---
title: _aligned_offset_malloc
ms.date: 11/04/2016
apiname:
- _aligned_offset_malloc
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
- _aligned_offset_malloc
- aligned_offset_malloc
helpviewer_keywords:
- _aligned_offset_malloc function
- aligned_offset_malloc function
ms.assetid: 447681a3-7c95-4655-86ba-fa3a4ca4c521
ms.openlocfilehash: 824edfd8bb96d805a030fb205dee62fa9eb4fd06
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62341771"
---
# <a name="alignedoffsetmalloc"></a>_aligned_offset_malloc

지정된 맞춤 경계에 메모리를 할당합니다.

## <a name="syntax"></a>구문

```C
void * _aligned_offset_malloc(
   size_t size,
   size_t alignment,
   size_t offset
);
```

### <a name="parameters"></a>매개 변수

*size*<br/>
요청된 메모리 할당 크기입니다.

*alignment*<br/>
맞춤 값으로 2의 정수 거듭제곱이어야 합니다.

*offset*<br/>
맞춤을 강제하는 메모리 할당으로의 오프셋입니다.

## <a name="return-value"></a>반환 값

할당 된 메모리 블록에 대 한 포인터 또는 **NULL** 작업이 실패 합니다.

## <a name="remarks"></a>설명

**_aligned_offset_malloc** 는 중첩된 된 요소에 맞춤이 필요한 상황에서 유용 예를 들어 중첩된 된 클래스에 맞춤이 필요한 경우.

**_aligned_offset_malloc** 더해서 **malloc**; 자세한 내용은 참조 하십시오 [malloc](malloc.md)합니다.

**_aligned_offset_malloc** 표시 됩니다 `__declspec(noalias)` 고 `__declspec(restrict)`는 함수가 전역 변수를 수정할 수 없도록 보장 되는 및 포인터에 별칭이 지정 되지 반환 함을 의미 합니다. 자세한 내용은 [noalias](../../cpp/noalias.md) 및 [restrict](../../cpp/restrict.md)를 참조하세요.

이 함수를 설정 합니다 **errno** 하 **ENOMEM** 메모리 할당에 실패 하는 경우 또는 요청된 된 크기 보다 큰 되었으면 **_HEAP_MAXREQ**합니다. 에 대 한 자세한 내용은 **errno**를 참조 하십시오 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)합니다. 또한 **_aligned_offset_malloc** 해당 매개 변수 유효성을 검사 합니다. 하는 경우 *맞춤* 2의 거듭제곱이 아닌 경우 *오프셋* 보다 크거나 같음 *크기* 0이 아닌 경우이 함수는 잘못 된 매개 변수 처리기를 호출 에설명된대로[ 매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행을 계속 하도록 허용 된 경우이 함수를 반환 합니다 **NULL** 집합과 **errno** 하 **EINVAL**합니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_aligned_offset_malloc**|\<malloc.h>|

## <a name="example"></a>예제

자세한 내용은 [_aligned_malloc](aligned-malloc.md)를 참조하세요.

## <a name="see-also"></a>참고자료

[데이터 맞춤](../../c-runtime-library/data-alignment.md)<br/>
