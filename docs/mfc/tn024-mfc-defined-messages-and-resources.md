---
title: 'TN024: MFC에서 정의한 메시지 및 리소스'
ms.date: 11/04/2016
f1_keywords:
- vc.mfc.messages
helpviewer_keywords:
- resources [MFC]
- Windows messages [MFC], MFC-defined
- messages [MFC], MFC
- TN024
ms.assetid: c65353ce-8096-454b-ad22-1a7a1dd9a788
ms.openlocfilehash: 029177821d37d5d26abe0b39ea1581e8a5ad602b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62306027"
---
# <a name="tn024-mfc-defined-messages-and-resources"></a>TN024: MFC에서 정의한 메시지 및 리소스

> [!NOTE]
>  다음 기술 노트는 온라인 설명서에 먼저 포함되어 있었으므로 업데이트되지 않았습니다. 따라서 일부 절차 및 항목은 만료되거나 올바르지 않을 수 있습니다. 최신 정보를 보려면 온라인 설명서 색인에서 관심 있는 항목을 검색하는 것이 좋습니다.

이 내부 Windows 메시지 및 MFC에서 사용 되는 리소스 형식에 설명 합니다. 이 정보는 framework의 구현에 설명 하 고 응용 프로그램을 디버깅 하는 데 도움이 됩니다. 모험에이 모든 정보는 공식적으로 지원 되는 경우에 사용할 수 있습니다이 정보 중 일부 고급 구현에 대 한 합니다.

이 이는 MFC private 구현 세부 정보를 포함합니다. 모든 내용을 미래가 변경 될 수 있습니다. MFC 개인 Windows 메시지 하나의 응용 프로그램의 범위에서 의미가 있지만 시스템 메시지를 포함 하는 나중에 변경 됩니다.

범위의 MFC 개인 Windows 메시지 및 리소스 종류는 예약 된 "시스템" 범위에서 따로 Microsoft Windows에서. 범위에 현재 일부 숫자 들을 사용 하 고 나중에 새 범위에서 사용할 수 있습니다. 현재 사용 되는 번호를 변경할 수 있습니다.

MFC 개인 Windows 메시지 0x360 범위는-0x37F > 합니다.

MFC 개인 리소스 유형은 0xF0 범위의 0xFF-> 합니다.

**MFC 개인 Windows 메시지**

이러한 Windows 메시지 대신 사용 하는 C++ 비교적 느슨한 창 개체 간에 필요한 가상 함수 및 위치는 C++ 가상 함수는 적절 한 것입니다.

이러한 개인 Windows 메시지와 연결 된 매개 변수 구조는 MFC 개인 헤더에 선언 된 ' AFXPRIV 합니다. H'입니다. 이 헤더를 포함 하는 코드의 모든 있습니다 수 의존 문서화 되지 않은 동작 및 중단 될 이후 버전의 MFC 경고가 표시 됩니다.

이러한 메시지 중 하나를 처리를 만들게 드문 경우에서 ON_MESSAGE 메시지 맵 매크로 사용 하 고 제네릭 LRESULT/WPARAM/LPARAM 형식으로 메시지를 처리 해야 합니다.

**WM_QUERYAFXWNDPROC**

이 메시지는 생성 되는 창에 전송 됩니다. WndProc는 경우를 결정 하는 방법으로 보낸 생성 프로세스에서 매우 일찍 **AfxWndProc 합니다. AfxWndProc** 1을 반환 합니다.

|||
|-|-|
|wParam|사용되지 않음|
|lParam|사용되지 않음|
|returns|1에서 처리 하는 경우 **AfxWndProc**|

**WM_SIZEPARENT**

이 메시지는 즉시 해당 자식 프레임 창에서 크기를 조정 하는 동안 전송 됩니다 (`CFrameWnd::OnSize` 호출 `CFrameWnd::RecalcLayout` 호출 하는 `CWnd::RepositionBars`) 관련 프레임의 컨트롤 막대 위치를 변경 합니다. AFX_SIZEPARENTPARAMS 구조를 호출 하는 부모 및 (NULL 일 수 있음)는 HDWP 현재 사용 가능한 클라이언트 사각형에 포함 된 `DeferWindowPos` 그려질 최소화 하기 위해.

|||
|-|-|
|wParam|사용되지 않음|
|lParam|AFX_SIZEPARENTPARAMS 구조의 주소|
|returns|사용 되지 않습니다 (0)|

메시지를 무시 창 레이아웃에서 일부를 갖지를 나타냅니다.

**WM_SETMESSAGESTRING**

이 메시지는 상태 표시줄에 메시지 줄을 업데이트 하도록 요청할 프레임 창에 전송 됩니다. 문자열 ID 또는 LPCSTR 지정 (하지만 둘 다가 아닌) 수 있습니다.

|||
|-|-|
|wParam|문자열 ID (또는 0)|
|lParam|LPCSTR 문자열 (또는 NULL)|
|returns|사용 되지 않습니다 (0)|

**WM_IDLEUPDATECMDUI**

명령 업데이트 UI 처리기의 유휴 시간 업데이트를 구현 하는 유휴 시간에이 메시지가 보내집니다. 창 (일반적으로 컨트롤 막대)에서 메시지를 처리 하는 경우 생성 된 `CCmdUI` 개체 (또는 파생된 클래스의 개체) 호출 및 `CCmdUI::DoUpdate` 각 창에 "항목"에 대 한 합니다. 이 명령 처리기 체인에 있는 개체에 대 한 ON_UPDATE_COMMAND_UI 처리기에 대 한 다시 확인 됩니다.

|||
|-|-|
|wParam|BOOL bDisableIfNoHandler|
|lParam|사용 되지 않습니다 (0)|
|returns|사용 되지 않습니다 (0)|

*bDisableIfNoHandler* 0이 아닌는 ON_UPDATE_COMMAND_UI 아니고 ON_COMMAND 처리기를 사용 하는 경우 UI 개체를 사용 하지 않도록 설정 합니다.

**WM_EXITHELPMODE**

이 메시지에 게시 되는 `CFrameWnd` 상황에 맞는 종료 하는 도움말 모드입니다. 이 메시지의 수신을 시작 하 여 모달 루프를 종료 `CFrameWnd::OnContextHelp`합니다.

|||
|-|-|
|wParam|사용 되지 않습니다 (0)|
|lParam|사용 되지 않습니다 (0)|
|returns|사용되지 않음|

**WM_INITIALUPDATE**

이 메시지는 해당 초기 업데이트를 수행 하기 위해 안전한 시기 문서 템플릿에서 프레임 창의 모든 하위 항목에 전송 됩니다. 에 대 한 호출에 매핑됩니다 `CView::OnInitialUpdate` 에 사용할 수 있지만 `CWnd`-다른 원 샷 업데이트에 대 한 클래스를 파생 합니다.

|||
|-|-|
|wParam|사용 되지 않습니다 (0)|
|lParam|사용 되지 않습니다 (0)|
|returns|사용 되지 않습니다 (0)|

**WM_RECALCPARENT**

이 메시지는 뷰에 의해 해당 부모 창으로 전송 됩니다 (을 통해 가져온 `GetParent`) 레이아웃이 다시 계산을 적용할 (부모를 호출 하는 일반적으로 `RecalcLayout`). OLE 서버 응용 프로그램에서 보기의 총 크기 증가 함에 따라 크기 증가를 프레임에 대 한 필요한 경우 사용 됩니다.

부모 창이이 메시지를 처리 하는 경우 TRUE를 반환 하 고 새 클라이언트 영역 크기를 사용 하 여 lParam 전달 된 사각형을 입력 합니다. 이 `CScrollView` 스크롤 막대 (다음 추가 될 때 창의 외부에 위치)를 올바르게 처리 하려면 서버 개체를 경우 현재 위치 활성화 합니다.

|||
|-|-|
|wParam|사용 되지 않습니다 (0)|
|lParam|LPRECT rectClient NULL 일 수 있습니다.|
|returns|TRUE 이면 새 클라이언트 사각형 반환 FALSE 그렇지 않은 경우|

**WM_SIZECHILD**

이 메시지를 보낼 `COleResizeBar` 소유자 창에 (통해 `GetOwner`) 사용자 크기 조정 핸들을 사용 하 여 크기 조정 막대를 조정 하는 경우. `COleIPFrameWnd` 사용자가 요청한 대로 프레임 창의 위치를 변경 하 여이 메시지에 응답 합니다.

새 사각형 크기 조정 막대를 포함 하는 프레임 창 기준으로 클라이언트 좌표에서 지정 된 lParam 가리키는 합니다.

|||
|-|-|
|wParam|사용 되지 않습니다 (0)|
|lParam|LPRECT rectNew|
|returns|사용 되지 않습니다 (0)|

**WM_DISABLEMODAL**

이 메시지를 비활성화 하 고 있는 프레임 창을 소유 하는 모든 팝업 창으로 전송 됩니다. 프레임 창 팝업을 사용 하지 않도록 설정할 것인지 여부를 확인 하려면 결과 사용 합니다.

프레임 모달 상태로 전환 하는 경우 팝업 창에서 특수 한 처리를 수행 하거나 특정 팝업 창이 비활성화 되지 않도록 하려면이 사용할 수 있습니다. 예를 들어 프레임 창을 모달 상태로 전환 될 때 자체를 삭제 하려면이 메시지를 사용 하는 도구 설명 합니다.

|||
|-|-|
|wParam|사용 되지 않습니다 (0)|
|lParam|사용 되지 않습니다 (0)|
|returns|0이 아닌 하 **되지** 창 사용 안 함, 0은 창이 비활성화 됩니다|

**WM_FLOATSTATUS**

이 메시지 프레임 활성화 또는 비활성화 다른 최상위 프레임 창이 프레임 창이 소유한 모든 팝업 창으로 전송 됩니다. MFS_SYNCACTIVE 구현에 의해 사용 됩니다 `CMiniFrameWnd`, 팝업 창 활성화의 최상위 수준 프레임 창이 활성화와 동기화 되도록 합니다.

|||
|-|-|
|wParam|다음 값 중 하나입니다.<br /><br /> FS_SHOW<br /><br /> FS_HIDE<br /><br /> FS_ACTIVATE<br /><br /> FS_DEACTIVATE<br /><br /> FS_ENABLEFS_DISABLE<br /><br /> FS_SYNCACTIVE|
|lParam|사용 되지 않습니다 (0)|

반환 값 0이 아닌 경우 FS_SYNCACTIVE 집합과 창 동기화를 활성화 해야 합니다. 부모 프레임입니다. `CMiniFrameWnd` 스타일 MFS_SYNCACTIVE로 설정 된 경우 0이 아닌 값을 반환 합니다.

자세한 내용은 참조 구현의 `CMiniFrameWnd`합니다.

## <a name="wmactivatetoplevel"></a>WM_ACTIVATETOPLEVEL

이 메시지는 해당 최상위 "그룹" 창을 활성화 또는 비활성화 하는 경우 최상위 창으로 전송 됩니다. 창의 최상위 그룹의 일부인 경우 (없습니다 부모 또는 소유자) 최상위 창이 또는 이러한 창을 소유입니다. 이 메시지 WM_ACTIVATEAPP를 사용 하 여 유사 하지만 (OLE 응용 프로그램에서 공통) 단일 창 계층의 서로 다른 프로세스에 속한 windows 있는 상황에서 작동 하는 혼합 합니다.

## <a name="wmcommandhelp-wmhelphittest-wmexithelpmode"></a>WM_COMMANDHELP, WM_HELPHITTEST, WM_EXITHELPMODE

이러한 메시지는 상황에 맞는 도움말의 구현에서 사용 됩니다. 참조 하십시오 [Technical Note 28](../mfc/tn028-context-sensitive-help-support.md) 자세한 내용은 합니다.

## <a name="mfc-private-resource-formats"></a>MFC 개인 리소스 형식

현재 MFC 두 개인 리소스 형식을 정의합니다. RT_TOOLBAR 및 RT_DLGINIT 합니다.

## <a name="rttoolbar-resource-format"></a>RT_TOOLBAR 리소스 형식

응용 프로그램 마법사에서 제공한 기본 도구 모음의 MFC 4.0에 도입 된는 RT_TOOLBAR 사용자 지정 리소스를 기반으로 합니다. 도구 모음 편집기를 사용 하 여이 리소스를 편집할 수 있습니다.

## <a name="rtdlginit-resource-format"></a>RT_DLGINIT 리소스 형식

추가 대화 상자 초기화 정보를 저장 한 MFC 개인 리소스 형식이 사용 됩니다. 콤보 상자에 저장 된 초기 문자열을 포함 합니다. 이 리소스의 형식은 기능이 없는 수동으로 편집할 수 있지만 시각적 개체에서 처리 됩니다 C++입니다.

Visual C++ 이 RT_DLGINIT 리소스는 리소스의 정보를 사용 하는 API 대신 되므로 MFC의 관련된 기능을 사용할 필요가 없습니다. 시각적 개체를 사용 하 여 C++ 훨씬 쉽게 작성, 유지 관리 및 장기 실행 응용 프로그램을 변환 합니다.

RT_DLGINIT 리소스의 기본 구조는 다음과 같습니다.

```
+---------------+    \
| Control ID    |   UINT             |
+---------------+    |
| Message #     |   UINT             |
+---------------+    |
|length of data |   DWORD            |
+---------------+    |   Repeated
|   Data        |   Variable Length  |   for each control
|   ...         |   and Format       |   and message
+---------------+    /
|     0         |   BYTE
+---------------+
```

반복 된 섹션에 있는 컨트롤 ID, 메시지를 보내려고 메시지 # send (표준 Windows 메시지) 및 데이터의 가변 길이를 합니다. Windows 메시지 형태로 전송 됩니다.

```
SendDlgItemMessage(<Control ID>, <Message #>, 0, &<Data>);
```

모든 Windows 메시지 및 데이터 콘텐츠는 매우 일반적인 형식입니다. 시각적 개체 C++ 리소스 편집기 및 MFC는만 Windows 메시지의 제한 된 하위 집합을 지원 합니다. CB_ADDSTRING 콤보 상자 (데이터는 텍스트 문자열)에 대 한 초기 목록을 선택 합니다.

## <a name="see-also"></a>참고자료

[번호별 기술 참고 사항](../mfc/technical-notes-by-number.md)<br/>
[범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)
