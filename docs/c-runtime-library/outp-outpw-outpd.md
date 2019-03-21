---
title: _outp, _outpw, _outpd
ms.date: 11/04/2016
apiname:
- _outpd
- _outp
- _outpw
apilocation:
- msvcrt.dll
- msvcr100.dll
- msvcr120.dll
- msvcr90.dll
- msvcr110_clr0400.dll
- msvcr110.dll
- msvcr80.dll
apitype: DLLExport
f1_keywords:
- _outpw
- _outpd
- _outp
- outpd
helpviewer_keywords:
- outpw function
- words
- _outpd function
- outpd function
- outp function
- ports, writing bytes at
- bytes, writing to ports
- words, writing to ports
- double words
- double words, writing to ports
- _outpw function
- _outp function
ms.assetid: c200fe22-41f6-46fd-b0be-ebb805b35181
ms.openlocfilehash: 1a507f4115a48372706590eb61f9e3e77a0e3548
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57752066"
---
# <a name="outp-outpw-outpd"></a>_outp, _outpw, _outpd

포트에서 바이트(`_outp`), 워드(`_outpw`) 또는 2배 워드(`_outpd`)를 출력합니다.

> [!IMPORTANT]
>  이러한 함수는 사용되지 않습니다. Visual Studio 2015부터 CRT에서 사용할 수 없습니다.

> [!IMPORTANT]
>  이 API는 Windows 런타임에서 실행되는 애플리케이션에서 사용할 수 없습니다. 자세한 내용은 [유니버설 Windows 플랫폼 앱에서 지원되지 않는 CRT 함수](../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)를 참조하세요.

## <a name="syntax"></a>구문

```

      int _outp(
unsigned short port,
int databyte
);
unsigned short _outpw(
unsigned short port,
unsigned short dataword
);
unsigned long _outpd(
unsigned short port,
unsigned long dataword
);
```

#### <a name="parameters"></a>매개 변수
*port*<br/>
포트 번호입니다.

*databyte, dataword*<br/>
출력 값입니다.

## <a name="return-value"></a>반환 값

함수는 데이터 출력을 반환합니다. 반환되는 오류가 없습니다.

## <a name="remarks"></a>주의

`_outp`, `_outpw`및 `_outpd` 함수는 바이트, 워드 및 2배 워드를 각각 지정된 출력 포트에 씁니다. *port* 인수는 0-65,535 범위에 속한 임의의 부호 없는 정수일 수 있고 *databyte*는 0–255 범위에 속한 임의의 정수일 수 있으며 *dataword*는 각각 정수, 부호 없는 정수(Short) 및 부호 없는 정수(Long) 범위에 속한 임의의 값일 수 있습니다.

이러한 함수는 I/O 포트에 직접 쓰기 때문에 사용자 코드에서 사용할 수 없습니다. 이러한 운영 체제에서 I/O 포트를 사용하는 방법에 대한 자세한 내용을 보려면 MSDN에서 "Win32의 직렬 통신"을 검색하십시오.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|`_outp`|\<conio.h>|
|`_outpw`|\<conio.h>|
|`_outpd`|\<conio.h>|

호환성에 대한 자세한 내용은 [호환성](../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="libraries"></a>라이브러리

모든 버전의 [C 런타임 라이브러리](../c-runtime-library/crt-library-features.md)입니다.

## <a name="see-also"></a>참고 항목

[콘솔 및 포트 I/O](../c-runtime-library/console-and-port-i-o.md)<br/>
[_inp, _inpw, _inpd](../c-runtime-library/inp-inpw-inpd.md)
