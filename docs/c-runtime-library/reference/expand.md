---
title: _expand
ms.date: 11/04/2016
apiname:
- _expand
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
- _bexpand
- fexpand
- expand
- nexpand
- _fexpand
- _nexpand
- bexpand
- _expand
helpviewer_keywords:
- memory blocks, changing size
- _expand function
- expand function
ms.assetid: 4ac55410-39c8-45c7-bccd-3f1042ae2ed3
ms.openlocfilehash: c1606bedbb1264bddb7674c829fe456f506d6584
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62335206"
---
# <a name="expand"></a>_expand

메모리 블록의 크기를 변경합니다.

## <a name="syntax"></a>구문

```C
void *_expand(
   void *memblock,
   size_t size
);
```

### <a name="parameters"></a>매개 변수

*memblock*<br/>
이전에 할당된 메모리 블록에 대한 포인터입니다.

*size*<br/>
새 크기(바이트)입니다.

## <a name="return-value"></a>반환 값

**_expand** 다시 할당된 된 메모리 블록에 대 한 void 포인터를 반환 합니다. **_expand**과 달리 **realloc**, 크기를 변경할 블록을 이동할 수 없습니다. 따라서 충분 한 메모리 블록을 이동 하지 않고 확장할 수 있는 경우는 *memblock* 매개 변수를 **_expand** 반환 값은 동일 합니다.

**_expand** 반환 **NULL** 작업 중 오류가 발견 된 경우. 예를 들어 있으면 **_expand** 는 메모리 블록을 축소 하기 위해 사용 될 수 있습니다 손상 작은 블록 힙의 이나 잘못 된 블록 포인터를 검색 하 고 반환 **NULL**합니다.

블록을 이동 하지 않고 지정 된 크기로 확장할 수 있는 메모리가 부족에 없으면 반환 **NULL**합니다. **_expand** 요청한 미만의 크기로 확장 된 블록을 반환 하지 않습니다. 오류가 발생 하는 경우 **errno** 오류의 특징을 나타냅니다. 에 대 한 자세한 내용은 **errno**를 참조 하십시오 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)합니다.

반환 값은 모든 형식의 개체 스토리지를 위해 적절하게 맞도록 보장되어 있는 스토리지 공간을 가리킵니다. 항목의 새 크기를 확인 하려면 사용 하 여 **_msize**합니다. 이외의 형식에 대 한 포인터를 가져오려면 **void**, 반환 값에 형식 캐스팅을 사용 합니다.

## <a name="remarks"></a>설명

합니다 **_expand** 함수 확장 하거나 힙에 있는 위치로 이동 하지 않고 블록을 축소 하 여 이전에 할당 된 메모리 블록의 크기를 변경 합니다. 합니다 *memblock* 매개 변수는 블록의 시작 부분을 가리킵니다. 합니다 *크기* 매개 변수는 바이트에서 블록의 새 크기를 제공 합니다. 블록의 콘텐츠는 새 크기와 이전 크기 중 더 짧은 크기까지 변경 사항이 없습니다. *memblock* 해제 된 블록을 하지 않아야 합니다.

> [!NOTE]
> 64 비트 플랫폼에서는 **_expand** 새 크기가 현재 크기 보다; 특히에서 작은 블록 크기가 16k 보다 작아 되었으며 낮은 조각화 힙에서 할당 하는 경우 블록을 축소할 수 없습니다 **확장 (_e)**  변경 하지 않고 블록을 떠나고 반환 *memblock*합니다.

응용 프로그램이 C 런타임 라이브러리의 디버그 버전과 연결 됩니다 **_expand** 로 확인 되 [_expand_dbg](expand-dbg.md)합니다. 디버깅 프로세스 동안 힙을 관리하는 방법에 대한 자세한 내용은 [CRT 디버그 힙](/visualstudio/debugger/crt-debug-heap-details)을 참조하세요.

이 함수는 해당 매개 변수의 유효성을 검사합니다. 하는 경우 *memblock* 가 null 포인터인 경우이 함수에 설명 된 대로 잘못 된 매개 변수 처리기를 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행을 계속 하도록 허용 된 경우 **errno** 로 설정 된 **EINVAL** 고 함수가 반환 **NULL**합니다. 하는 경우 *크기* 보다 크면 **_HEAP_MAXREQ**, **errno** 로 설정 되어 **ENOMEM** 반환 하 고 **NULL**.

## <a name="requirements"></a>요구 사항

|기능|필수 헤더|
|--------------|---------------------|
|**_expand**|\<malloc.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_expand.c

#include <stdio.h>
#include <malloc.h>
#include <stdlib.h>

int main( void )
{
   char *bufchar;
   printf( "Allocate a 512 element buffer\n" );
   if( (bufchar = (char *)calloc( 512, sizeof( char ) )) == NULL )
      exit( 1 );
   printf( "Allocated %d bytes at %Fp\n",
         _msize( bufchar ), (void *)bufchar );
   if( (bufchar = (char *)_expand( bufchar, 1024 )) == NULL )
      printf( "Can't expand" );
   else
      printf( "Expanded block to %d bytes at %Fp\n",
            _msize( bufchar ), (void *)bufchar );
   // Free memory
   free( bufchar );
   exit( 0 );
}
```

```Output
Allocate a 512 element buffer
Allocated 512 bytes at 002C12BC
Expanded block to 1024 bytes at 002C12BC
```

## <a name="see-also"></a>참고자료

[메모리 할당](../../c-runtime-library/memory-allocation.md)<br/>
[calloc](calloc.md)<br/>
[free](free.md)<br/>
[malloc](malloc.md)<br/>
[_msize](msize.md)<br/>
[realloc](realloc.md)<br/>
