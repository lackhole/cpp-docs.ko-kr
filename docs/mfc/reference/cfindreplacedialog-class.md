---
title: CFindReplaceDialog 클래스
ms.date: 11/04/2016
f1_keywords:
- CFindReplaceDialog
- AFXDLGS/CFindReplaceDialog
- AFXDLGS/CFindReplaceDialog::CFindReplaceDialog
- AFXDLGS/CFindReplaceDialog::Create
- AFXDLGS/CFindReplaceDialog::FindNext
- AFXDLGS/CFindReplaceDialog::GetFindString
- AFXDLGS/CFindReplaceDialog::GetNotifier
- AFXDLGS/CFindReplaceDialog::GetReplaceString
- AFXDLGS/CFindReplaceDialog::IsTerminating
- AFXDLGS/CFindReplaceDialog::MatchCase
- AFXDLGS/CFindReplaceDialog::MatchWholeWord
- AFXDLGS/CFindReplaceDialog::ReplaceAll
- AFXDLGS/CFindReplaceDialog::ReplaceCurrent
- AFXDLGS/CFindReplaceDialog::SearchDown
- AFXDLGS/CFindReplaceDialog::m_fr
helpviewer_keywords:
- CFindReplaceDialog [MFC], CFindReplaceDialog
- CFindReplaceDialog [MFC], Create
- CFindReplaceDialog [MFC], FindNext
- CFindReplaceDialog [MFC], GetFindString
- CFindReplaceDialog [MFC], GetNotifier
- CFindReplaceDialog [MFC], GetReplaceString
- CFindReplaceDialog [MFC], IsTerminating
- CFindReplaceDialog [MFC], MatchCase
- CFindReplaceDialog [MFC], MatchWholeWord
- CFindReplaceDialog [MFC], ReplaceAll
- CFindReplaceDialog [MFC], ReplaceCurrent
- CFindReplaceDialog [MFC], SearchDown
- CFindReplaceDialog [MFC], m_fr
ms.assetid: 610f0b5d-b398-4ef6-8c05-e9d6641e50a8
ms.openlocfilehash: de48d8f495802bdf1c5f69e7a4edc41153c9599f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62206015"
---
# <a name="cfindreplacedialog-class"></a>CFindReplaceDialog 클래스

응용 프로그램에서 표준 문자열 찾기/바꾸기 대화 상자를 구현할 수 있습니다.

## <a name="syntax"></a>구문

```
class CFindReplaceDialog : public CCommonDialog
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CFindReplaceDialog::CFindReplaceDialog](#cfindreplacedialog)|생성 하려면이 함수 호출을 `CFindReplaceDialog` 개체입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CFindReplaceDialog::Create](#create)|만들고 표시를 `CFindReplaceDialog` 대화 상자.|
|[CFindReplaceDialog::FindNext](#findnext)|찾 문자열의 다음 항목을 찾기 위해 사용자가 있는지 여부를 결정 하는이 함수를 호출 합니다.|
|[CFindReplaceDialog::GetFindString](#getfindstring)|현재 찾기 문자열을 검색 하려면이 함수를 호출 합니다.|
|[CFindReplaceDialog::GetNotifier](#getnotifier)|검색 하려면이 함수를 호출 합니다 `FINDREPLACE` 등록된 메시지 처리기에서 구조입니다.|
|[CFindReplaceDialog::GetReplaceString](#getreplacestring)|현재 대체 문자열을 검색 하려면이 함수를 호출 합니다.|
|[CFindReplaceDialog::IsTerminating](#isterminating)|대화 상자를 종료 하 고 있는지 여부를 결정 하는이 함수를 호출 합니다.|
|[CFindReplaceDialog::MatchCase](#matchcase)|사용자가 find 문자열의 대/소문자를 정확 하 게 일치 하는지 여부를 결정 하는이 함수를 호출 합니다.|
|[CFindReplaceDialog::MatchWholeWord](#matchwholeword)|사용자가 단어 전체 하려고 하는지 여부를 결정 하는이 함수를 호출 합니다.|
|[CFindReplaceDialog::ReplaceAll](#replaceall)|사용자가 대체 문자열의 모든 발생 하는지 여부를 결정 하는이 함수를 호출 합니다.|
|[CFindReplaceDialog::ReplaceCurrent](#replacecurrent)|사용자가 현재 단어를 바꿀 수 있는지 여부를 결정 하는이 함수를 호출 합니다.|
|[CFindReplaceDialog::SearchDown](#searchdown)|사용자가 아래쪽 방향으로 진행 하도록 검색 여부를 결정 하는이 함수를 호출 합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CFindReplaceDialog::m_fr](#m_fr)|사용자 지정 하는 데 사용 되는 구조를 `CFindReplaceDialog` 개체입니다.|

## <a name="remarks"></a>설명

다른 Windows 공용 대화 상자를 달리 `CFindReplaceDialog` 개체는 모덜리스 사용자가 화면에는 다른 windows와 상호 작용 하도록 허용 합니다. 두 가지 종류의 `CFindReplaceDialog` 개체: 대화 상자 및 찾기/바꾸기 대화 상자를 찾습니다. 대화 상자에서 입력된 된 검색 및 찾기/바꾸기 문자열에 사용자를 수 있지만 함수를 대체 또는 검색을 수행 하지 않습니다. 응용 프로그램을 추가 해야 합니다.

생성 하는 `CFindReplaceDialog` 개체 (있음, 인수 없이) 제공 된 생성자를 사용 합니다. 모덜리스 대화 상자 이므로 사용 하 여 힙 개체를 할당 합니다 **새** 연산자 대신 스택에 합니다.

한 번을 `CFindReplaceDialog` 생성 된 개체를 호출 해야 합니다는 [만들기](#create) 멤버 함수를 만들고 대화 상자를 표시 합니다.

사용 된 [m_fr](#m_fr) 호출 하기 전에 대화 상자를 초기화 하는 구조 `Create`합니다. 합니다 `m_fr` 형식의 구조체가 [FINDREPLACE](/windows/desktop/api/commdlg/ns-commdlg-tagfindreplacea)합니다. 이 구조에 대 한 자세한 내용은 Windows SDK를 참조 하세요.

찾기/바꾸기 요청 알릴 부모 창에 대 한 순서를 사용 해야 하는 Windows [RegisterWindowMessage](/windows/desktop/api/winuser/nf-winuser-registerwindowmessagea) 함수를 사용 합니다 [ON_REGISTERED_MESSAGE](message-map-macros-mfc.md#on_registered_message) 프레임에 대 한 메시지 맵 매크로 이 등록 된 메시지를 처리 하는 창입니다.

사용자가 대화 상자를 종료 하기로 여부를 확인할 수 있습니다는 `IsTerminating` 멤버 함수입니다.

`CFindReplaceDialog` COMMDLG 의존합니다. Windows 버전 3.1 이상 함께 제공 되는 DLL 파일입니다.

대화 상자를 사용자 지정 하려면 클래스를 파생 `CFindReplaceDialog`사용자 지정 대화 상자 템플릿을 제공 하 고 확장 된 컨트롤에서 알림 메시지를 처리 하는 메시지 맵을 추가 합니다. 처리 되지 않은 메시지는 기본 클래스에 전달 되어야 합니다.

후크 함수를 사용자 지정 필요 하지 않습니다.

사용 하 여 대 한 자세한 내용은 `CFindReplaceDialog`를 참조 하세요 [일반 대화 상자 클래스](../../mfc/common-dialog-classes.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

`CFindReplaceDialog`

## <a name="requirements"></a>요구 사항

**헤더:** afxdlgs.h

##  <a name="cfindreplacedialog"></a>  CFindReplaceDialog::CFindReplaceDialog

`CFindReplaceDialog` 개체를 생성합니다.

```
CFindReplaceDialog();
```

### <a name="remarks"></a>설명

때문에 `CFindReplaceDialog` 개체는 모덜리스 대화 상자를 사용 하 여 힙에 생성 해야 합니다 **새** 연산자.

소멸 하는 동안 프레임 워크를 수행 하려고를 **삭제** 대화 상자에 포인터에 대 한 합니다. 스택에 대화 상자를 만든 경우 합니다 **이** 포인터 존재 하지 않는 및 정의 되지 않은 동작이 발생할 수 있습니다.

생성에 대 한 자세한 내용은 `CFindReplaceDialog` 개체를 참조 합니다 [CFindReplaceDialog](../../mfc/reference/cfindreplacedialog-class.md) 개요. 사용 된 [CFindReplaceDialog::Create](#create) 멤버 함수는 대화 상자를 표시 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#170](../../mfc/codesnippet/cpp/cfindreplacedialog-class_1.cpp)]

##  <a name="create"></a>  CFindReplaceDialog::Create

만들고 찾기 또는 찾기/바꾸기 대화 상자 개체의 값에 따라 표시 `bFindDialogOnly`합니다.

```
virtual BOOL Create(
    BOOL bFindDialogOnly,
    LPCTSTR lpszFindWhat,
    LPCTSTR lpszReplaceWith = NULL,
    DWORD dwFlags = FR_DOWN,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>매개 변수

*bFindDialogOnly*<br/>
이 매개 변수를 표시 하려면 TRUE로 설정 된 **찾을** 대화 상자. 표시 하려면 FALSE로 설정 된 **찾기/바꾸기** 대화 상자.

*lpszFindWhat*<br/>
대화 상자가 나타나면 기본 검색 문자열에 대 한 포인터입니다. NULL 인 경우 대화 상자는 기본 검색 문자열을 없습니다.

*lpszReplaceWith*<br/>
대화 상자가 나타나면 기본 대체 문자열에 대 한 포인터입니다. NULL 인 경우 대화 상자는 기본 대체 문자열을 없습니다.

*dwFlags*<br/>
비트 OR 연산자를 사용 하 여 결합 대화 상자에서 설정을 사용자 지정 하 여 하나 이상의 플래그입니다. 기본값은 FR_DOWN 아래쪽 방향으로 진행 하도록 검색 인지를 지정 하는 합니다. 참조 된 [FINDREPLACE](/windows/desktop/api/commdlg/ns-commdlg-tagfindreplacea) 이러한 플래그에 대 한 자세한 내용은 Windows SDK에는 구조입니다.

*pParentWnd*<br/>
대화 상자의 부모 또는 소유자 창에 대 한 포인터입니다. 이 창 찾기/바꾸기 작업을 요청 된 나타내는 특별 한 메시지를 받을입니다. NULL 인 경우 응용 프로그램의 주 창이 사용 됩니다.

### <a name="return-value"></a>반환 값

대화 상자 개체 성공적으로 만들어진 경우 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

찾기/바꾸기 요청 알릴 부모 창에 대 한 순서를 사용 해야 하는 Windows [RegisterWindowMessage](/windows/desktop/api/winuser/nf-winuser-registerwindowmessagea) 함수 반환 값은 응용 프로그램의 인스턴스에 대해 고유한 메시지 번호가 있습니다. 프레임 창에 콜백 함수를 선언 하는 메시지 맵 항목을 있어야 합니다. ( `OnFindReplace` 뒤에 나오는 예제에서)이 등록 된 메시지를 처리 하는 합니다. 다음 코드 조각은 라는 프레임 창 클래스에 대 한이 작업을 수행 하는 방법의 예로 `CMyRichEditView`:

[!code-cpp[NVC_MFCDocView#171](../../mfc/codesnippet/cpp/cfindreplacedialog-class_2.h)]

[!code-cpp[NVC_MFCDocView#172](../../mfc/codesnippet/cpp/cfindreplacedialog-class_3.cpp)]

[!code-cpp[NVC_MFCDocView#173](../../mfc/codesnippet/cpp/cfindreplacedialog-class_4.cpp)]

내에 `OnFindReplace` 함수를 사용 하 여 사용자의 의도 해석 합니다 [CFindReplaceDialog::FindNext](#findnext) 및 [CFindReplaceDialog::IsTerminating](#isterminating) 메서드를 만들면 코드 찾기/바꾸기 작업입니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CFindReplaceDialog::CFindReplaceDialog](#cfindreplacedialog)합니다.

##  <a name="findnext"></a>  CFindReplaceDialog::FindNext

검색 문자열의 다음 항목을 찾기 위해 사용자가 있는지 여부를 확인 하려면 콜백 함수에서이 함수를 호출 합니다.

```
BOOL FindNext() const;
```

### <a name="return-value"></a>반환 값

검색 문자열의 다음 항목을 찾기 위해 사용자가 0이 아닌 값 그렇지 않으면 0입니다.

##  <a name="getfindstring"></a>  CFindReplaceDialog::GetFindString

검색할 기본 문자열을 검색 하려면 콜백 함수에서이 함수를 호출 합니다.

```
CString GetFindString() const;
```

### <a name="return-value"></a>반환 값

기본 찾을 문자열입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#69](../../mfc/codesnippet/cpp/cfindreplacedialog-class_5.cpp)]

##  <a name="getnotifier"></a>  CFindReplaceDialog::GetNotifier

현재 찾기 및 바꾸기 대화 상자에 대 한 포인터를 검색 하려면이 함수를 호출 합니다.

```
static CFindReplaceDialog* PASCAL GetNotifier(LPARAM lParam);
```

### <a name="parameters"></a>매개 변수

*lParam*<br/>
합니다 *lparam* 프레임 창에 전달 된 값 `OnFindReplace` 멤버 함수입니다.

### <a name="return-value"></a>반환 값

현재 대화 상자에 대 한 포인터입니다.

### <a name="remarks"></a>설명

현재 대화 상자에 액세스 하 여 해당 멤버를 호출 하 여 함수 및 액세스를 콜백 함수 내에서 사용 해야는 `m_fr` 구조입니다.

### <a name="example"></a>예제

참조 [CFindReplaceDialog::Create](#create) 찾기 및 바꾸기 대화 상자에서 알림을 받을 OnFindReplace 처리기를 등록 하는 방법의 예입니다.

[!code-cpp[NVC_MFCDocView#69](../../mfc/codesnippet/cpp/cfindreplacedialog-class_5.cpp)]

##  <a name="getreplacestring"></a>  CFindReplaceDialog::GetReplaceString

현재 대체 문자열을 검색 하려면이 함수를 호출 합니다.

```
CString GetReplaceString() const;
```

### <a name="return-value"></a>반환 값

검색된 문자열을 바꾸는 데 사용할 기본 문자열입니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CFindReplaceDialog::GetFindString](#getfindstring)합니다.

##  <a name="isterminating"></a>  CFindReplaceDialog::IsTerminating

사용자가 대화 상자를 종료 하기로 여부를 확인 하 여 콜백 함수 내에서이 함수를 호출 합니다.

```
BOOL IsTerminating() const;
```

### <a name="return-value"></a>반환 값

0이 아닌 사용자는 대화 상자를 종료 하기로 결정 했습니다 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 함수는 0이 아닌 반환 하는 경우 호출 해야 합니다 `DestroyWindow` 현재 대화의 멤버 함수 상자 하 고 모든 대화 상자 포인터 변수를 NULL로 설정 합니다. 필요에 따라도 마지막으로 입력 한 찾기/바꾸기 텍스트를 저장할 고 찾기/바꾸기 대화 상자를 초기화 하는 데 사용할 수 있습니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CFindReplaceDialog::GetFindString](#getfindstring)합니다.

##  <a name="m_fr"></a>  CFindReplaceDialog::m_fr

사용자 지정 하는 데는 `CFindReplaceDialog` 개체입니다.

```
FINDREPLACE m_fr;
```

### <a name="remarks"></a>설명

`m_fr` 형식의 구조가 [FINDREPLACE](/windows/desktop/api/commdlg/ns-commdlg-tagfindreplacea)합니다. 해당 멤버는 대화 상자 개체의 특성을 저장합니다. 생성 한 후에 `CFindReplaceDialog` 개체를 사용할 수 있습니다 `m_fr` 대화 상자에서 다양 한 값을 수정 합니다.

이 구조에 대 한 자세한 내용은 참조는 `FINDREPLACE` Windows SDK에는 구조입니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CFindReplaceDialog::CFindReplaceDialog](#cfindreplacedialog)합니다.

##  <a name="matchcase"></a>  CFindReplaceDialog::MatchCase

사용자가 find 문자열의 대/소문자를 정확 하 게 일치 하는지 여부를 결정 하는이 함수를 호출 합니다.

```
BOOL MatchCase() const;
```

### <a name="return-value"></a>반환 값

찾으려면 검색 문자열 검색 문자열의 대/소문자를 정확히 일치 하는 사용자가 0이 아닌 값 그렇지 않으면 0입니다.

##  <a name="matchwholeword"></a>  CFindReplaceDialog::MatchWholeWord

사용자가 단어 전체 하려고 하는지 여부를 결정 하는이 함수를 호출 합니다.

```
BOOL MatchWholeWord() const;
```

### <a name="return-value"></a>반환 값

사용자가 전체 단어만 검색 문자열의 일치 하는 경우 0이 아닌 값 그렇지 않으면 0입니다.

##  <a name="replaceall"></a>  CFindReplaceDialog::ReplaceAll

사용자가 대체 문자열의 모든 발생 하는지 여부를 결정 하는이 함수를 호출 합니다.

```
BOOL ReplaceAll() const;
```

### <a name="return-value"></a>반환 값

바꾸기 문자열에 일치 하는 모든 문자열 대체 되어야 함을; 사용자가 요청 하는 경우 0이 아닌 값 그렇지 않으면 0입니다.

##  <a name="replacecurrent"></a>  CFindReplaceDialog::ReplaceCurrent

사용자가 현재 단어를 바꿀 수 있는지 여부를 결정 하는이 함수를 호출 합니다.

```
BOOL ReplaceCurrent() const;
```

### <a name="return-value"></a>반환 값

현재 선택된 된 문자열을 바꾸기 문자열 바꿀 수는 사용자가 요청 하는 경우 0이 아닌 값 그렇지 않으면 0입니다.

##  <a name="searchdown"></a>  CFindReplaceDialog::SearchDown

사용자가 아래쪽 방향으로 진행 하도록 검색 여부를 결정 하는이 함수를 호출 합니다.

```
BOOL SearchDown() const;
```

### <a name="return-value"></a>반환 값

사용자 검색 아래쪽 방향;에서 계속을 읽으려는 경우 0이 아닌 값 사용자가 위쪽 방향에서 계속 검색 하는 경우 0입니다.

## <a name="see-also"></a>참고자료

[CCommonDialog 클래스](../../mfc/reference/ccommondialog-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)
