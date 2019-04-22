---
title: 'TN041: Mfc-ole 2로 MFC-OLE1 마이그레이션'
ms.date: 10/18/2018
f1_keywords:
- vc.mfc.ole
helpviewer_keywords:
- OLE1 [MFC]
- migrating OLE1 to OLE2
- migration [MFC], OLE1 to OLE2
- OLE2 [MFC]
- porting OLE1 to OLE2
- converting OLE1 to OLE2
- upgrading Visual C++ applications [MFC], OLE1 to OLE2
- TN041
ms.assetid: 67f55552-4b04-4ddf-af0b-4d9eaf5da957
ms.openlocfilehash: b398a1adbf2f47343eed076f32ade5bb2564cd52
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58767979"
---
# <a name="tn041-mfcole1-migration-to-mfcole-2"></a>TN041: MFC/OLE 2로 mfc/ole1 마이그레이션

> [!NOTE]
> 다음 기술 노트는 온라인 설명서에 먼저 포함되어 있었으므로 업데이트되지 않았습니다. 따라서 일부 절차 및 항목은 만료되거나 올바르지 않을 수 있습니다. 최신 정보를 보려면 온라인 설명서 색인에서 관심 있는 항목을 검색하는 것이 좋습니다.

## <a name="general-issues-relating-to-migration"></a>마이그레이션에 관련 된 일반적인 문제

(이상) MFC 2.5에서 OLE 2 클래스의 디자인 목표 중 하나 대부분의 배치 MFC 2.0 OLE 1.0 지원에 대 한 동일한 아키텍처를 유지 하는 것 이었습니다. 결과적으로, 많은 MFC 2.0에서 동일한 OLE 클래스에에서 있는이 버전의 MFC (`COleDocument`, `COleServerDoc`하십시오 `COleClientItem`, `COleServerItem`). 또한 많은 Api를 이러한 클래스에 동일 합니다. 그러나 OLE 2 이므로 전혀 다른 OLE 1.0에서 변경 된 세부 정보 중 일부를 예상할 수 있습니다. MFC 2.0 OLE1 지원에 익숙한 경우 MFC의 2.0 지원을 통해 집 느낄 수 있습니다.

기존 MFC/OLE1 응용 프로그램을 수행 하 고 OLE 2 기능을 추가 하는 경우 먼저이 참고 하십시오. 이 노트에서는 MFC/OLE 2로 OLE1 기능을 이식 하는 동안 발생할 수 있습니다 하 고 다음 MFC 2.0에 포함 된 두 개의 응용 프로그램을 이식 하는 동안 처리 되지 않는 문제를 설명 합니다. 몇 가지 일반적인 문제: MFC OLE 샘플 [OCLIENT](../overview/visual-cpp-samples.md) 및 [HIERSVR](../overview/visual-cpp-samples.md)합니다.

## <a name="mfc-documentview-architecture-is-important"></a>MFC 문서/뷰 아키텍처는 중요 한

이제 응용 프로그램이 MFC의 문서/뷰 아키텍처를 사용 하지 않는 응용 프로그램에 OLE 2 지원을 추가 하려는 경우에 문서/뷰를 이동할 수 때가입니다. 응용 프로그램에 기본 제공 아키텍처와 mfc 구성 요소를 사용 하는 면만 실현 됩니다 많은 MFC의 OLE 2 클래스의 혜택.

MFC 아키텍처를 사용 하지 않고 서버 또는 컨테이너를 구현 하는 것은 가능 하지만 권장 하지는 않습니다.

## <a name="use-mfc-implementation-instead-of-your-own"></a>사용자 고유의 대신 사용 하 여 MFC 구현

와 같은 클래스 구현 "MFC"고정 `CToolBar`, `CStatusBar`, 및 `CScrollView` OLE 2 지원에 대 한 특수 사례 코드가 기본 제공 합니다. 따라서 응용 프로그램에서 이러한 클래스를 사용할 수 있는 경우 노력에 있도록 OLE 인식에서 작업할 수 있습니다. 마찬가지로 클래스 "롤 your own" 여기에 이러한 목적을 위해 있지만 것이 좋습니다. 유사한 기능을 구현 하는 경우 MFC 소스 코드를 몇 가지 세부적인 사항을 OLE의 처리에 대 한 훌륭한 참조 (특히 있어는 내부 활성화에).

## <a name="examine-the-mfc-sample-code"></a>MFC 샘플 코드를 검사 합니다.

MFC 샘플 OLE 기능을 포함 하는 여러 가지가 있습니다. 각 응용이 프로그램은 다른 각도에서 OLE를 구현합니다.

- [HIERSVR](../overview/visual-cpp-samples.md) 대부분 서버 응용 프로그램으로 사용 해야 합니다. 이 MFC/OLE1 응용 프로그램으로 MFC 2.0에 포함 된 및 MFC/OLE 2로 이식 되었으며 OLE 2에서 사용할 수 있는 많은 OLE 기능을 구현 하는 확장 합니다.

- [OCLIENT](../overview/visual-cpp-samples.md) 독립 실행형 컨테이너 응용 프로그램을 컨테이너의 관점에서 다양 한 OLE 기능을 보여 주기 위한 것입니다. 너무이 MFC 2.0에서 포팅된 및 다양 한 사용자 지정 클립보드 형식 및 포함 된 항목에 대 한 링크와 같은 고급 OLE 기능을 지원 하도록 확장 합니다.

- [DRAWCLI](../overview/visual-cpp-samples.md) 이 응용 프로그램 구현 OLE 컨테이너 지원 훨씬 OCLIENT는 같은 점을 제외 하 고 기존 개체 지향 그리기 프로그램의 프레임 워크 내에서 수행 합니다. OLE 컨테이너 지원을 구현 하 고 기존 응용 프로그램에 통합할 수 있는 방법을 있습니다 보여 합니다.

- [SUPERPAD](../overview/visual-cpp-samples.md) 세밀 하 게에서는 독립 실행형 응용 프로그램 뿐만 아니라이 응용 프로그램에 OLE 서버 이기도 합니다. 구현 server 지원은 상당히 원칙은입니다. 특히 관심 데이터를 클립보드에 복사할 OLE 클립보드 서비스를 사용 하는 방법 이지만 클립보드 붙여넣기 기능을 구현 하는 Windows "편집" 컨트롤에 기본 제공 기능을 사용 합니다. 새 OLE Api를 사용 하 여 통합 뿐만 아니라 기존의 Windows API 사용의 흥미로운 혼합 하 여 보여 줍니다.

샘플 응용 프로그램에 대 한 자세한 내용은 도움말을 참조 하십시오 "MFC 샘플"입니다.

## <a name="case-study-oclient-from-mfc-20"></a>사례 연구: MFC 2.0 OCLIENT

위에서 설명 했 듯이 [OCLIENT](../overview/visual-cpp-samples.md) 고 MFC 2.0에 포함 된 OLE MFC/OLE1을 사용 하 여 구현 합니다. 이 응용 프로그램 처음으로 변환 되었습니다 MFC/OLE 2 클래스를 사용 하는 단계에 대 한 설명은 다음과 같습니다. 초기 포트 MFC/OLE 클래스 이해를 돕기 위해 완료 된 후 다양 한 기능이 추가 되었습니다. 이러한 기능은 다루지 않습니다. 이러한 고급 기능에 대 한 자세한 내용은 샘플 자체를 참조 하십시오.

> [!NOTE]
> 컴파일러 오류 및 단계별 프로세스를 시각적 개체를 사용 하 여 만든 C++ 2.0. 시각적 개체를 사용 하 여 특정 오류 메시지 및 위치 변경 될 수 있습니다 C++ 4.0 있지만 개념 정보를 유효한 상태로 유지 합니다.

## <a name="getting-it-up-and-running"></a>해당 시작 및 실행

OCLIENT 샘플 MFC/OLE에 포트를 수행 하는 방법은 빌드하고 이어지는 확실 한 컴파일러 오류를 수정 하 여 시작 하는 것입니다. MFC 2.0에서 OCLIENT 샘플을 사용 하 고이 버전의 MFC에서 컴파일할 경우 많은 오류를 해결 하려면 많지 않은지를 찾을 수 있습니다. 발생 한 순서 대로 오류에 대 한 설명은 다음과 같습니다.

## <a name="compile-and-fix-errors"></a>컴파일 및 오류 수정

```Output
\oclient\mainview.cpp(104) : error C2660: 'Draw' : function does not take 4 parameters
```

첫 번째 오류 문제 `COleClientItem::Draw`합니다. OLE1 MFC/MFC/OLE 버전은 보다 많은 매개 변수가 걸린입니다. 추가 매개 변수는 필요한 및이 예에서 같이 일반적으로 NULL 종종 되지 않았습니다. 이 버전의 MFC 그리고은 CDC 메타 파일 DC 때는 lpWBounds 값을 자동으로 결정할 수입니다. 또한 pFormatDC 매개 변수는 더 이상 필요한 프레임 워크 "DC"의 특성에 전달 된 pDC에서 빌드됩니다. 이 문제를 해결 하려면 단순히 두가 제거 되므로 추가 그리기 호출에 매개 변수를 NULL입니다.

```Output
\oclient\mainview.cpp(273) : error C2065: 'OLE_MAXNAMESIZE' : undeclared identifier
\oclient\mainview.cpp(273) : error C2057: expected constant expression
\oclient\mainview.cpp(280) : error C2664: 'CreateLinkFromClipboard' : cannot convert parameter 1 from 'char [1]' to 'enum ::tagOLERENDER '
\oclient\mainview.cpp(286) : error C2664: 'CreateFromClipboard' : cannot convert parameter 1 from 'char [1]' to 'enum ::tagOLERENDER '
\oclient\mainview.cpp(288) : error C2664: 'CreateStaticFromClipboard' : cannot convert parameter 1 from 'char [1]' to 'enum ::tagOLERENDER '
```

결과 사실에서 위의 오류는 모든는 `COleClientItem::CreateXXXX` mfc/ole1 함수 필요한 고유 이름을 나타내는 항목을 전달할 수 있습니다. 이 기본 OLE API의 요구 사항입니다. 이 OLE 2 DDE (이름이 DDE 대화에 사용 된)의 기본 통신 메커니즘으로 사용 하지 않으므로 MFC/OLE 2에서 필요 하지 않습니다. 이 문제를 해결 하려면 제거할 수 있습니다는 `CreateNewName` 모든 참조가 뿐만 아니라 함수입니다. 각 MFC/OLE 함수 예상 하는 것이 버전에 대 한 호출에 커서를 배치 하 고 F1 키를 누르면 하면 확인 하는 것이 쉽습니다.

크게 달라 지는 또 다른 영역은 OLE 2 클립보드 처리 됩니다. OLE1을 사용 하 여 클립보드를 사용 하 여 Windows 클립보드 Api 상호 작용 사용 했습니다. OLE 2를 사용 하 여 다른 메커니즘을 사용 하 여 수행 됩니다. MFC/OLE1 Api를 클립보드로 복사 하기 전에 열려 있었던 것으로 간주 한 `COleClientItem` 클립보드로 개체. 이 더 이상 필요 하며 모든 MFC/OLE 클립보드 작업이 실패 하면. 종속성을 제거 하는 코드를 편집 하는 동안 `CreateNewName`를 열고 Windows 클립보드 닫는 코드를 제거 해야 합니다.

```Output
\oclient\mainview.cpp(332) : error C2065: 'AfxOleInsertDialog' : undeclared identifier
\oclient\mainview.cpp(332) : error C2064: term does not evaluate to a function
\oclient\mainview.cpp(344) : error C2057: expected constant expression
\oclient\mainview.cpp(347) : error C2039: 'CreateNewObject' : is not a member of 'CRectItem'
```

오류가이 발생 하면 이러한 발생을 `CMainView::OnInsertObject` 처리기입니다. 명령을 처리 하는 "New Object 삽입" 영역이 다른 몇 가지가 상당히 변경 되었습니다. 이 경우 단순히 병합할 원본 구현을 새 OLE 컨테이너 응용 프로그램에 대 한 응용 프로그램 마법사에서 제공한 쉽습니다. 사실 이것이 다른 응용 프로그램 이식에 적용할 수 있는 방법입니다. MFC/OLE1을 호출 하 여 "개체 삽입" 대화 상자 표시 `AfxOleInsertDialog` 함수입니다. 생성이 버전에는 `COleInsertObject` 대화 상자 개체 및 호출 `DoModal`합니다. 사용 하 여 새 OLE 항목을 만드는 하는 또한을 **CLSID** classname 문자열 대신 합니다. 최종 결과 다음과 같아야 합니다.

```cpp
COleInsertDialog dlg;
if (dlg.DoModal() != IDOK)
    return;

BeginWaitCursor();

CRectItem* pItem = NULL;
TRY
{
    // First create the C++ object
    pItem = GetDocument()->CreateItem();
    ASSERT_VALID(pItem);

    // Initialize the item from the dialog data.
    if (!dlg.CreateItem(pItem))
        AfxThrowMemoryException();
            // any exception will do
    ASSERT_VALID(pItem);

    // run the object if appropriate
    if (dlg.GetSelectionType() == COleInsertDialog::createNewItem)
        pItem->DoVerb(OLEIVERB_SHOW, this);

    // update right away
    pItem->UpdateLink();
    pItem->UpdateItemRectFromServer();

    // set selection to newly inserted item
    SetSelection(pItem);
    pItem->Invalidate();
}
CATCH (CException, e)
{
    // clean up item
    if (pItem != NULL)
        GetDocument()->DeleteItem(pItem);

    AfxMessageBox(IDP_FAILED_TO_CREATE);
}
END_CATCH

EndWaitCursor();
```

> [!NOTE]
> 새 개체 삽입 다를 수 응용 프로그램에 대 한).

포함 하는 데 필요한 이기도 \<afxodlgs.h >에 대 한 선언을 포함 하는 `COleInsertObject` 대화 상자 클래스 뿐만 아니라 다른 표준 대화 상자에서 MFC 제공 합니다.

```Output
\oclient\mainview.cpp(367) : error C2065: 'OLEVERB_PRIMARY' : undeclared identifier
\oclient\mainview.cpp(367) : error C2660: 'DoVerb' : function does not take 1 parameters
```

이러한 오류는 않기 때문에 일부 OLE1 상수 OLE 2에서 변경 된 개념의 경우도 동일 합니다. 이 예에서 `OLEVERB_PRIMARY` 으로 바뀌었습니다.%12%n%n `OLEIVERB_PRIMARY`합니다. 기본 동사 OLE1 및 OLE 2에서는 일반적으로 항목을 클릭할 때 컨테이너에서 실행 됩니다.

또한 `DoVerb` 이제에서 추가 매개 변수-뷰에 대 한 포인터 (`CView`*). 이 매개 변수는 "비주얼 편집" (또는 내부 활성화) 구현에 사용 됩니다. 이제이 이번에이 기능을 구현 하지 않는 때문에 NULL로 매개 변수를 설정 합니다.

재정의 해야 되도록는 프레임 워크 활성화 되지 않습니다 전체 하려고, `COleClientItem::CanActivate` 다음과 같습니다.

```cpp
BOOL CRectItem::CanActivate()
{
    return FALSE;
}
```

```Output
\oclient\rectitem.cpp(53) : error C2065: 'GetBounds' : undeclared identifier
\oclient\rectitem.cpp(53) : error C2064: term does not evaluate to a function
\oclient\rectitem.cpp(84) : error C2065: 'SetBounds' : undeclared identifier
\oclient\rectitem.cpp(84) : error C2064: term does not evaluate to a function
```

MFC/OLE1에 `COleClientItem::GetBounds` 및 `SetBounds` 쿼리 항목의 범위를 조작 하는 데 사용 된 (합니다 `left` 및 `top` 멤버 된 항상 0). MFC/OLE 2에서가 더 직접 지원할 `COleClientItem::GetExtent` 하 고 `SetExtent`를 처리 하는 **크기** 또는 `CSize` 대신 합니다.

에 새 SetItemRectToServer에 대 한 코드와 UpdateItemRectFromServer 호출은 다음과 유사 합니다.

```cpp
BOOL CRectItem::UpdateItemRectFromServer()
{
    ASSERT(m_bTrackServerSize);
    CSize size;
    if (!GetExtent(&size))
        return FALSE;    // blank

    // map from HIMETRIC to screen coordinates
    {
        CClientDC screenDC(NULL);
        screenDC.SetMapMode(MM_HIMETRIC);
        screenDC.LPtoDP(&size);
    }
    // just set the item size
    if (m_rect.Size() != size)
    {
        // invalidate the old size/position
        Invalidate();
        m_rect.right = m_rect.left + size.cx;
        m_rect.bottom = m_rect.top + size.cy;
        // as well as the new size/position
        Invalidate();
    }
    return TRUE;
}

BOOL CRectItem::SetItemRectToServer()
{
    // set the official bounds for the embedded item
    CSize size = m_rect.Size();
    {
        CClientDC screenDC(NULL);
        screenDC.SetMapMode(MM_HIMETRIC);
        screenDC.DPtoLP(&size);
    }
    TRY
    {
        SetExtent(size);    // may do a wait
    }
    CATCH(CException, e)
    {
        return FALSE;  // links will not allow SetBounds
    }
    END_CATCH
    return TRUE;
}
```

```Output
\oclient\frame.cpp(50) : error C2039: 'InWaitForRelease' : is not a member of 'COleClientItem'
\oclient\frame.cpp(50) : error C2065: 'InWaitForRelease' : undeclared identifier
\oclient\frame.cpp(50) : error C2064: term does not evaluate to a function
```

MFC/OLE1 동기 API의 서버에 컨테이너에서 호출 된 *시뮬레이션 된*이므로 OLE1 된 대부분의 경우에서 기본적으로 비동기적입니다. 사용자의 명령을 처리 하기 전에 진행 중인 처리 중인 비동기 호출에 대 한 확인 해야 했습니다. MFC/OLE1 제공 된 `COleClientItem::InWaitForRelease` 이렇게 하는 것에 대 한 함수입니다. MFC/OLE 2에서이 아니므로 필요한 OnCommand 재정의 CMainFrame 모두 함께 제거할 수 있습니다.

이 시점에서 OCLIENT을 컴파일하고 연결 됩니다.

## <a name="other-necessary-changes"></a>필요한 다른 변경 내용

하지만 수행 되지 않으며 계속 OCLIENT 실행에서는 몇 가지 있습니다. 나중에 대신 이제 이러한 문제를 해결 하는 것이 좋습니다.

먼저, OLE 라이브러리를 초기화 하는 데 필요한 것입니다. 호출 하 여 이렇게 `AfxOleInit` 에서 `InitInstance`:

```cpp
if (!AfxOleInit())
{
    AfxMessageBox("Failed to initialize OLE libraries");
    return FALSE;
}
```

또한 매개 변수 목록 변경 내용에 대 한 가상 함수에 대 한 확인 하는 것이 좋습니다. 이러한 함수 중 하나는 `COleClientItem::OnChange`, 모든 MFC/OLE 컨테이너 응용 프로그램에서 재정의 합니다. 온라인 도움말을 보고를 추가 'DWORD dwParam'가 추가 되었는지 표시 됩니다. 새 CRectItem::OnChange 아래와 같습니다.

```cpp
void
CRectItem::OnChange(OLE_NOTIFICATION wNotification, DWORD dwParam)
{
    if (m_bTrackServerSize && !UpdateItemRectFromServer())
    {
        // Blank object
        if (wNotification == OLE_CLOSED)
        {
            // no data received for the object - destroy it
            ASSERT(!IsVisible());
            GetDocument()->DeleteItem(this);
            return; // no update (item is gone now)
        }
    }
    if (wNotification != OLE_CLOSED)
        Dirty();
    Invalidate();
    // any change will cause a redraw
}
```

MFC/OLE1 컨테이너 응용 프로그램에서 문서 클래스 파생 `COleClientDoc`합니다. MFC/OLE 2에서이 클래스는 제거 되 고 바뀝니다 `COleDocument` (이 새 조직을 쉽게 컨테이너/서버 응용 프로그램 빌드). **#define** 매핑되 `COleClientDoc` 에 `COleDocument` OCLIENT 같은 MFC/OLE 2로 mfc/ole1 응용 프로그램 이식 간소화 하기 위해. 제공 되지 않은 기능 중 하나 `COleDocument` 에서 제공 하는 `COleClientDoc` 표준 명령 메시지 맵 항목입니다. 이 그렇게 하지 않은 사용 되는 서버 응용 프로그램, `COleDocument` (간접적으로)을 포함 하지 하를 사용 하 여 이러한 명령 처리기의 오버 헤드가 컨테이너/서버 응용 프로그램이 아닌 합니다. CMainDoc 메시지 맵에 다음 항목을 추가 해야 합니다.

```cpp
ON_UPDATE_COMMAND_UI(ID_EDIT_PASTE, OnUpdatePasteMenu)
ON_UPDATE_COMMAND_UI(ID_EDIT_PASTE_LINK, OnUpdatePasteLinkMenu)
ON_UPDATE_COMMAND_UI(ID_OLE_EDIT_LINKS, OnUpdateEditLinksMenu)
ON_COMMAND(ID_OLE_EDIT_LINKS, COleDocument::OnEditLinks)
ON_UPDATE_COMMAND_UI(ID_OLE_VERB_FIRST, OnUpdateObjectVerbMenu)
ON_UPDATE_COMMAND_UI(ID_OLE_EDIT_CONVERT, OnUpdateObjectVerbMenu)
ON_COMMAND(ID_OLE_EDIT_CONVERT, OnEditConvert)
```

이러한 명령의 모든 구현은 `COleDocument`,이 문서에 대 한 기본 클래스입니다.

이 OCLIENT 기능 OLE 컨테이너 응용 프로그램입니다. (OLE1 또는 OLE 2) 모든 형식의 항목을 삽입 하는 것이 가능 합니다. 내부 활성화를 사용 하도록 설정 하는 데 필요한 코드 구현 되지 않으면 이후 항목은 OLE1와 마찬가지로 대부분 별도 창에서 편집 됩니다. 다음 단원에서는 내부 편집 ("비주얼 편집"이 라고도 함)을 사용 하도록 설정 하려면 필요에 따라 변경 합니다.

## <a name="adding-visual-editing"></a>"비주얼 편집" 추가

OLE의 가장 흥미로운 기능 중 하나에 내부 활성화 (또는 "비주얼 편집")입니다. 이 기능에는 서버 응용 프로그램을 사용자에 대 한 더 원활 하 게 편집 인터페이스를 제공 하는 컨테이너의 사용자 인터페이스의 일부를 통해 데 있습니다. OCLIENT에 내부 활성화를 구현 하려면 몇 가지 특별 한 리소스를 몇 가지 추가 코드 뿐만 아니라 추가 해야 합니다. 이러한 리소스와 코드는 일반적으로 응용 프로그램 마법사에서 제공-"Container" 지원 사용 하 여 새 응용 프로그램 마법사에서 응용 프로그램에서 직접 가져온 된 코드 대부분 사실입니다.

먼저, 전체 활성 상태인 항목 때 사용할 메뉴 리소스를 추가 하는 데 필요한 것입니다. 시각적 개체에이 추가 메뉴 리소스를 만들 수 있습니다 C++ IDR_OCLITYPE 리소스 복사 및 파일과 창 팝업 남기고 모두 제거 합니다. 구분선을 두 그룹의 분리를 나타내려면 파일과 창 팝업 사이 삽입 됩니다 (처럼 보여야 합니다. 파일 &#124; &#124; 창). 이러한 구분 기호 의미 하 고 서버 및 컨테이너 메뉴를 병합 하는 방법에 대 한 자세한 내용은 참조 [메뉴 및 리소스: 메뉴 병합](../mfc/menus-and-resources-menu-merging.md)입니다.

만든 이러한 메뉴를 만든 후에 대 한 프레임 워크를 사용 해야 합니다. 호출 하 여 이렇게 `CDocTemplate::SetContainerInfo` 여 InitInstance에 문서 템플릿 목록에 추가 하기 전에 문서 서식 파일에 대 한 합니다. 문서 서식 파일을 등록 하려면 새 코드는 다음과 같습니다.

```cpp
CDocTemplate* pTemplate = new CMultiDocTemplate(
    IDR_OLECLITYPE,
    RUNTIME_CLASS(CMainDoc),
    RUNTIME_CLASS(CMDIChildWnd), // standard MDI child frame
    RUNTIME_CLASS(CMainView));

pTemplate->SetContainerInfo(IDR_OLECLITYPE_INPLACE);

AddDocTemplate(pTemplate);
```

IDR_OLECLITYPE_INPLACE 리소스에 시각적 개체에서 만든 특수 한 전체 리소스는 C++입니다.

내부 활성화를 사용 하려면 몇 가지 모두에서 변경 해야 하는 합니다 `CView` (CMainView) 파생 클래스와 `COleClientItem` 파생 클래스 (CRectItem). 응용 프로그램 마법사에서 제공 하는 모든이 재정의 및 대부분의 구현은 기본 응용 프로그램 마법사에서 응용 프로그램에서 직접 제공 됩니다.

이 포트의 첫 번째 단계에서는 내부 활성화를 재정의 하 여 완전히 비활성화 되었습니다 `COleClientItem::CanActivate`합니다. 내부 활성화를 허용 하도록이 재정의 제거 해야 합니다. NULL에 대 한 모든 호출에 전달 된 또한 `DoVerb` (두 개 정도의) 되었으므로 뷰에 제공만 내부 활성화에 필요한 합니다. 내부 활성화를 완벽 하 게 구현 하려면 올바른 보기에 전달 하는 데 필요한 것은 `DoVerb` 호출 합니다. 이러한 호출 중 하나는 `CMainView::OnInsertObject`:

```cpp
pItem->DoVerb(OLEIVERB_SHOW, this);
```

에 다른 `CMainView::OnLButtonDblClk`:

```cpp
m_pSelection->DoVerb(OLEIVERB_PRIMARY, this);
```

재정의 해야 하는 `COleClientItem::OnGetItemPosition`합니다. 이렇게 하면 서버가 항목 활성화 될 때 컨테이너의 창을 기준으로 해당 창의 넣을 위치. OCLIENT에 대 한 구현은 매우 간단 합니다.

```cpp
void CRectItem::OnGetItemPosition(CRect& rPosition)
{
    rPosition = m_rect;
}
```

대부분의 서버는 "전체 크기를 조정 합니다." 라는 것도 구현 이 사용 하면 서버 창이 크기가 정 해지고 사용자가 항목을 편집 하는 동안 이동 합니다. 컨테이너는 컨테이너 문서 자체 내에서 크기와 위치 영향을 이동 하거나 일반적으로 창의 크기를 조정 하므로이 작업에 참여 해야 합니다. OCLIENT 구현 내부 사각형 크기와 새 위치를 사용 하 여 m_rect에서 유지 관리를 동기화 합니다.

```cpp
BOOL CRectItem::OnChangeItemPosition(const CRect& rectPos)
{
    ASSERT_VALID(this);

    if (!COleClientItem::OnChangeItemPosition(rectPos))
        return FALSE;

    Invalidate();
    m_rect = rectPos;
    Invalidate();
    GetDocument()->SetModifiedFlag();

    return TRUE;
}
```

이 시점에서 활성화 될 수 고가 활성 상태 이면 항목을 이동 및 크기 조정과 처리 하는 항목 수 있도록 충분 한 코드가 있지만 코드가 없는 편집 세션을 종료할 허용 됩니다. 하지만 일부 서버는이 기능 자체 esc 키를 처리 하 여, 컨테이너 제공 항목을 비활성화 하는 두 가지는 것이 좋습니다. (1)에서 항목을 외부에 있고 ESC 키를 눌러 다음을 수행 합니다 (2)를 클릭 합니다.

ESC 키에 대 한 시각적 개체를 사용 하 여 액셀러레이터 키를 추가 C++ 명령에 VK_ESCAPE 키를 매핑하는 ID_CANCEL_EDIT 리소스에 추가 됩니다. 이 명령에 대 한 처리기는 다음과 같습니다.

```cpp
// The following command handler provides the standard
// keyboard user interface to cancel an in-place
// editing session.void CMainView::OnCancelEdit()
{
    // Close any in-place active item on this view.
    COleClientItem* pActiveItem =
        GetDocument()->GetInPlaceActiveItem(this);
    if (pActiveItem != NULL)
        pActiveItem->Close();
    ASSERT(GetDocument()->GetInPlaceActiveItem(this) == NULL);
}
```

사용자 항목 외부 클릭할 수 있는 경우를 처리 하려면 다음 코드에 추가한 시작과 `CMainView::SetSelection`:

```cpp
if (pNewSel != m_pSelection || pNewSel == NULL)
{
    COleClientItem* pActiveItem =
        GetDocument()->GetInPlaceActiveItem(this);
    if (pActiveItem != NULL&& pActiveItem != pNewSel)
        pActiveItem->Close();
}
```

항목에는 내부 활성화 되 면 포커스가 있어야 합니다. 이 경우 되도록 포커스 보기 포커스를 받을 때 항상 활성 항목으로 전송 됩니다 있도록 OnSetFocus 처리:

```cpp
// Special handling of OnSetFocus and OnSize are required
// when an object is being edited in-place.
void CMainView::OnSetFocus(CWnd* pOldWnd)
{
    COleClientItem* pActiveItem =
        GetDocument()->GetInPlaceActiveItem(this);

    if (pActiveItem != NULL &&
        pActiveItem->GetItemState() == COleClientItem::activeUIState)
    {
        // need to set focus to this item if it is same view
        CWnd* pWnd = pActiveItem->GetInPlaceWindow();
        if (pWnd != NULL)
        {
            pWnd->SetFocus();   // don't call the base class
            return;
        }
    }

    CView::OnSetFocus(pOldWnd);
}
```

보기의 크기를 조정 하는 경우 클리핑 사각형을 변경 하는 활성 항목에 알리기 위해 필요 합니다. 에 대 한 처리기를 제공 하면이 위해 `OnSize`:

```cpp
void CMainView::OnSize(UINT nType, int cx, int cy)
{
    CView::OnSize(nType, cx, cy);
    COleClientItem* pActiveItem =
        GetDocument()->GetInPlaceActiveItem(this);
    if (pActiveItem != NULL)
        pActiveItem->SetItemRects();
}
```

## <a name="case-study-hiersvr-from-mfc-20"></a>사례 연구: MFC 2.0 HIERSVR

[HIERSVR](../overview/visual-cpp-samples.md) OLE MFC/OLE1을 사용 하 여 구현 및 MFC 2.0에 포함 되었습니다. 이는이 응용 프로그램 처음으로 변환 되었습니다 MFC/OLE 2 클래스를 사용 하는 단계를 간략하게 설명 합니다. 초기 포트 MFC/OLE 2 클래스 이해를 돕기 위해 완료 된 후 다양 한 기능이 추가 되었습니다. 이러한 기능은 다루지 않습니다. 이러한 고급 기능에 대 한 자세한 내용은 샘플 자체를 참조 하십시오.

> [!NOTE]
> 컴파일러 오류 및 단계별 프로세스를 시각적 개체를 사용 하 여 만든 C++ 2.0. 시각적 개체를 사용 하 여 특정 오류 메시지 및 위치 변경 될 수 있습니다 C++ 4.0 있지만 개념 정보를 유효한 상태로 유지 합니다.

## <a name="getting-it-up-and-running"></a>해당 시작 및 실행

HIERSVR 샘플 MFC/OLE에 포트를 수행 하는 방법은 빌드하고 이어지는 확실 한 컴파일러 오류를 수정 하 여 시작 하는 것입니다. MFC 2.0에서 HIERSVR 샘플을 사용 하 고이 버전의 MFC에서 컴파일할 경우 오류 수 (있더라도 OCLIENT 샘플과 함께 두 개)를 해결 하지는 찾을 수 있습니다. 일반적으로 발생 하는 순서 대로 오류에 대 한 설명은 다음과 같습니다.

## <a name="compile-and-fix-errors"></a>컴파일 및 오류 수정

```Output
\hiersvr\hiersvr.cpp(83) : error C2039: 'RunEmbedded' : is not a member of 'COleTemplateServer'
```

이 첫 번째 오류 훨씬 더 큰 문제를 지적 합니다 `InitInstance` 서버에 대 한 함수입니다. OLE 서버에 필요한 초기화를 실행할 수 OLE1 MFC/응용 프로그램을 확인 해야 하는 가장 큰 변화 중 하나 때문일 수 있습니다. 좋은 방법은 OLE 서버에 대 한 마법사에서는 확인 되어 적절 하 게 코드를 수정 합니다. 유의 사항은 다음과 같습니다.

호출 하 여 OLE 라이브러리를 초기화 하는 데 필요한 것 `AfxOleInit`

서버 리소스 핸들을 사용 하 여 설정할 수 없는 런타임 클래스 정보를 설정 하려면 문서 템플릿 개체에 SetServerInfo 호출 된 `CDocTemplate` 생성자입니다.

프로그램이 /Embedding 명령줄에 있는 경우 응용 프로그램의 주 창이 표시 되지 마십시오.

필요는 **GUID** 문서에 대 한 합니다. 문서 형식 (128 비트)에 대 한 고유 식별자입니다. 응용 프로그램 마법사를 만들어집니다-여기 설명 된 기법을 사용 하는 경우 새 생성 하는 응용 프로그램 마법사에서 서버 응용 프로그램에서 새 코드를 복사, 있습니다 수 단순히 "도용" 응용 프로그램의 GUID입니다. 그렇지 않은 경우는 GUIDGEN을 사용할 수 있습니다. BIN 디렉터리에서 EXE 유틸리티입니다.

"연결" 해야 하는 사용자 `COleTemplateServer` 개체를 호출 하 여 서식 파일에 `COleTemplateServer::ConnectTemplate`입니다.

응용 프로그램은 독립 실행형 실행 될 때 시스템 레지스트리를 업데이트 합니다. 이 이렇게 하면 사용자가 이동 합니다. 응용 프로그램에 대 한 EXE가 새 위치에서 실행 하는 새 위치를 가리키도록 Windows 시스템 등록 데이터베이스를 업데이트 합니다.

모두에 대 한 마법사에서는 기준으로 이러한 변경 내용을 적용 한 후 `InitInstance`, `InitInstance` (및 관련 GUID) HIERSVR 다음과 같이 참조 해야 합니다.

```cpp
// this is the GUID for HIERSVR documents
static const GUID BASED_CODE clsid =
{ 0xA0A16360L, 0xC19B, 0x101A, { 0x8C, 0xE5, 0x00, 0xDD, 0x01, 0x11, 0x3F, 0x12 } };

/////////////////////////////////////////////////////////////////////////////
// COLEServerApp initialization

BOOL COLEServerApp::InitInstance()
{
    // OLE 2 initialization
    if (!AfxOleInit())
    {
        AfxMessageBox("Initialization of the OLE failed!");
        return FALSE;
    }

    // Standard initialization
    LoadStdProfileSettings();   // Load standard INI file options

    // Register document templates
    CDocTemplate* pDocTemplate;
    pDocTemplate = new CMultiDocTemplate(IDR_HIERSVRTYPE,
        RUNTIME_CLASS(CServerDoc),
        RUNTIME_CLASS(CMDIChildWnd),
        RUNTIME_CLASS(CServerView));
    pDocTemplate->SetServerInfo(IDR_HIERSVRTYPE_SRVR_EMB);
    AddDocTemplate(pDocTemplate);

    // create main MDI Frame window
    CMainFrame* pMainFrame = new CMainFrame;
    if (!pMainFrame->LoadFrame(IDR_MAINFRAME))
        return FALSE;
    m_pMainWnd = pMainFrame;

    SetDialogBkColor(); // gray look

    // enable file manager drag/drop and DDE Execute open
    m_pMainWnd->DragAcceptFiles();
    EnableShellOpen();

    m_server.ConnectTemplate(clsid, pDocTemplate, FALSE);
    COleTemplateServer::RegisterAll();

    // try to launch as an OLE server
    if (RunEmbedded())
    {
        // "short-circuit" initialization -- run as server!
        return TRUE;
    }
    m_server.UpdateRegistry();
    RegisterShellFileTypes();

    // not run as OLE server, so show the main window
    if (m_lpCmdLine[0] == '\0')
    {
        // create a new (empty) document
        OnFileNew();
    }
    else
    {
        // open an existing document
        OpenDocumentFile(m_lpCmdLine);
    }

    pMainFrame->ShowWindow(m_nCmdShow);
    pMainFrame->UpdateWindow();

    return TRUE;
}
```

위의 코드를 새 리소스 ID 인 IDR_HIERSVRTYPE_SRVR_EMB 가리킵니다 확인할 수 있습니다. 다른 컨테이너에 포함 된 문서를 편집할 때 사용 되는 메뉴 리소스입니다. MFC/OLE1에서 포함 된 항목을 편집 하려면 특정 메뉴 항목은 즉석에서 수정 되었습니다. 파일 기반 문서를 편집 하는 대신 포함 된 항목을 편집 하는 경우는 완전히 다른 메뉴 구조를 사용 하 여 훨씬 쉽게 이러한 두 가지 별도 모드에 대 한 다른 사용자 인터페이스를 제공 합니다. 나중에 알게 완전히 별도 메뉴 리소스를 포함 된 개체 전체를 편집할 때 사용 됩니다.

이 리소스를 만들려면 리소스 스크립트 시각적 개체로 로드 합니다 C++ 기존 IDR_HIERSVRTYPE 메뉴 리소스 복사 합니다. (이 응용 프로그램 마법사를 사용 하는 동일한 명명 규칙) IDR_HIERSVRTYPE_SRVR_EMB 새 리소스를 이름을 바꿉니다. 그런 다음 "파일 업데이트"; "파일 저장"을 변경 ID ID_FILE_UPDATE 명령으로 제공 합니다. 또한 변경 "파일 이름으로 저장" 파일 복사본으로 저장; ID ID_FILE_SAVE_COPY_AS 명령으로 제공 합니다. 프레임 워크에는 두이 명령은 모두의 구현을 제공 합니다.

```Output
\hiersvr\svritem.h(60) : error C2433: 'OLESTATUS' : 'virtual' not permitted on data declarations
\hiersvr\svritem.h(60) : error C2501: 'OLESTATUS' : missing decl-specifiers
\hiersvr\svritem.h(60) : error C2146: syntax error : missing ';' before identifier 'OnSetData'
\hiersvr\svritem.h(60) : error C2061: syntax error : identifier 'OLECLIPFORMAT'
\hiersvr\svritem.h(60) : error C2501: 'OnSetData' : missing decl-specifiers
```

재정의에서 발생 하는 오류는 여러 가지가 `OnSetData`가 참조 하는 **OLESTATUS** 형식입니다. **OLESTATUS** OLE1 오류를 반환 하는 방법이 있습니다. 변경 되었습니다 **HRESULT** OLE 2에서는 MFC 일반적으로 변환 합니다. 하지만 **HRESULT** 에 `COleException` 오류를 포함 하 합니다. 이 경우 재정의 `OnSetData` 이므로 더 이상 필요에 따라 제거 하는 작업을 수행 하는 작업은 간단 합니다.

```Output
\hiersvr\svritem.cpp(30) : error C2660: 'COleServerItem::COleServerItem' : function does not take 1 parameters
```

`COleServerItem` 생성자 'BOOL' 매개 변수를 추가 합니다. 이 플래그는 메모리 관리에서 수행 되는 방법 결정을 `COleServerItem` 개체입니다. TRUE로 설정 하 여 프레임 워크는 이러한 개체의 메모리 관리를 처리-더 이상 필요 없는 경우 삭제 합니다. 사용 하 여 HIERSVR `CServerItem` (에서 파생 된 `COleServerItem`)이이 플래그를 FALSE로 설정 되므로 해당 네이티브 데이터의 일부로 개체. 이렇게 하면 각 서버 항목을 삭제 하는 경우 결정 HIERSVR이 있습니다.

```Output
\hiersvr\svritem.cpp(44) : error C2259: 'CServerItem' : illegal attempt to instantiate abstract class
\hiersvr\svritem.cpp(44) : error C2259: 'CServerItem' : illegal attempt to instantiate abstract class
```

이러한 오류에서 알 수 있듯이는 다음과 같은 몇 가지 ' 순수 가상 ' 함수 CServerItem에서 재정의 되지 않은입니다. 대개 OnDraw의 매개 변수 목록이 변경 되었습니다 했다는 사실로 원인입니다. 이 오류를 해결 하려면 변경 `CServerItem::OnDraw` 같이 (뿐만 아니라 svritem.h에서 선언).

```cpp
BOOL CServerItem::OnDraw(CDC* pDC, CSize& rSize)
{
    // request from OLE to draw node
    pDC->SetMapMode(MM_TEXT); // always in pixels
    return DoDraw(pDC, CPoint(0, 0), FALSE);
}
```

새 'rSize'입니다. 이렇게 하면 편리 하 게 하는 경우 그리기, 개체의 크기에 맞게 있습니다. 이 크기에 있어야 **HIMETRIC**합니다. 이 경우이 아니므로에서는이 값을 입력 하기에 편리한 프레임 워크에서 호출 `OnGetExtent` 범위를 검색 하려면. 작업을 구현 해야 `OnGetExtent`:

```cpp
BOOL CServerItem::OnGetExtent(DVASPECT dwDrawAspect, CSize& rSize)
{
    if (dwDrawAspect != DVASPECT_CONTENT)
        return COleServerItem::OnGetExtent(dwDrawAspect, rSize);

    rSize = CalcNodeSize();
    return TRUE;
}
```

```Output
\hiersvr\svritem.cpp(104) : error C2065: 'm_rectBounds' : undeclared identifier
\hiersvr\svritem.cpp(104) : error C2228: left of '.SetRect' must have class/struct/union type
\hiersvr\svritem.cpp(106) : error C2664: 'void __pascal __far DPtoLP(struct ::tagPOINT __far *,
    int)__far const ' : cannot convert parameter 1 from 'int __far *' to 'struct ::tagPOINT __far *'
```

항목 크기 변환할 CServerItem::CalcNodeSize 함수의 **HIMETRIC** 에 저장 *m_rectBounds*합니다. 문서화 되지 않은 '*m_rectBounds*'의 멤버 `COleServerItem` 존재 하지 않습니다 (부분적으로 대체 되었습니다 *m_sizeExtent*, 되었지만 OLE 2에서이 멤버 보다약간다른사용량*m_rectBounds* OLE1에서). 설정 하는 대신 합니다 **HIMETRIC** 크기가 멤버 변수로에서는 반환 합니다. 반환 값이는 `OnGetExtent`, 이전에 구현 합니다.

```cpp
CSize CServerItem::CalcNodeSize()
{
    CClientDC dcScreen(NULL);

    m_sizeNode = dcScreen.GetTextExtent(m_strDescription,
        m_strDescription.GetLength());
    m_sizeNode += CSize(CX_INSET * 2, CY_INSET * 2);

    // set suggested HIMETRIC size
    CSize size(m_sizeNode.cx, m_sizeNode.cy);
    dcScreen.SetMapMode(MM_HIMETRIC);
    dcScreen.DPtoLP(&size);
    return size;
}
```

CServerItem 재정의 `COleServerItem::OnGetTextData`합니다. 이 함수는 MFC/OLE에서 사용 되지 않습니다 하 고 다른 메커니즘으로 대체 됩니다. MFC 3.0 버전의 MFC OLE 샘플 [HIERSVR](../overview/visual-cpp-samples.md) 재정의 하 여이 기능을 구현 `COleServerItem::OnRenderFileData`합니다. 이 기능은 OnGetTextData 재정의 제거할 수 있도록이 기본 포트에 대 한 중요 하지 않습니다.

많은 자세한 svritem.cpp 하는 오류를 해결 하지 않은 경우 "실제" 오류가 없는-이전 오류로 인해 발생 하는 오류 만으로 합니다.

```Output
\hiersvr\svrview.cpp(325) : error C2660: 'CopyToClipboard' : function does not take 2 parameters
```

`COleServerItem::CopyToClipboard` 더 이상 지원 하지는 `bIncludeNative` 플래그입니다. 원시 데이터 (서버 항목의 직렬화 함수에 의해 쓰여지는 데이터)는 첫 번째 매개 변수를 제거 하므로 항상 복사 됩니다. 또한 `CopyToClipboard` FALSE를 반환 하는 대신 오류가 발생 하면 예외가 throw 됩니다. CServerView::OnEditCopy에 대 한 코드를 다음과 같이 변경 합니다.

```cpp
void CServerView::OnEditCopy()
{
    if (m_pSelectedNode == NULL)
        AfxThrowNotSupportedException();

    TRY
    {
        m_pSelectedNode->CopyToClipboard(TRUE);
    }
    CATCH_ALL(e)
    {
        AfxMessageBox("Copy to clipboard failed");
    }
    END_CATCH_ALL
}
```

동일한 버전의 OCLIENT 있었습니다 보다 HIERSVR MFC 2.0 버전의 컴파일에서 결과 자세한 오류가 발생 하지만 개가 실제로 더 적은 변경 합니다.

이 시점에서 HIERSVR 컴파일 및 연결 하 고 구현 되는 전체 편집 기능을 하지 않고 OLE 서버로 작동 합니다.

## <a name="adding-visual-editing"></a>"비주얼 편집" 추가

"비주얼 편집" (또는 내부 활성화)이 서버 응용 프로그램에 추가 하려면 가지만 몇의 주의 해야 합니다.

- 항목은 전체 활성 때 사용 되는 특별 한 메뉴 리소스가 필요 합니다.

- 이 응용 프로그램 도구 모음, 있으므로 일반 도구 모음 메뉴 명령 서버에서 사용할 수 있습니다 (위에서 언급 한 메뉴 리소스와) 일치의 하위 집합만 사용 하 여 도구 모음을 사용 하도록 해야 합니다.

- 새 클래스에서 파생 해야 `COleIPFrameWnd` 전체 사용자 인터페이스를 제공 하는 (CMainFrame에서 파생 된 마찬가지로 `CMDIFrameWnd`, MDI 사용자 인터페이스를 제공).

- 이러한 특별 리소스 및 클래스에 대 한 프레임 워크를 입력 해야 합니다.

메뉴 리소스는 쉽게 만들 수 있습니다. 시각적 개체를 실행 C++, 메뉴 리소스 IDR_HIERSVRTYPE IDR_HIERSVRTYPE_SRVR_IP 라는 메뉴 리소스 복사 합니다. 편집 및 도움말 메뉴 팝업만 유지 됩니다 있도록 메뉴를 수정 합니다. 메뉴 편집 및 도움말 메뉴 사이 두 개의 구분 기호를 추가 (처럼 보여야 합니다. 편집 &#124; &#124; 도움말). 이러한 구분 기호 의미 서버 및 컨테이너 메뉴를 병합 하는 방법에 대 한 자세한 내용은 참조 하세요. [메뉴 및 리소스: 메뉴 병합](../mfc/menus-and-resources-menu-merging.md)입니다.

"서버" 옵션을 선택 하 여 새로 생성 하는 응용 프로그램 마법사에서 응용 프로그램에서 하나를 복사 하 여 하위 집합 도구 모음에 대 한 비트맵을 쉽게 만들 수 있습니다. 이 비트맵 시각적 개체로 가져올 수 있습니다 C++입니다. ID의 IDR_HIERSVRTYPE_SRVR_IP 비트맵을 제공 해야 합니다.

클래스에서 파생 된 `COleIPFrameWnd` server 지원 사용 하 여 생성 하는 응용 프로그램 마법사에서 응용 프로그램에서 복사할 수 있습니다. IPFRAME 두 파일을 복사 합니다. CPP 및 IPFRAME 합니다. H 프로젝트에 추가 합니다. 확인 된 `LoadBitmap` 호출 IDR_HIERSVRTYPE_SRVR_IP, 이전 단계에서 만든 비트맵을 가리킵니다.

이제 모든 새 리소스 및 클래스는를 만들었으므로 이러한 알고 (및이 응용 프로그램을 지금 바로 편집 기능을 지원 하는지 알고) 프레임 워크 있도록 필요한 코드를 추가 합니다. 몇 가지 자세한 매개 변수를 추가 하면 됩니다는 `SetServerInfo` 에서 호출 된 `InitInstance` 함수:

```cpp
pDocTemplate->SetServerInfo(IDR_HIERSVRTYPE_SRVR_EMB,
    IDR_HIERSVRTYPE_SRVR_IP,
    RUNTIME_CLASS(CInPlaceFrame));
```

전체를 실행할 준비가 되었습니다도 내부 활성화를 지 원하는 모든 컨테이너에서. 그러나 코드에서 아직 해결 한 사소한 버그 있습니다. HIERSVR은 마우스 오른쪽 단추를 누를 때 표시 되는 상황에 맞는 메뉴를 지원 합니다. 이 메뉴에는 HIERSVR 완전히 열려 포함 전체를 편집 하는 경우 작동 하지 않는 경우 작동 합니다. 이유는 CServerView::OnRButtonDown 코드의이 한 줄 고정할 수 있습니다.

```cpp
pMenu->TrackPopupMenu(TPM_CENTERALIGN | TPM_RIGHTBUTTON,
    point.x,
    point.y,
    AfxGetApp()->m_pMainWnd);
```

에 대 한 참조를 확인할 수 있습니다 `AfxGetApp()->m_pMainWnd`합니다. 서버가 활성화 될 때 주 창 및 m_pMainWnd 설정 되어 있으며 일반적으로 표시 되지 않습니다. 또한이 창 참조 하는 *주* 응용 프로그램의 창에서 서버를 완벽 하 게 하는 경우 표시 되는 MDI 프레임 창을 열거나 독립 실행형 실행 합니다. 활성 프레임이 창에는 나타내지 않습니다-때 현재 위치 활성화 되는 프레임 창에서 파생 된 `COleIPFrameWnd`합니다. 전체 편집,이 버전의 MFC는 새로운 함수를 추가 하는 경우에 올바른 활성 창에 가져오려는 `AfxGetMainWnd`합니다. 대신이 함수를 사용 해야 하는 일반적으로 `AfxGetApp()->m_pMainWnd`입니다. 이 코드는 다음과 같이 변경 해야 합니다.

```cpp
pMenu->TrackPopupMenu(TPM_CENTERALIGN | TPM_RIGHTBUTTON,
    point.x,
    point.y,
    AfxGetMainWnd());
```

이제 OLE 서버가 내부 활성화 기능에 대 한 최소한으로 사용 하도록 설정 해야 합니다. 하지만 여전히 여러 가지 기능 mfc/ole1에 사용할 수 없었던 MFC/OLE 2를 사용 하 여 사용할 수 있습니다. 구현 하려는 기능에 더 많은 아이디어 HIERSVR 예제를 참조 하세요. HIERSVR 구현 하는 기능 중 일부는 다음과 같습니다.

- 확대/축소, 컨테이너와 관련 하 여 true wysiwyg (위지윅) 동작에 대 한 합니다.

- 끌어서 놓기 및 사용자 지정 클립보드 형식입니다.

- 선택 항목으로 컨테이너 창을 스크롤하여 변경 됩니다.

MFC 3.0에서 HIERSVR 샘플은 또한 해당 서버 항목에 대해 약간 다른 디자인을 사용합니다. 이 메모리를 절약 하는 데 도움이 됩니다 및 보다 융통성 있는 링크를 만듭니다. HIERSVR의 2.0 버전을 사용 하 여 트리의 각 노드 *동등* `COleServerItem`합니다. `COleServerItem` 이러한 노드 각각에 대해 엄격 하 게 필요한 것 보다 좀 더 많은 오버 헤드가 수반 하지만 `COleServerItem` 각 활성 연결에 필요 합니다. 그러나 대부분의 경우 사항이 거의 활성 링크 언제 든 지 있습니다. 이 버전의 MFC에서 HIERSVR 더 효율적인이 위해에서 노드를 구분 합니다 `COleServerItem`합니다. 모두는 CServerNode 있기 및 `CServerItem` 클래스입니다. 합니다 `CServerItem` (에서 파생 된 `COleServerItem`) 필요에 따라 만들어집니다. 컨테이너 (또는 컨테이너)는 특정 노드에 특정 링크를 사용 하 여 중지 된 CServerNode 연관 CServerItem 개체 삭제 됩니다. 이 디자인에 더 효율적이 고 유연한은입니다. 여러 개의 선택 링크를 사용 하 여 처리 하는 경우 유연성 제공 됩니다. HIERSVR의 이러한 두 버전 모두에서 다중 선택을 지원 하지만 쉽게 추가할 (및 이러한 선택 항목에 대 한 링크를 지원 하기 위해) 것 HIERSVR, MFC 3.0 버전을 사용 하 여 이후는 `COleServerItem` 원시 데이터에서 구분 됩니다.

## <a name="see-also"></a>참고자료

[번호별 기술 참고 사항](../mfc/technical-notes-by-number.md)<br/>
[범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)
