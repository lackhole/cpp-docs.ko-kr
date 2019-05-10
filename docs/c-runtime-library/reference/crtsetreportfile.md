---
title: _CrtSetReportFile
ms.date: 11/04/2016
apiname:
- _CrtSetReportFile
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
- CrtSetReportFile
- _CrtSetReportFile
helpviewer_keywords:
- CrtSetReportFile function
- _CrtSetReportFile function
ms.assetid: 3126537e-511b-44af-9c1c-0605265eabc4
ms.openlocfilehash: 32a560e09c47468daf48c185e23d6e289c6d1d9b
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64343015"
---
# <a name="crtsetreportfile"></a>_CrtSetReportFile

사용 하 여 [_CrtSetReportMode](crtsetreportmode.md) 지정할 **_CRTDBG_MODE_FILE**, 메시지 텍스트를 수신할 파일 핸들을 지정할 수 있습니다. **_CrtSetReportFile** 에서도 [_CrtDbgReport, _CrtDbgReportW](crtdbgreport-crtdbgreportw.md) 텍스트 (디버그 버전에만 해당)의 대상을 지정할 수 있습니다.

## <a name="syntax"></a>구문

```C
_HFILE _CrtSetReportFile(
   int reportType,
   _HFILE reportFile
);
```

### <a name="parameters"></a>매개 변수

*reportType*<br/>
보고서 형식: **_CRT_WARN**를 **_CRT_ERROR**, 및 **_CRT_ASSERT**합니다.

*reportFile*<br/>
새 보고서 파일에 대 한 *reportType*합니다.

## <a name="return-value"></a>반환 값

성공적으로 완료 되 면 **_CrtSetReportFile** 에 지정 된 보고서 형식에 대해 정의 된 이전 보고서 파일을 반환 합니다 *reportType*합니다. 잘못 된 값이 전달 되 면에 대 한 *reportType*,이 함수에 설명 된 대로 잘못 된 매개 변수 처리기를 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행을 계속 하도록 허용 된 경우 **errno** 로 설정 된 **EINVAL** 고 함수가 반환 **_CRTDBG_HFILE_ERROR**합니다. 자세한 내용은 [errno, _doserrno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.

## <a name="remarks"></a>설명

**_CrtSetReportFile** 사용 되는 [_CrtSetReportMode](crtsetreportmode.md) 에서 생성 된 특정 보고서 형식의 대상을 정의 하는 함수 **_CrtDbgReport**합니다. 때 **_CrtSetReportMode** 할당 호출 되어 합니다 **_CRTDBG_MODE_FILE** 보고 특정 보고서 형식에 대 한 모드 **_CrtSetReportFile** 를 호출한 해야 특정 파일 또는 대상으로 사용 하는 스트림을 정의 합니다. 때 [_DEBUG](../../c-runtime-library/debug.md) 가 정의 되지 않은, 호출 **_CrtSetReportFile** 전처리 중 제거 됩니다.

다음 목록에 대 한 사용 가능한 선택 항목을 보여 줍니다 *reportFile* 의 결과 동작 **_CrtDbgReport**합니다. 이러한 옵션은 Crtdbg.h에서 비트 플래그로 정의되어 있습니다.

- **file handle**

   메시지의 대상이 될 파일에 대한 핸들입니다. 핸들의 유효성이 확인되지는 않습니다. 파일에 대한 핸들을 열고 닫아야 합니다. 예를 들어:

   ```C
   HANDLE hLogFile;
   hLogFile = CreateFile("c:\\log.txt", GENERIC_WRITE,
      FILE_SHARE_WRITE, NULL, CREATE_ALWAYS,
      FILE_ATTRIBUTE_NORMAL, NULL);
   _CrtSetReportMode(_CRT_WARN, _CRTDBG_MODE_FILE);
   _CrtSetReportFile(_CRT_WARN, hLogFile);

   _RPT0(_CRT_WARN,"file message\n");
   CloseHandle(hLogFile);
   ```

- **_CRTDBG_FILE_STDERR**

   메시지를 작성 **stderr**에 다음과 같이 리디렉션될 수 있습니다.

   ```C
   freopen( "c:\\log2.txt", "w", stderr);
   _CrtSetReportMode(_CRT_ERROR, _CRTDBG_MODE_FILE);
   _CrtSetReportFile(_CRT_ERROR, _CRTDBG_FILE_STDERR);

   _RPT0(_CRT_ERROR,"1st message\n");
   ```

- **_CRTDBG_FILE_STDOUT**

   메시지를 작성 **stdout**를 리디렉션할 수 있는 합니다.

- **_CRTDBG_REPORT_FILE**

   현재 보고서 모드를 반환합니다.

각 보고서 형식에 사용되는 보고서 파일을 개별적으로 제어할 수 있습니다. 예를 들어에 지정할 수는 *reportType* 의 **_CRT_ERROR** 에 보고 될 **stderr**, 하는 동안를 *reportType* 의 **_CRT_ASSERT** 사용자 정의 파일 핸들 또는 스트림에 보고 합니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|선택적 헤더|
|-------------|---------------------|---------------------|
|**_CrtSetReportFile**|\<crtdbg.h>|\<errno.h>|

콘솔 유니버설 Windows 플랫폼 (UWP) 앱에서 지원 되지 않습니다. 콘솔을 사용 하 여 연결 된 표준 스트림 핸들 **stdin**하십시오 **stdout**, 및 **stderr**, C 런타임 함수 UWP 앱에서 사용할 수 있는 되기 전에 리디렉션되어야 . 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

**라이브러리:** 디버그 버전 [CRT 라이브러리 기능](../../c-runtime-library/crt-library-features.md) 만 합니다.

## <a name="see-also"></a>참고자료

[디버그 루틴](../../c-runtime-library/debug-routines.md)<br/>
