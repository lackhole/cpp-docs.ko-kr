---
title: fwrite
ms.date: 11/04/2016
apiname:
- fwrite
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- fwrite
helpviewer_keywords:
- streams, writing data to
- fwrite function
ms.assetid: 7afacf3a-72d7-4a50-ba2e-bea1ab9f4124
ms.openlocfilehash: b4d6b9ce4fb66ee545f52946e28e4984d9e4f924
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62287549"
---
# <a name="fwrite"></a>fwrite

스트림에 데이터를 씁니다.

## <a name="syntax"></a>구문

```C
size_t fwrite(
   const void *buffer,
   size_t size,
   size_t count,
   FILE *stream
);
```

### <a name="parameters"></a>매개 변수

*buffer*<br/>
쓸 데이터에 대한 포인터입니다.

*size*<br/>
항목 크기입니다(바이트).

*count*<br/>
쓸 항목의 최대 수입니다.

*stream*<br/>
**FILE** 구조체에 대한 포인터입니다.

## <a name="return-value"></a>반환 값

**fwrite** 전체 개수를 반환 일 수 있는 실제로 기록 된 항목 보다 작거나 *개수* 오류가 발생 한 경우. 또한 오류가 발생하면 파일 위치 표시기를 확인할 수 없습니다. 이면 *스트림을* 하거나 *버퍼* 가 null 포인터인 경우 또는 유니코드 모드에서 홀수 바이트를 쓰도록가 지정 하는 경우 함수에 설명 된 대로 잘못 된 매개 변수 처리기를을 호출 하는 [ 매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 이 함수를 설정 하는 경우는 계속 실행 하도록 허용 합니다 **errno** 하 **EINVAL** 0을 반환 합니다.

## <a name="remarks"></a>설명

합니다 **fwrite** 함수 작성 *개수* 항목의 *크기* 길이 각각에서 *버퍼* 출력에 *stream*. 연결 된 파일 포인터 *스트림을* (있는 경우)는 실제로 쓴 바이트 수가 씩 증가 합니다. 하는 경우 *스트림을* 열릴 텍스트 모드에서 각 줄 바꿈은 캐리지 리턴-줄 바꿈 쌍으로 바뀝니다. 이렇게 바뀌더라도 반환 값에는 영향을 미치지 않습니다.

때 *스트림* 유니코드 변환 모드로 열리면-예를 들어, 경우 *스트림* 를 호출 하 여 열 **fopen** 포함 하는 모드 매개 변수를 사용 하 여 및 **ccs = 유니코드**, **ccs = u t F-16LE**, 또는 **ccs = u t F-8**를 사용 하 여 모드를 유니코드 변환 모드로 변경 된 경우 또는 **_setmode** 와 모드 매개 변수를 포함 하는 **_O_WTEXT**, **_O_U16TEXT**, 또는 **_O_U8TEXT**-*버퍼* 포인터로 해석 되는 배열을 **wchar_t** utf-16 형식으로 데이터를 포함 하는 합니다. 이 모드에서 홀수 바이트를 쓰려고 하면 매개 변수 유효성 검사 오류가 발생합니다.

이 함수는 호출 스레드를 잠그기 때문에 스레드로부터 안전하게 보호됩니다. 잠기지 않은 버전을 참조 하세요 **_fwrite_nolock**합니다.

## <a name="requirements"></a>요구 사항

|기능|필수 헤더|
|--------------|---------------------|
|**fwrite**|\<stdio.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

[fread](fread.md)의 예제를 참조하세요.

## <a name="see-also"></a>참고자료

[스트림 I/O](../../c-runtime-library/stream-i-o.md)<br/>
[_setmode](setmode.md)<br/>
[fread](fread.md)<br/>
[_fwrite_nolock](fwrite-nolock.md)<br/>
[_write](write.md)<br/>
