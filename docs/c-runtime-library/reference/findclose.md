---
title: _findclose
ms.date: 11/04/2016
apiname:
- _findclose
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
- api-ms-win-crt-filesystem-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _findclose
- findclose
helpviewer_keywords:
- _findclose function
- findclose function
ms.assetid: 9216c573-0878-444c-b5d7-cdaf16fb9163
ms.openlocfilehash: 29010f8a502d463eeb6ca98837a1b7dae9f5ae6b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62333757"
---
# <a name="findclose"></a>_findclose

지정된 검색 핸들을 닫고 연결된 리소스를 해제합니다.

## <a name="syntax"></a>구문

```C
int _findclose(
   intptr_t handle
);
```

### <a name="parameters"></a>매개 변수

*handle*<br/>
에 대 한 이전 호출에서 반환 된 검색 핸들 **_findfirst**합니다.

## <a name="return-value"></a>반환 값

성공 하면 **_findclose** 0을 반환 합니다. 그렇지 않으면-1을 반환 합니다 설정 **errno** 하 **ENOENT**를 나타내는 더 이상 일치 하는 파일을 찾을 수 없습니다.

## <a name="requirements"></a>요구 사항

|기능|필수 헤더|
|--------------|---------------------|
|**_findclose**|\<io.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[시스템 호출](../../c-runtime-library/system-calls.md)<br/>
[파일 이름 검색 함수](../../c-runtime-library/filename-search-functions.md)<br/>
