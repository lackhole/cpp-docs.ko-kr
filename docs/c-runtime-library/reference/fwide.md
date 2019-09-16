---
title: fwide
ms.date: 11/04/2016
api_name:
- fwide
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- fwide
helpviewer_keywords:
- fwide function
ms.assetid: a4641f5b-d74f-4946-95d5-53a64610d28d
ms.openlocfilehash: 2e986ba5ab28072f4933e555eea32a5893c8df56
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70956214"
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
**파일** 구조에 대 한 포인터입니다 (무시 됨).

*mode*<br/>
스트림의 새 너비: 와이드 문자의 경우 양수, 바이트의 경우 음수이며 0은 변경되지 않습니다. 이 값은 무시됩니다.

## <a name="return-value"></a>반환 값

이 함수는 현재 *모드*를 반환 합니다.

## <a name="remarks"></a>설명

이 함수의 현재 버전은 표준에 맞지 않습니다.

## <a name="requirements"></a>요구 사항

|기능|필수 헤더|
|--------------|---------------------|
|**fwide**|\<wchar.h>|

자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.