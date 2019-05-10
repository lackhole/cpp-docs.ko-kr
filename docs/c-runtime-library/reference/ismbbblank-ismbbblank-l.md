---
title: _ismbbblank, _ismbbblank_l
ms.date: 11/04/2016
apiname:
- _ismbbblank_l
- _ismbbblank
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
- api-ms-win-crt-multibyte-l1-1-0.dll
apitype: DLLExport
ms.assetid: d21b2e41-7206-41f5-85bb-9c9ab4f3e21b
ms.openlocfilehash: c6709d5a5870c44d200b704e4a34043ff9c37226
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62286951"
---
# <a name="ismbbblank-ismbbblankl"></a>_ismbbblank, _ismbbblank_l

지정된 멀티바이트 문자가 공백 문자인지 여부를 확인합니다.

> [!IMPORTANT]
> 이 API는 Windows 런타임에서 실행되는 애플리케이션에서 사용할 수 없습니다. 자세한 내용은 [유니버설 Windows 플랫폼 앱에서 지원되지 않는 CRT 함수](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
int _ismbbblank(
   unsigned int c
);
int _ismbbblank_l(
   unsigned int c,
   _locale_t locale
);
```

### <a name="parameters"></a>매개 변수

*c*<br/>
테스트할 정수입니다.

*locale*<br/>
사용할 로캘입니다.

## <a name="return-value"></a>반환 값

**_ismbbblank** 이면 0이 아닌 값을 반환 *c* (0x20) 공백 문자, 가로 탭 (0x09) 문자인 또는 어떤 에대한텍스트줄내에서단어를구분하는데사용되는로캘별문자를나타내는**isspace** true, 그렇지 않으면 0을 반환 합니다. **_ismbbblank** 모든 로캘 종속 동작에 현재 로캘을 사용 합니다. **_ismbbblank_l** 전달 된 로캘을 대신 사용 한다는 점을 제외 하 고는 동일 합니다. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_ismbbblank**|\<mbctype.h>|
|**_ismbbblank_l**|\<mbctype.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[바이트 분류](../../c-runtime-library/byte-classification.md)<br/>
[_ismbb 루틴](../../c-runtime-library/ismbb-routines.md)<br/>
