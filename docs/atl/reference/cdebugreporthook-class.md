---
title: CDebugReportHook 클래스
ms.date: 11/04/2016
f1_keywords:
- CDebugReportHook
- ATLUTIL/ATL::CDebugReportHook
- ATLUTIL/ATL::CDebugReportHook::CDebugReportHook
- ATLUTIL/ATL::CDebugReportHook::CDebugReportHookProc
- ATLUTIL/ATL::CDebugReportHook::RemoveHook
- ATLUTIL/ATL::CDebugReportHook::SetHook
- ATLUTIL/ATL::CDebugReportHook::SetPipeName
- ATLUTIL/ATL::CDebugReportHook::SetTimeout
helpviewer_keywords:
- CDebugReportHook class
ms.assetid: 798076c3-6e63-4286-83b8-aa1bbcd0c20c
ms.openlocfilehash: a7c5993d1b96daaa73e7fc9509c93e66daed77f3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62245929"
---
# <a name="cdebugreporthook-class"></a>CDebugReportHook 클래스

이 클래스를 사용 하 여 명명 된 파이프 디버그 보고서를 보내도록 합니다.

## <a name="syntax"></a>구문

```
class CDebugReportHook
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CDebugReportHook::CDebugReportHook](#cdebugreporthook)|호출 [SetPipeName](#setpipename)하십시오 [SetTimeout](#settimeout), 및 [SetHook](#sethook)합니다.|
|[CDebugReportHook::~CDebugReportHook](#dtor)|Calls [CDebugReportHook::RemoveHook](#removehook).|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CDebugReportHook::CDebugReportHookProc](#cdebugreporthookproc)|(정적) C 런타임 디버그 보고 프로세스에 연결 되는 사용자 지정 보고 함수입니다.|
|[CDebugReportHook::RemoveHook](#removehook)|명명된 된 파이프에 디버그 보고서를 보내는 중지 하려면이 메서드를 호출 하 고 이전 보고서 후크를 복원 합니다.|
|[CDebugReportHook::SetHook](#sethook)|명명된 된 파이프에 디버그 보고서를 보내려면이 메서드를 호출 합니다.|
|[CDebugReportHook::SetPipeName](#setpipename)|디버그 보고서를 전송 하는 파이프의 이름 확인 하 고 컴퓨터를 설정 하려면이 메서드를 호출 합니다.|
|[CDebugReportHook::SetTimeout](#settimeout)|이 클래스를 사용할 수 있이 명명된 된 파이프에 대 한 대기 함을 밀리초 단위로 시간을 설정 하려면이 메서드를 호출 합니다.|

## <a name="remarks"></a>설명

서비스 또는 명명 된 파이프 디버그 보고서를 보내도록 응용 프로그램의 디버그 빌드에서이 클래스의 인스턴스를 만듭니다. 디버그 보고서를 호출 하 여 생성 됩니다 [_CrtDbgReport](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md) 또는 같은이 함수에 대 한 래퍼를 사용 하는 [ATLTRACE](debugging-and-error-reporting-macros.md#atltrace) 하 고 [ATLASSERT](debugging-and-error-reporting-macros.md#atlassert) 매크로입니다.

이 클래스의 사용을 사용 하면 대화형으로 비 대화형 데스크톱에서 실행 하는 구성 요소를 디버깅할 수 있습니다 [윈도우 스테이션](/windows/desktop/winstation/window-stations)합니다.

Note 스레드의 기본 보안 컨텍스트를 사용 하 여 디버그 보고서 전송 됩니다. 여기서 가장 낮은 권한의 사용자 수행 되 같은 웹 응용 프로그램의 경우에서 디버그 보고서를 볼 수 있도록 가장이 일시적으로 해제 됩니다.

## <a name="requirements"></a>요구 사항

**헤더:** 와 atlutil.h

##  <a name="cdebugreporthook"></a>  CDebugReportHook::CDebugReportHook

호출 [SetPipeName](#setpipename)하십시오 [SetTimeout](#settimeout), 및 [SetHook](#sethook)합니다.

```
CDebugReportHook(
    LPCSTR szMachineName = ".",
    LPCSTR szPipeName = "AtlsDbgPipe",
    DWORD dwTimeout = 20000) throw();
```

### <a name="parameters"></a>매개 변수

*szMachineName*<br/>
디버그 출력을 전송 해야 하는 컴퓨터의 이름입니다. 기본값은 로컬 컴퓨터입니다.

*szPipeName*<br/>
디버그 출력을 전송 해야 하는 명명된 된 파이프의 이름입니다.

*dwTimeout*<br/>
이 클래스는 명명된 된 파이프를 사용할 수 있을 대기할 시간 (밀리초) 시간입니다.

##  <a name="dtor"></a>  CDebugReportHook::~CDebugReportHook

Calls [CDebugReportHook::RemoveHook](#removehook).

```
~CDebugReportHook() throw();
```

##  <a name="cdebugreporthookproc"></a>  CDebugReportHook::CDebugReportHookProc

C 런타임 디버그 보고 프로세스에 연결 되는 사용자 지정 보고 함수입니다.

```
static int __cdecl CDebugReportHookProc(
    int reportType,
    char* message,
    int* returnValue) throw();
```

### <a name="parameters"></a>매개 변수

*reportType*<br/>
(_CRT_WARN, _CRT_ERROR, 또는 _CRT_ASSERT) 보고서의 형식입니다.

*message*<br/>
메시지 문자열입니다.

*returnValue*<br/>
반환 되어야 하는 값 [_CrtDbgReport](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md)합니다.

### <a name="return-value"></a>반환 값

더 이상 보고할 없습니다 있도록 후크 해당 메시지를 완전히 처리 하는 경우 FALSE를 반환 합니다. TRUE를 반환 합니다 `_CrtDbgReport` 일반적인 방법으로 메시지를 보고 해야 합니다.

### <a name="remarks"></a>설명

보고 함수를 명명된 된 파이프를 열고 다른 끝에 있는 프로세스와 통신 하려고 합니다. 파이프 사용량이 많을 경우 보고 함수는 파이프 무료 되거나 제한 시간이 만료 될 때까지 기다릴 수 있습니다. 생성자 또는 호출 하 여 제한 시간을 설정할 수 있습니다 [CDebugReportHook::SetTimeout](#settimeout)합니다.

이 함수에서 코드 호출 스레드의 기본 보안 컨텍스트에서 실행 되 고,이 함수의 지속 시간에 대 한 가장을 사용할 수 없습니다, 합니다.

##  <a name="removehook"></a>  CDebugReportHook::RemoveHook

명명된 된 파이프에 디버그 보고서를 보내는 중지 하려면이 메서드를 호출 하 고 이전 보고서 후크를 복원 합니다.

```
void RemoveHook() throw();
```

### <a name="remarks"></a>설명

호출 [_CrtSetReportHook2](../../c-runtime-library/reference/crtsetreporthook2-crtsetreporthookw2.md) 이전 보고서 후크를 복원 합니다.

##  <a name="sethook"></a>  CDebugReportHook::SetHook

명명된 된 파이프에 디버그 보고서를 보내려면이 메서드를 호출 합니다.

```
void SetHook() throw();
```

### <a name="remarks"></a>설명

호출 [_CrtSetReportHook2](../../c-runtime-library/reference/crtsetreporthook2-crtsetreporthookw2.md) 라우팅된 디버그 보고서를 할 [CDebugReportHookProc](#cdebugreporthookproc) 명명된 된 파이프에 있습니다. 이 클래스는 추적 이전 보고서 후크 될 수 있도록 복원 될 때 [RemoveHook](#removehook) 라고 합니다.

##  <a name="setpipename"></a>  CDebugReportHook::SetPipeName

디버그 보고서를 전송 하는 파이프의 이름 확인 하 고 컴퓨터를 설정 하려면이 메서드를 호출 합니다.

```
BOOL SetPipeName(
    LPCSTR szMachineName = ".",
    LPCSTR szPipeName = "AtlsDbgPipe") throw();
```

### <a name="parameters"></a>매개 변수

*szMachineName*<br/>
디버그 출력을 전송 해야 하는 컴퓨터의 이름입니다.

*szPipeName*<br/>
디버그 출력을 전송 해야 하는 명명된 된 파이프의 이름입니다.

### <a name="return-value"></a>반환 값

성공 하면 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.

##  <a name="settimeout"></a>  CDebugReportHook::SetTimeout

이 클래스를 사용할 수 있이 명명된 된 파이프에 대 한 대기 함을 밀리초 단위로 시간을 설정 하려면이 메서드를 호출 합니다.

```
void SetTimeout(DWORD dwTimeout);
```

### <a name="parameters"></a>매개 변수

*dwTimeout*<br/>
이 클래스는 명명된 된 파이프를 사용할 수 있을 대기할 시간 (밀리초) 시간입니다.

## <a name="see-also"></a>참고자료

[클래스](../../atl/reference/atl-classes.md)
