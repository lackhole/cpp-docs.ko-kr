---
title: _close
ms.date: 11/04/2016
apiname:
- _close
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
- _close
helpviewer_keywords:
- _close function
- close function
- files [C++], closing
ms.assetid: 4708a329-8acf-4cd9-b7b0-a952e1897247
ms.openlocfilehash: faea008903136e8abdc39297672b31800ada796d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62340016"
---
# <a name="close"></a>_close

파일을 닫습니다.

## <a name="syntax"></a>구문

```C
int _close(
   int fd
);
```

### <a name="parameters"></a>매개 변수

*fd*<br/>
열려 있는 파일을 참조하는 파일 설명자입니다.

## <a name="return-value"></a>반환 값

**_close** 파일을 성공적으로 닫은 경우 0을 반환 합니다. 반환 값이-1 오류를 나타냅니다.

## <a name="remarks"></a>설명

**_close** 함수에 연결 된 파일을 닫고 *fd*합니다.

파일 설명자와 기본 OS 파일 핸들을 닫습니다. 따라서 필요한 경우가 아니라면 호출 **CloseHandle** 파일을 원래 Win32 함수를 사용 하 여 연 경우 **CreateFile** 사용 하는 파일 설명자를 변환 및 **_open_osfhandle**.

이 함수는 해당 매개 변수의 유효성을 검사합니다. 하는 경우 *fd* 잘못 된 파일 설명자 인에 설명 된 대로 잘못 된 매개 변수 처리기가 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 함수는 계속 실행 하도록 허용,-1을 반환 하 고 **errno** 로 설정 된 **EBADF**합니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|선택적 헤더|
|-------------|---------------------|---------------------|
|**_close**|\<io.h>|\<errno.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

[_open](open-wopen.md)의 예제를 참조하세요.

## <a name="see-also"></a>참고자료

[하위 수준 I/O](../../c-runtime-library/low-level-i-o.md)<br/>
[_chsize](chsize.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[_dup, _dup2](dup-dup2.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_unlink, _wunlink](unlink-wunlink.md)<br/>
