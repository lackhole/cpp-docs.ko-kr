---
title: _free_locale
ms.date: 11/04/2016
api_name:
- _free_locale
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
- api-ms-win-crt-locale-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- __free_locale
- free_locale
- _free_locale
helpviewer_keywords:
- __free_locale function
- free_locale function
- locales, freeing
- _free_locale function
ms.assetid: 1f08d348-ab32-4028-a145-6cbd51b49af9
ms.openlocfilehash: 31a8e3191c5e370acb00aaf12e21f0c712c51dd1
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70956756"
---
# <a name="_free_locale"></a>_free_locale

로캘 개체를 해제합니다.

## <a name="syntax"></a>구문

```C
void _free_locale(
   _locale_t locale
);
```

### <a name="parameters"></a>매개 변수

*locale*<br/>
해제할 로캘 개체입니다.

## <a name="remarks"></a>설명

**_Free_locale** 함수는 **_get_current_locale** 또는 **_create_locala**호출에서 얻은 로캘 개체를 해제 하는 데 사용 됩니다.

이 함수의 이전 이름인 **__free_locale** (두 개의 선행 밑줄이 있음)은 더 이상 사용 되지 않습니다.

## <a name="requirements"></a>요구 사항

|**일반**|필수 헤더|
|---------------|---------------------|
|**_free_locale**|\<locale.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[_get_current_locale](get-current-locale.md)<br/>
[_create_locale, _wcreate_locale](create-locale-wcreate-locale.md)<br/>
