---
title: _CrtSetReportHook
ms.date: 11/04/2016
apiname:
- _CrtSetReportHook
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
- _CrtSetReportHook
- CrtSetReportHook
helpviewer_keywords:
- CrtSetReportHook function
- _CrtSetReportHook function
ms.assetid: 1ae7c64f-8c84-4797-9574-b59f00f7a509
ms.openlocfilehash: 7dcb916ea920751618ffa6a4afbcde8df5e35cba
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64343043"
---
# <a name="crtsetreporthook"></a>_CrtSetReportHook

클라이언트 정의 보고 함수를 C 런타임 디버그 보고 프로세스에 연결함으로써 설치합니다(디버그 버전에만 해당).

## <a name="syntax"></a>구문

```C
_CRT_REPORT_HOOK _CrtSetReportHook(
   _CRT_REPORT_HOOK reportHook
);
```

### <a name="parameters"></a>매개 변수

*reportHook*<br/>
C 런타임 디버그 보고 프로세스에 연결할 새로운 클라이언트 정의 보고 함수입니다.

## <a name="return-value"></a>반환 값

이전 클라이언트 정의 보고 함수를 반환합니다.

## <a name="remarks"></a>설명

**_CrtSetReportHook** 응용 프로그램이 C 런타임 디버그 라이브러리 보고 프로세스에 고유한 보고 함수를 사용할 수 있습니다. 결과적으로 [_CrtDbgReport](crtdbgreport-crtdbgreportw.md)가 호출되어 디버그 보고서를 생성할 때마다 애플리케이션의 보고 함수가 먼저 호출됩니다. 이 기능을 사용 하면 해당 특정 할당 형식에 중점을 두거나 이용할 수 없는 대상에 사용 하 여 보고서를 보낼 수 있도록 디버그 보고서 필터링과 같은 작업을 수행 하는 응용 프로그램 **_CrtDbgReport**합니다. 때 [_DEBUG](../../c-runtime-library/debug.md) 가 정의 되지 않은, 호출 **_CrtSetReportHook** 전처리 중 제거 됩니다.

보다 강력한 버전 **_CrtSetReportHook**를 참조 하십시오 [_CrtSetReportHook2](crtsetreporthook2-crtsetreporthookw2.md)합니다.

합니다 **_CrtSetReportHook** 함수를 설치 새로운 클라이언트 정의 보고 함수에 지정 된 *reportHook* 이전 클라이언트 정의 후크를 반환 합니다. 다음 예제에서는 클라이언트 정의 보고서 후크가 어떻게 프로토타입화되어야 하는지를 보여 줍니다.

```C
int YourReportHook( int reportType, char *message, int *returnValue );
```

여기서 *reportType* 는 디버그 보고서 형식 (**_CRT_WARN**에 **_CRT_ERROR**, 또는 **_CRT_ASSERT**), *메시지* 보고서에 포함할 완전히 어셈블된 디버그 사용자 메시지와 **returnValue** 클라이언트 정의 지정 된 값으로 반환 되어야 하는 함수를 보고 **_ CrtDbgReport**합니다. 사용 가능한 보고서 형식에 대한 자세한 설명은 [_CrtSetReportMode](crtsetreportmode.md) 함수를 참조하세요.

클라이언트 정의 보고 함수는 더 이상 보고 하지 않으려면 필요한 완전히 디버그 메시지를 처리를 하는 경우 함수 반환 해야 **TRUE**합니다. 함수가 반환 하는 경우 **FALSE**하십시오 **_CrtDbgReport** 보고서 형식, 모드 및 파일에 대 한 현재 설정을 사용 하 여 디버그 보고서를 생성 하기 위해 호출 됩니다. 또한 지정 하 여 합니다 **_CrtDbgReport** 에서 값 반환 **returnValue**, 응용 프로그램에서 디버그 중단 발생 하는지 여부를 제어할 수도 있습니다. 디버그 보고서를을 구성 하 고 생성 하는 방법의 설명은 참조 하세요. **_CrtSetReportMode**하십시오 [_CrtSetReportFile](crtsetreportfile.md), 및 **_CrtDbgReport**합니다.

다른 후크 가능 런타임 함수를 사용하고 고유한 클라이언트 정의 후크 함수를 작성하는 방법에 대한 자세한 내용은 [디버그 후크 함수 작성](/visualstudio/debugger/debug-hook-function-writing)을 참조하세요.

> [!NOTE]
> 응용 프로그램을 사용 하 여 컴파일된 경우 **/clr** 보고 함수를 호출 응용 프로그램이 종료 될 때 주, CLR 보고 함수가 CRT 함수를 호출 하는 경우 예외가 throw 됩니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_CrtSetReportHook**|\<crtdbg.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="libraries"></a>라이브러리

[C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)의 디버그 버전만 해당됩니다.

## <a name="see-also"></a>참조

[디버그 루틴](../../c-runtime-library/debug-routines.md)<br/>
[_CrtGetReportHook](crtgetreporthook.md)<br/>
