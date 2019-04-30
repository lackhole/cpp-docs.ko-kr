---
title: CCommandLineInfo 클래스
ms.date: 11/04/2016
f1_keywords:
- CCommandLineInfo
- AFXWIN/CCommandLineInfo
- AFXWIN/CCommandLineInfo::CCommandLineInfo
- AFXWIN/CCommandLineInfo::ParseParam
- AFXWIN/CCommandLineInfo::m_bRunAutomated
- AFXWIN/CCommandLineInfo::m_bRunEmbedded
- AFXWIN/CCommandLineInfo::m_bShowSplash
- AFXWIN/CCommandLineInfo::m_nShellCommand
- AFXWIN/CCommandLineInfo::m_strDriverName
- AFXWIN/CCommandLineInfo::m_strFileName
- AFXWIN/CCommandLineInfo::m_strPortName
- AFXWIN/CCommandLineInfo::m_strPrinterName
- AFXWIN/CCommandLineInfo::m_strRestartIdentifier
helpviewer_keywords:
- CCommandLineInfo [MFC], CCommandLineInfo
- CCommandLineInfo [MFC], ParseParam
- CCommandLineInfo [MFC], m_bRunAutomated
- CCommandLineInfo [MFC], m_bRunEmbedded
- CCommandLineInfo [MFC], m_bShowSplash
- CCommandLineInfo [MFC], m_nShellCommand
- CCommandLineInfo [MFC], m_strDriverName
- CCommandLineInfo [MFC], m_strFileName
- CCommandLineInfo [MFC], m_strPortName
- CCommandLineInfo [MFC], m_strPrinterName
- CCommandLineInfo [MFC], m_strRestartIdentifier
ms.assetid: 3e313ddb-0a82-4991-87ac-a27feff4668c
ms.openlocfilehash: 6e4b535da00fdcecf4ce52fad696cb5d2bc55efa
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62408149"
---
# <a name="ccommandlineinfo-class"></a>CCommandLineInfo 클래스

애플리케이션을 시작할 때 명령줄을 구문 분석하는 데 유용합니다.

## <a name="syntax"></a>구문

```
class CCommandLineInfo : public CObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CCommandLineInfo::CCommandLineInfo](#ccommandlineinfo)|기본값 생성 `CCommandLineInfo` 개체입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CCommandLineInfo::ParseParam](#parseparam)|이 콜백은 개별 매개 변수를 구문 분석을 재정의 합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CCommandLineInfo::m_bRunAutomated](#m_brunautomated)|명령줄 나타냅니다 `/Automation` 옵션이 발견 되었습니다.|
|[CCommandLineInfo::m_bRunEmbedded](#m_brunembedded)|명령줄 나타냅니다 `/Embedding` 옵션이 발견 되었습니다.|
|[CCommandLineInfo::m_bShowSplash](#m_bshowsplash)|시작 화면을 표시 해야 하는 경우를 나타냅니다.|
|[CCommandLineInfo::m_nShellCommand](#m_nshellcommand)|셸 명령 처리를 나타냅니다.|
|[CCommandLineInfo::m_strDriverName](#m_strdrivername)|드라이버를 나타내는 이름 지정 인 경우 셸 명령을 인쇄 합니다. 그렇지 않은 경우 비어 있습니다.|
|[CCommandLineInfo::m_strFileName](#m_strfilename)|열거나; 출력 파일 이름을 나타냅니다. 빈 경우 신규 또는 DDE 셸 명령입니다.|
|[CCommandLineInfo::m_strPortName](#m_strportname)|포트를 나타내는 이름 지정 인 경우 셸 명령을 인쇄 합니다. 그렇지 않은 경우 비어 있습니다.|
|[CCommandLineInfo::m_strPrinterName](#m_strprintername)|프린터를 나타내는 이름 지정 인 경우 셸 명령을 인쇄 합니다. 그렇지 않은 경우 비어 있습니다.|
|[CCommandLineInfo::m_strRestartIdentifier](#m_strrestartidentifier)|다시 시작 관리자 응용 프로그램을 다시 시작 하는 경우 다시 시작 관리자에 대 한 다시 시작 고유 식별자를 나타냅니다.|

## <a name="remarks"></a>설명

MFC 응용 프로그램에서이 클래스의 로컬 인스턴스를 만듭니다 일반적으로 [InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) 해당 응용 프로그램 개체의 기능입니다. 이 개체가 전달 됩니다 [CWinApp::ParseCommandLine](../../mfc/reference/cwinapp-class.md#parsecommandline)를 반복적으로 호출 [ParseParam](#parseparam) 맞게는 `CCommandLineInfo` 개체입니다. 합니다 `CCommandLineInfo` 개체가 전달 됩니다 [CWinApp::ProcessShellCommand](../../mfc/reference/cwinapp-class.md#processshellcommand) 플래그 및 명령줄 인수를 처리 합니다.

다음 명령줄 옵션 및 매개 변수를 캡슐화 할이 개체를 사용할 수 있습니다.

|명령줄 인수|명령 실행|
|----------------------------|----------------------|
|*app*|새 파일입니다.|
|*app* filename|파일을 엽니다.|
|*app* `/p` filename|파일이 기본 프린터로 인쇄 됩니다.|
|*앱* `/pt` filename 프린터 드라이버 포트|파일을 지정 된 프린터로 인쇄 합니다.|
|*app* `/dde`|시작 되 고 await DDE 명령입니다.|
|*app* `/Automation`|OLE 자동화 서버를 시작 합니다.|
|*app* `/Embedding`|포함된 OLE 항목 편집을 시작 합니다.|
|*app* `/Register`<br /><br /> *app* `/Regserver`|모든 등록 작업을 수행 하는 응용 프로그램을 알립니다.|
|*app* `/Unregister`<br /><br /> *app* `/Unregserver`|등록 취소 작업을 수행 하려면 응용 프로그램을 알립니다.|

새 클래스를 파생 `CCommandLineInfo` 다른 플래그와 매개 변수 값을 처리 하도록 합니다. 재정의 [ParseParam](#parseparam) 새 플래그를 처리할 수 있습니다.

## <a name="inheritance-hierarchy"></a>상속 계층

[CObject](../../mfc/reference/cobject-class.md)

`CCommandLineInfo`

## <a name="requirements"></a>요구 사항

**헤더:** afxwin.h

##  <a name="ccommandlineinfo"></a>  CCommandLineInfo::CCommandLineInfo

이 생성자는 `CCommandLineInfo` 기본값을 사용 하 여 개체입니다.

```
CCommandLineInfo();
```

### <a name="remarks"></a>설명

기본값은 시작 화면을 표시 하도록 ( `m_bShowSplash=TRUE`) 파일 메뉴에서 새 명령을 실행 하 고 ( `m_nShellCommand` **NewFile =**).

응용 프로그램 프레임 워크 호출 [ParseParam](#parseparam) 이 개체의 데이터 멤버에 맞게 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#54](../../mfc/codesnippet/cpp/ccommandlineinfo-class_1.cpp)]

##  <a name="m_brunautomated"></a>  CCommandLineInfo::m_bRunAutomated

나타내는 `/Automation` 플래그 명령줄에서 찾을 수 있습니다.

```
BOOL m_bRunAutomated;
```

### <a name="remarks"></a>설명

True 인 경우,이 OLE 자동화 서버 시작을 의미 합니다.

##  <a name="m_brunembedded"></a>  CCommandLineInfo::m_bRunEmbedded

나타내는 `/Embedding` 플래그 명령줄에서 찾을 수 있습니다.

```
BOOL m_bRunEmbedded;
```

### <a name="remarks"></a>설명

True 인 경우,이 포함 된 OLE 항목을 편집 하는 것에 대 한 시작을 의미 합니다.

##  <a name="m_bshowsplash"></a>  CCommandLineInfo::m_bShowSplash

시작 화면을 표시 해야 함을 나타냅니다.

```
BOOL m_bShowSplash;
```

### <a name="remarks"></a>설명

TRUE 이면 즉, 시작 하는 동안이 응용 프로그램에 대 한 시작 화면을 표시 합니다. 기본 구현의 [ParseParam](#parseparam) 경우 TRUE로 설정 하는이 데이터 멤버 [m_nShellCommand](#m_nshellcommand) 값과 같음 `CCommandLineInfo::FileNew`합니다.

##  <a name="m_nshellcommand"></a>  CCommandLineInfo::m_nShellCommand

응용 프로그램의이 인스턴스에 대 한 셸 명령을 나타냅니다.

```
m_nShellCommand;
```

### <a name="remarks"></a>설명

이 데이터 멤버에 대 한 형식은 다음 열거형된 형식에 정의 되어 있는 `CCommandLineInfo` 클래스입니다.

```
enum {
    FileNew,
    FileOpen,
    FilePrint,
    FilePrintTo,
    FileDDE,
    AppRegister,
    AppUnregister,
    RestartByRestartManager,
    FileNothing = -1
    };
```

이러한 값의 간략 한 설명을 다음 목록을 참조 합니다.

- `CCommandLineInfo::FileNew` 파일 이름은 없으므로 명령줄에서 찾을 수 있는지를 나타냅니다.

- `CCommandLineInfo::FileOpen` 파일 이름을 명령줄에서 찾을 수를 나타내며는 명령줄에서 찾지 못한 다음 플래그 중: `/p`, `/pt`, `/dde`합니다.

- `CCommandLineInfo::FilePrint` 나타내는 `/p` 플래그 명령줄에서 찾을 수 있습니다.

- `CCommandLineInfo::FilePrintTo` 나타내는 `/pt` 플래그 명령줄에서 찾을 수 있습니다.

- `CCommandLineInfo::FileDDE` 나타내는 `/dde` 플래그 명령줄에서 찾을 수 있습니다.

- `CCommandLineInfo::AppRegister` 나타내는 합니다 `/Register` 또는 `/Regserver` 플래그 명령줄에서 찾을 수 및 응용 프로그램은 등록 하 라는 메시지가 표시 되었습니다.

- `CCommandLineInfo::AppUnregister` 나타내는 합니다 `/Unregister` 또는 `/Unregserver` 응용 프로그램은 등록을 취소 하 라는 메시지가 표시 되었습니다.

- `CCommandLineInfo::RestartByRestartManager` 되는 응용 프로그램 다시 시작 관리자가 다시 시작 되었음을 나타냅니다.

- `CCommandLineInfo::FileNothing` 시작 시 새 MDI 자식 창에 표시 되지 않습니다. 기본적으로 응용 프로그램 마법사에서 생성 된 MDI 응용 프로그램 시작 시 새 자식 창을 표시. 이 기능을 해제 하려면 응용 프로그램 사용 `CCommandLineInfo::FileNothing` 호출할 때 셸 명령과 [ProcessShellCommand](../../mfc/reference/cwinapp-class.md#processshellcommand)합니다. `ProcessShellCommand` 호출한 합니다 `InitInstance( )` 모든 `CWinApp` 클래스를 파생 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#55](../../mfc/codesnippet/cpp/ccommandlineinfo-class_2.cpp)]

##  <a name="m_strdrivername"></a>  CCommandLineInfo::m_strDriverName

명령줄에서 세 번째 비 플래그 매개 변수의 값을 저장합니다.

```
CString m_strDriverName;
```

### <a name="remarks"></a>설명

이 매개 변수는 일반적으로 인쇄에 셸 명령에 대 한 프린터 드라이버의 이름입니다. 기본 구현을 [ParseParam](#parseparam) 설정 하는 경우에만이 데이터 멤버는 `/pt` 플래그 명령줄에서 찾을 수 있습니다.

##  <a name="m_strfilename"></a>  CCommandLineInfo::m_strFileName

명령줄에서 첫 번째 비 플래그 매개 변수의 값을 저장합니다.

```
CString m_strFileName;
```

### <a name="remarks"></a>설명

이 매개 변수는 일반적으로 열 파일의 이름입니다.

##  <a name="m_strportname"></a>  CCommandLineInfo::m_strPortName

명령줄에서 네 번째 비 플래그 매개 변수의 값을 저장합니다.

```
CString m_strPortName;
```

### <a name="remarks"></a>설명

이 매개 변수는 일반적으로 인쇄에 셸 명령에 대 한 프린터 포트의 이름입니다. 기본 구현을 [ParseParam](#parseparam) 설정 하는 경우에만이 데이터 멤버는 `/pt` 플래그 명령줄에서 찾을 수 있습니다.

##  <a name="m_strprintername"></a>  CCommandLineInfo::m_strPrinterName

명령줄에서 두 번째 비 플래그 매개 변수의 값을 저장합니다.

```
CString m_strPrinterName;
```

### <a name="remarks"></a>설명

이 매개 변수는 일반적으로 인쇄에 셸 명령에 대 한 프린터의 이름입니다. 기본 구현을 [ParseParam](#parseparam) 설정 하는 경우에만이 데이터 멤버는 `/pt` 플래그 명령줄에서 찾을 수 있습니다.

##  <a name="m_strrestartidentifier"></a>  CCommandLineInfo::m_strRestartIdentifier

고유한 명령줄에 대 한 식별자를 다시 시작합니다.

```
CString m_strRestartIdentifier;
```

### <a name="remarks"></a>설명

다시 시작 식별자는 응용 프로그램의 각 인스턴스에 대해 고유 합니다.

다시 시작 관리자 응용 프로그램을 종료 하 고 다시 시작 하도록 구성 된, 다시 시작 관리자 실행 응용 프로그램 다시 시작 식별자를 사용 하 여 명령줄에서 선택적 매개 변수로 사용 됩니다. 다시 시작 관리자를 다시 시작 식별자가 사용 될 경우 응용 프로그램 다시 이전에 열려 있는 문서를 업데이트 하 고 자동 저장 된 파일을 복구할 수 있습니다.

##  <a name="parseparam"></a>  CCommandLineInfo::ParseParam

프레임 워크는 명령줄에서 개별 매개 변수를 구문 분석/해석 하려면이 함수를 호출 합니다. 두 번째 버전에서 첫 번째 다른 유니코드 프로젝트에만 합니다.

```
virtual void ParseParam(
    const char* pszParam,
    BOOL bFlag,
    BOOL bLast);

virtual void ParseParam(
    const TCHAR* pszParam,
    BOOL bFlag,
    BOOL bLast);
```

### <a name="parameters"></a>매개 변수

*pszParam*<br/>
매개 변수를 플래그 합니다.

*bFlag*<br/>
나타냅니다 여부 *pszParam* 매개 변수 또는 플래그입니다.

*bLast*<br/>
마지막 매개 변수 또는 명령줄에서 플래그 인지 여부를 나타냅니다.

### <a name="remarks"></a>설명

[CWinApp::ParseCommandLine](../../mfc/reference/cwinapp-class.md#parsecommandline) 호출 `ParseParam` 되 면 각 매개 변수 또는 명령줄에서 플래그에 대 한 인수를 전달 *pszParam*합니다. 매개 변수의 첫 번째 문자가 ' **-**'또는' **/**'를 제거는 및 *bFlag* 가 TRUE로 설정 합니다. 마지막 매개 변수를 구문 분석할 때 *블 래 스 트* 가 TRUE로 설정 합니다.

이 함수의 기본 구현은 다음 플래그를 인식 합니다. `/p`, `/pt`, `/dde`, `/Automation`, 및 `/Embedding`다음 표에 나와 있는 것 처럼:

|명령줄 인수|명령 실행|
|----------------------------|----------------------|
|*app*|새 파일입니다.|
|*app* filename|파일을 엽니다.|
|*app* `/p` filename|파일이 기본 프린터로 인쇄 됩니다.|
|*앱* `/pt` filename 프린터 드라이버 포트|파일을 지정 된 프린터로 인쇄 합니다.|
|*app* `/dde`|시작 되 고 await DDE 명령입니다.|
|*app* `/Automation`|OLE 자동화 서버를 시작 합니다.|
|*app* `/Embedding`|포함된 OLE 항목 편집을 시작 합니다.|
|*app* `/Register`<br /><br /> *app* `/Regserver`|모든 등록 작업을 수행 하는 응용 프로그램을 알립니다.|
|*app* `/Unregister`<br /><br /> *app* `/Unregserver`|등록 취소 작업을 수행 하려면 응용 프로그램을 알립니다.|

이 정보에 저장 됩니다 [m_bRunAutomated](#m_brunautomated)하십시오 [m_bRunEmbedded](#m_brunembedded), 및 [m_nShellCommand](#m_nshellcommand)합니다. 슬래시 플래그 중 하나에서 표시 된 ' **/**'또는 하이픈' **-**'.

기본 구현에 첫 번째 비 플래그 매개 변수를 넣습니다 [m_strFileName](#m_strfilename)합니다. 경우에 `/pt` 플래그를 기본 구현에서는 배치 두 번째, 세 번째 및 네 번째 비 플래그 매개 변수를 [m_strPrinterName](#m_strprintername), [m_strDriverName](#m_strdrivername), 및 [m_ strPortName](#m_strportname), 각각.

기본 구현은 작업도 [m_bShowSplash](#m_bshowsplash) 새 파일의 경우에 true입니다. 새 파일인 경우 사용자는 응용 프로그램 자체와 관련 된 작업을 수행 했습니다. 기타 모든 경우에는 셸을 사용 하 여 기존 파일을 열을 포함 하 여 사용자 동작을 파일 직접 포함 합니다. 문서 중심 관점에서 시작 화면 응용 프로그램 시작을 알릴 필요가 없습니다.

다른 플래그와 매개 변수 값을 처리 하려면 파생된 클래스에서이 함수를 재정의 합니다.

## <a name="see-also"></a>참고자료

[CObject 클래스](../../mfc/reference/cobject-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CWinApp::ParseCommandLine](../../mfc/reference/cwinapp-class.md#parsecommandline)<br/>
[CWinApp::ProcessShellCommand](../../mfc/reference/cwinapp-class.md#processshellcommand)
