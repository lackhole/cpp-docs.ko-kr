---
title: fsetpos
ms.date: 11/04/2016
apiname:
- fsetpos
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
- fsetpos
helpviewer_keywords:
- streams, setting position indicators
- fsetpos function
ms.assetid: 6d19ff48-1a2b-47b3-9f23-ed0a47b5a46e
ms.openlocfilehash: 9854c71e381da6ec9a75d440b9588e2476bada7c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62287575"
---
# <a name="fsetpos"></a>fsetpos

스트림 위치 표시기를 설정합니다.

## <a name="syntax"></a>구문

```C
int fsetpos(
   FILE *stream,
   const fpos_t *pos
);
```

### <a name="parameters"></a>매개 변수

*stream*<br/>
**FILE** 구조체에 대한 포인터입니다.

*pos*<br/>
위치 표시기 스토리지입니다.

## <a name="return-value"></a>반환 값

성공 하면 **fsetpos** 0을 반환 합니다. 함수 실패 시 0이 아닌 값을 반환 하 고 설정 **errno** 다음 중 하나를 매니페스트 상수 (ERRNO에 정의 합니다. H): **EBADF**, 즉, 파일에 액세스할 수 없는 또는 개체는 *스트림* 가리키는 유효한 파일 구조는 아닙니다. 또는 **EINVAL**, 즉, 잘못 된 값에 대 한 *스트림*  나 *pos* 전달 되었습니다. 잘못된 매개 변수가 전달되면 이러한 함수는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)의 설명대로 잘못된 매개 변수 처리기를 호출합니다.

이러한 반환 코드 및 기타 반환 코드에 대한 자세한 내용은 [_doserrno, errno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.

## <a name="remarks"></a>설명

합니다 **fsetpos** 함수에 대 한 파일 위치 표시기를 설정 합니다. *스트림을* 의 값으로 *pos*에 대 한 이전 호출에서 가져온 **fgetpos**에 대해 *스트림을*합니다. 함수는 파일 끝 표시기를 지우고의 효과 실행 취소 [ungetc](ungetc-ungetwc.md) 온 *스트림*합니다. 호출한 후 **fsetpos**에서 다음 작업 *스트림* 수 중 입력 또는 출력 될 수 있습니다.

## <a name="requirements"></a>요구 사항

|기능|필수 헤더|
|--------------|---------------------|
|**fsetpos**|\<stdio.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

[fgetpos](fgetpos.md)의 예제를 참조하세요.

## <a name="see-also"></a>참고자료

[스트림 I/O](../../c-runtime-library/stream-i-o.md)<br/>
[fgetpos](fgetpos.md)<br/>
