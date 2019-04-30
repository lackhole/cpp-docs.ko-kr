---
title: getchar, getwchar
ms.date: 11/04/2016
apiname:
- getchar
- getwchar
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
- getwchar
- GetChar
helpviewer_keywords:
- gettchar function
- characters, reading
- getwchar function
- _gettchar function
- standard input, reading from
ms.assetid: 19fda588-3e33-415c-bb60-dd73c028086a
ms.openlocfilehash: 5f8d7dbeb35c8818706eb6070df613df8654feb6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62287243"
---
# <a name="getchar-getwchar"></a>getchar, getwchar

표준 입력에서 문자를 읽습니다.

## <a name="syntax"></a>구문

```C
int getchar();
wint_t getwchar();
```

## <a name="return-value"></a>반환 값

읽은 문자를 반환합니다. 읽기 오류 또는 파일 끝 조건을 나타내기 위해 **getchar** 반환 **EOF**, 및 **getwchar** 반환 **WEOF**합니다. 에 대 한 **getchar**를 사용 하 여 **ferror** 또는 **feof** 오류 또는 파일의 끝을 확인 합니다.

## <a name="remarks"></a>설명

각 루틴에서 단일 문자를 읽습니다 **stdin** 다음 문자를 가리키도록 연결 된 파일 포인터를 증가 시킵니다. **getchar** 같습니다 [_fgetchar](fgetc-fgetwc.md), 함수 및 매크로로 구현 됩니다.

이러한 함수는 호출 스레드를 잠그므로 스레드로부터 안전합니다. 잠기지 않는 버전의 경우 [_getchar_nolock, _getwchar_nolock](getchar-nolock-getwchar-nolock.md)을 참조하세요.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_gettchar**|**getchar**|**getchar**|**getwchar**|

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**getchar**|\<stdio.h>|
|**getwchar**|\<stdio.h> 또는 \<wchar.h>|

콘솔 유니버설 Windows 플랫폼 (UWP) 앱에서 지원 되지 않습니다. 콘솔을 사용 하 여 연결 된 표준 스트림 핸들 **stdin**하십시오 **stdout**, 및 **stderr**, C 런타임 함수 UWP 앱에서 사용할 수 있는 되기 전에 리디렉션되어야 . 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_getchar.c
// Use getchar to read a line from stdin.

#include <stdio.h>

int main()
{
    char buffer[81];
    int i, ch;

    for (i = 0; (i < 80) && ((ch = getchar()) != EOF)
                         && (ch != '\n'); i++)
    {
        buffer[i] = (char) ch;
    }

    // Terminate string with a null character
    buffer[i] = '\0';
    printf( "Input was: %s\n", buffer);
}
```

```Output

This textInput was: This text
```

## <a name="see-also"></a>참고자료

[스트림 I/O](../../c-runtime-library/stream-i-o.md)<br/>
[getc, getwc](getc-getwc.md)<br/>
[fgetc, fgetwc](fgetc-fgetwc.md)<br/>
[_getch, _getwch](getch-getwch.md)<br/>
[putc, putwc](putc-putwc.md)<br/>
[ungetc, ungetwc](ungetc-ungetwc.md)<br/>
