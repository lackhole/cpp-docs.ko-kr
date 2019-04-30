---
title: _get_FMA3_enable, _set_FMA3_enable
ms.date: 04/05/2018
apiname:
- _get_FMA3_enable
- _set_FMA3_enable
apilocation:
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _get_FMA3_enable
- _set_FMA3_enable
- math/_get_FMA3_enable
- math/_set_FMA3_enable
helpviewer_keywords:
- _get_FMA3_enable
- _set_FMA3_enable
ms.assetid: 4c1dc4bc-e86b-451b-9211-5a2ba6c98ee4
ms.openlocfilehash: 19eabc3b5a11246d5b0056bdafbb169e2a7de9f2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62332197"
---
# <a name="getfma3enable-setfma3enable"></a>_get_FMA3_enable, _set_FMA3_enable

초월수 수학 부동 소수점 라이브러리 함수에서에서 사용 하 여 FMA3 지침 컴파일된 코드 x64를 지정 하는 플래그를 가져오거나 설정 합니다. 플랫폼입니다.

## <a name="syntax"></a>구문

```C
int _set_FMA3_enable(int flag);
int _get_FMA3_enable();
```

### <a name="parameters"></a>매개 변수

*flag*<br/>
X64 초월수 수학 부동 소수점 라이브러리 함수의 FMA3 구현을 사용 하도록 설정 하려면 1로 설정 플랫폼 또는 0으로 FMA3 지침을 사용 하지 않는 구현을 사용 합니다.

## <a name="return-value"></a>반환 값

초월수 수학 부동 소수점 라이브러리 함수의 FMA3 구현을 사용 하는 경우는 0이 아닌 값입니다. 그렇지 않으면 0입니다.

## <a name="remarks"></a>설명

사용 된 **_set_FMA3_enable** 함수를 사용 하는 CRT 라이브러리에서 초월수 수학 부동 소수점 함수에 대 한 fma3 사용 하지 않도록 설정 합니다. 반환 값을 사용 하 여 변경 된 후의 구현은 반영합니다. CPU FMA3 지침을 지원 하지 않는 경우이 함수 라이브러리에서 사용할 수 없습니다 및 반환 값은 0입니다. 사용 하 여 **_get_FMA3_enable** 라이브러리의 현재 상태를 가져옵니다. 기본적으로 x64 CPU FMA3 지침 지원 사용 하도록 설정 또는 라이브러리에서 FMA3 구현을 사용 하지 않도록 설정 하는지 여부를 플랫폼 CRT 시작 코드를 검색 합니다.

FMA3 구현은 서로 다른 알고리즘을 사용 하므로 계산의 결과에서 약간의 차이가 FMA3 구현을 설정 또는 해제, 때나 하거나 FMA3 지원 하지 않는 컴퓨터 간에 관찰 가능 개체를 수 있습니다. 자세한 내용은 [부동 소수점 마이그레이션 문제](../../porting/floating-point-migration-issues.md)합니다.

## <a name="requirements"></a>요구 사항

**_set_FMA3_enable** 하 고 **_get_FMA3_enable** 함수 에서만 사용할 X64 CRT 버전.

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_set_FMA3_enable**, **_get_FMA3_enable**| C: \<math.h><br />C++: \<cmath > 또는 \<math.h >|

합니다 **_set_FMA3_enable** 하 고 **_get_FMA3_enable** 함수는 Microsoft 전용입니다. 호환성에 대한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)<br/>
[부동 소수점 마이그레이션 문제](../../porting/floating-point-migration-issues.md)<br/>
