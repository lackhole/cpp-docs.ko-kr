---
title: fwide
ms.date: 11/04/2016
apiname:
- fwide
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
apitype: DLLExport
f1_keywords:
- fwide
helpviewer_keywords:
- fwide function
ms.assetid: a4641f5b-d74f-4946-95d5-53a64610d28d
ms.openlocfilehash: d992ebc527744beeb4ef14175e3f10646a77a064
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62287618"
---
# <a name="fwide"></a>fwide

구현되지 않았습니다.

## <a name="syntax"></a>구문

```C
int fwide(
   FILE *stream,
   int mode;
);
```

### <a name="parameters"></a>매개 변수

*stream*<br/>
에 대 한 포인터 **파일** 구조 (무시 됨).

*모드*<br/>
스트림의 새 너비: 와이드 문자의 경우 양수, 바이트의 경우 음수이며 0은 변경되지 않습니다. 이 값은 무시됩니다.

## <a name="return-value"></a>반환 값

이 함수는 현재는 그냥 반환 *모드*합니다.

## <a name="remarks"></a>설명

이 함수의 현재 버전은 표준에 맞지 않습니다.

## <a name="requirements"></a>요구 사항

|기능|필수 헤더|
|--------------|---------------------|
|**fwide**|\<wchar.h>|

자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.