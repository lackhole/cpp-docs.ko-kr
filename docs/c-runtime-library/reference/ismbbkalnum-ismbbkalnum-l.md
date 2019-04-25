---
title: _ismbbkalnum, _ismbbkalnum_l
ms.date: 11/04/2016
apiname:
- _ismbbkalnum
- _ismbbkalnum_l
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
f1_keywords:
- _ismbbkalnum
- ismbbkalnum
- ismbbkalnum_l
- _ismbbkalnum_l
helpviewer_keywords:
- _ismbbkalnum_l function
- ismbbkalnum_l function
- _ismbbkalnum function
- ismbbkalnum function
ms.assetid: e1d70e7b-29d0-469c-9d93-442b99de22ac
ms.openlocfilehash: 4eca5738068dab7393f70edf619629b179637e73
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62158009"
---
# <a name="ismbbkalnum-ismbbkalnuml"></a>_ismbbkalnum, _ismbbkalnum_l

특정 멀티바이트 문자가 ASCII가 아닌 텍스트 기호인지 여부를 결정합니다.

## <a name="syntax"></a>구문

```C
int _ismbbkalnum(
   unsigned int c
);
int _ismbbkalnum_l(
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

**_ismbbkalnum** 이면 0이 아닌 값을 반환 정수 *c* 0 또는 문장 부호 이외의 ASCII가 아닌 텍스트 기호 이면 아닙니다. **_ismbbkalnum** 로캘 종속 문자 정보에 대 한 현재 로캘을 사용 합니다. **_ismbbkalnum_l** 동일 **_ismbbkalnum** 는 로캘을 매개 변수로 사용 한다는 점을 제외 하 고 있습니다. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_ismbbkalnum**|\<mbctype.h>|
|**_ismbbkalnum_l**|\<mbctype.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[바이트 분류](../../c-runtime-library/byte-classification.md)<br/>
[_ismbb 루틴](../../c-runtime-library/ismbb-routines.md)<br/>
