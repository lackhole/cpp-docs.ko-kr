---
title: _ismbbalnum, _ismbbalnum_l
ms.date: 11/04/2016
api_name:
- _ismbbalnum
- _ismbbalnum_l
api_location:
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _ismbbalnum
- ismbbalnum
- _ismbbalnum_l
- ismbbalnum_l
helpviewer_keywords:
- _ismbbalnum_l function
- ismbbalnum function
- ismbbalnum_l function
- _ismbbalnum function
ms.assetid: 8025de50-a871-49fd-9ae6-f437b47aa987
ms.openlocfilehash: d817ea6875149f9342854b0c22b27b0c93d29636
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70954292"
---
# <a name="_ismbbalnum-_ismbbalnum_l"></a>_ismbbalnum, _ismbbalnum_l

지정된 멀티바이트 문자가 영문자인지 숫자인지를 확인합니다.

## <a name="syntax"></a>구문

```C
int _ismbbalnum(
   unsigned int c
);
int _ismbbalnum_l(
   unsigned int c
);
```

### <a name="parameters"></a>매개 변수

*c*<br/>
테스트할 정수입니다.

*locale*<br/>
사용할 로캘입니다.

## <a name="return-value"></a>반환 값

**_ismbbalnum** 는 식이 다음과 같이 0이 아닌 값을 반환 합니다.

`isalnum(c) || _ismbbkalnum(c)`

*c*의 경우 0이 아니고, 그렇지 않으면 0입니다.

**_L** 접미사가 있는이 함수의 버전은 로캘 종속 동작에 현재 로캘 대신 전달 된 로캘을 사용 한다는 점을 제외 하 고는 동일 합니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_ismbbalnum**|\<mbctype.h>|
|**_ismbbalnum_l**|\<mbctype.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="libraries"></a>라이브러리

모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.

## <a name="see-also"></a>참고자료

[바이트 분류](../../c-runtime-library/byte-classification.md)<br/>
[_ismbb 루틴](../../c-runtime-library/ismbb-routines.md)<br/>
