---
title: _RPT, _RPTF, _RPTW, _RPTFW 매크로
ms.date: 11/04/2016
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
- RPT3
- RPTF4
- _RPT4
- RPT1
- _RPTF0
- RPTF3
- _RPTF4
- RPTF1
- RPT4
- _RPT1
- _RPT0
- RPT0
- _RPTF2
- RPTF0
- _RPT3
- _RPT2
- _RPTF3
- RPT2
- _RPTF1
helpviewer_keywords:
- debugging [CRT], using macros
- _RPTW3 macro
- _RPT0 macro
- RPTW4 macro
- _RPTF3 macro
- _RPTW4 macro
- RPTF4 macro
- RPTFW2 macro
- RPTW macros
- RPT1 macro
- _RPTF macros
- RPTFW3 macro
- _RPTW0 macro
- _RPTF0 macro
- macros, debugging with
- _RPTW2 macro
- RPTF3 macro
- RPT3 macro
- RPT0 macro
- _RPT macros
- RPTW3 macro
- _RPTFW macros
- debug reporting macros
- RPTF macros
- RPT macros
- _RPTW macros
- RPTF2 macro
- _RPTF1 macro
- _RPT1 macro
- _RPT4 macro
- _RPTFW2 macro
- _RPTFW1 macro
- RPTF0 macro
- _RPT2 macro
- RPTFW macros
- _RPTW1 macro
- _RPTFW0 macro
- RPT4 macro
- _RPT3 macro
- _RPTFW3 macro
- _RPTF4 macro
- _RPTFW4 macro
- _RPTF2 macro
- RPTW0 macro
- RPTFW4 macro
- RPTFW0 macro
- RPTW2 macro
- RPTF1 macro
- RPT2 macro
- RPTFW1 macro
- RPTW1 macro
ms.assetid: a5bf8b30-57f7-4971-8030-e773b7a1ae13
ms.openlocfilehash: 61748cca2cdfcc2d72b6943bfeedd9597009e20b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62357508"
---
# <a name="rpt-rptf-rptw-rptfw-macros"></a>_RPT, _RPTF, _RPTW, _RPTFW 매크로

디버그 보고서를 생성하여 애플리케이션의 진행률을 추적합니다(디버그 버전에만 해당함). 사실은 *n* 의 인수 개수를 지정 *args* 및 0, 1, 2, 3, 4 또는 5 일 수 있습니다.

## <a name="syntax"></a>구문

```C
_RPT
      n
      (
   reportType,
   format,
...[args]
);
_RPTFn(
   reportType,
   format,
   [args]
);
_RPTWn(
   reportType,
   format
   [args]
);
_RPTFWn(
   reportType,
   format
   [args]
);
```

### <a name="parameters"></a>매개 변수

*reportType*<br/>
보고서 종류: **_CRT_WARN**하십시오 **_CRT_ERROR**, 또는 **_CRT_ASSERT**합니다.

*format*<br/>
사용자 메시지를 만드는 데 사용되는 형식 제어 문자열입니다.

*args*<br/>
사용 되는 대체 인수 *형식*합니다.

## <a name="remarks"></a>설명

이러한 모든 매크로 *reportType* 하 고 *형식* 매개 변수입니다. 또한 매크로 이름에 추가된 번호로 표시되는 추가 인수도 4개까지 사용할 수 있습니다. 예를 들어 **_RPT0** 하 고 **_RPTF0** 추가 인수를 취하지 **_RPT1** 고 **_RPTF1** 걸릴 *arg1*, **_RPT2** 하 고 **_RPTF2** 걸릴 *arg1* 및 **arg2**등입니다.

**_RPT** 및 **_RPTF** 매크로 비슷합니다는 [printf](printf-printf-l-wprintf-wprintf-l.md) 진행률을 추적 하는 응용 프로그램의 디버깅 프로세스 동안 사용할 수 있기 때문에 작동 합니다. 그러나 이러한 매크로 보다 유연한 **printf** 묶이 필요가 없습니다 때문에 **#ifdef** 없도록 않으려면 문을 응용 프로그램의 정품 빌드 시에서 호출 합니다. 이러한 유연성을 사용 하 여 이루어집니다 합니다 [_DEBUG](../../c-runtime-library/debug.md) 매크로, **_RPT** 및 **_RPTF** 매크로 하면 볼 수 있습니다 합니다 **_DEBUG** 플래그는 정의 합니다. 때 **_DEBUG** 가 정의 되지 않은 이러한 매크로 호출이 전처리 중 제거 됩니다.

합니다 **_RPTW** 하 고 **_RPTFW** 매크로 이러한 매크로의 와이드 문자 버전입니다. 이들은 아마도 **wprintf** 및 와이드 문자 문자열을 인수로 사용 합니다.

합니다 **_RPT** 매크로 호출을 [_CrtDbgReport](crtdbgreport-crtdbgreportw.md) 사용자 메시지를 사용 하 여 디버그 보고서를 생성 하는 함수입니다. 합니다 **_RPTW** 매크로 호출을 **_CrtDbgReportW** 와이드 문자를 사용 하 여 동일한 보고서를 생성 하는 함수입니다. 합니다 **_RPTF** 하 고 **_RPTFW** 매크로 보고서 매크로가 호출 또한 사용자 메시지를 소스 파일 및 줄 번호를 사용 하 여 디버그 보고서를 만듭니다. 대체 하 여 사용자 메시지를 작성 합니다 **arg**[*n*] 인수를를 *형식* 문자열를 정의한 동일한 규칙을 사용 하는 [printf](printf-printf-l-wprintf-wprintf-l.md)함수입니다.

**_CrtDbgReport** 나 **_CrtDbgReportW** 디버그 보고서를 생성 하 고 현재 보고서 모드에 따라 대상 및 파일에 대해 정의 된 해당 결정 *reportType*합니다. [_CrtSetReportMode](crtsetreportmode.md) 및 [_CrtSetReportFile](crtsetreportfile.md) 함수는 각 보고서 종류의 대상을 정의하는 데 사용됩니다.

경우는 **_RPT** 매크로가 호출 모두 **_CrtSetReportMode** 나 **_CrtSetReportFile** 되었습니다 호출 메시지가 다음과 같이 표시 됩니다.

|보고서 종류|출력 대상|
|-----------------|------------------------|
|**_CRT_WARN**|경고 텍스트가 표시되지 않습니다.|
|**_CRT_ERROR**|팝업 창이 표시됩니다. `_CrtSetReportMode(_CRT_ERROR, _CRTDBG_MODE_WNDW);`를 지정한 경우와 동일합니다.|
|**_CRT_ASSERT**|동일 **_CRT_ERROR**합니다.|

경우 대상이 디버그 메시지 창이 고 사용자가 선택는 **을 다시 시도 하세요** 단추를 **_CrtDbgReport** 또는 **_CrtDbgReportW** 하려면 이러한 매크로 유발 하는 1을 반환 합니다 디버거는 적시에 (JIT) 디버깅을 사용 합니다. 이들 매크로를 디버깅 오류 처리 메커니즘으로 사용하는 방법에 대한 자세한 내용은 [확인 및 보고에 매크로 사용](/visualstudio/debugger/macros-for-reporting)을 참조하세요.

디버그 보고서를 생성하는 두 가지 다른 매크로가 있습니다. [_ASSERT](assert-asserte-assert-expr-macros.md) 매크로는 해당 식 인수가 FALSE인 경우에 한해 보고서를 생성합니다. [_ASSERTE](assert-asserte-assert-expr-macros.md) 는 정확 하 게 like **_ASSERT**, 생성된 된 보고서에 실패 한 식을 포함 합니다.

## <a name="requirements"></a>요구 사항

|매크로|필수 헤더|
|-----------|---------------------|
|**_RPT** macros|\<crtdbg.h>|
|**_RPTF** macros|\<crtdbg.h>|
|**_RPTW** 매크로|\<crtdbg.h>|
|**_RPTFW** 매크로|\<crtdbg.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="libraries"></a>라이브러리

[C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)의 디버그 버전만 해당됩니다.

이러한 항목은 매크로이며 Crtdbg.h를 포함하면 가져올 수 있지만, 이러한 매크로는 다른 런타임 함수를 호출하므로 애플리케이션을 디버그 라이브러리 중 하나와 연결해야 합니다.

## <a name="example"></a>예제

[_ASSERT](assert-asserte-assert-expr-macros.md) 항목의 예제를 참조하세요.

## <a name="see-also"></a>참고자료

[디버그 루틴](../../c-runtime-library/debug-routines.md)<br/>
