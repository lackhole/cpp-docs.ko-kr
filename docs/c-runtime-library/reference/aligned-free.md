---
title: _aligned_free
ms.date: 11/04/2016
apiname:
- _aligned_free
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
- aligned_free
- _aligned_free
helpviewer_keywords:
- _aligned_free function
- aligned_free function
ms.assetid: ed1ce952-cdfc-4682-85cc-f75d4101603d
ms.openlocfilehash: e2d1dc1172d1cd0d31f8daa8125bd052252393c0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62341654"
---
# <a name="alignedfree"></a>_aligned_free

[_aligned_malloc](aligned-malloc.md) 또는 [_aligned_offset_malloc](aligned-offset-malloc.md)를 사용하여 할당된 메모리 블록을 해제합니다.

## <a name="syntax"></a>구문

```C
void _aligned_free (
   void *memblock
);
```

### <a name="parameters"></a>매개 변수

*memblock*<br/>
`_aligned_malloc` 또는 `_aligned_offset_malloc` 함수로 반환된 메모리 블록에 대한 포인터입니다.

## <a name="remarks"></a>설명

**_aligned_free** 표시 된 `__declspec(noalias)`에 함수가 전역 변수를 수정할 수 없도록 보장 되는 의미입니다. 자세한 내용은 [noalias](../../cpp/noalias.md)를 참조하세요.

이 함수는 다른 _aligned CRT 함수와 달리 매개 변수의 유효성을 검사하지 않습니다. 하는 경우 *memblock* NULL 포인터인 경우이 함수는 아무 작업도 수행 합니다. `errno`를 변경하지 않으며, 잘못된 매개 변수 처리기를 호출하지도 않습니다. 메모리 블록을 할당하기 위해 전에 _aligned 함수를 사용하지 않아 함수에 오류가 발생하거나 예기치 않은 문제 때문에 메모리 맞춤 오류가 발생하면 함수는 [_RPT, _RPTF, _RPTW, _RPTFW 매크로](rpt-rptf-rptw-rptfw-macros.md)에서 디버그 보고서를 생성합니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_aligned_free**|\<malloc.h>|

## <a name="example"></a>예제

자세한 내용은 [_aligned_malloc](aligned-malloc.md)를 참조하세요.

## <a name="see-also"></a>참고자료

[데이터 맞춤](../../c-runtime-library/data-alignment.md)