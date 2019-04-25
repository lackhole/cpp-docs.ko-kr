---
title: 'TN071: MFC IOleCommandTarget 구현'
ms.date: 06/28/2018
f1_keywords:
- IOleCommandTarget
helpviewer_keywords:
- TN071 [MFC]
- IOleCommandTarget interface [MFC]
ms.assetid: 3eef571e-6357-444d-adbb-6f734a0c3161
ms.openlocfilehash: dca1183a17fe8f3022f517d1ad0c3932ea272417
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62168000"
---
# <a name="tn071-mfc-iolecommandtarget-implementation"></a>TN071: MFC IOleCommandTarget 구현

> [!NOTE]
> 다음 기술 노트는 온라인 설명서에 먼저 포함되어 있었으므로 업데이트되지 않았습니다. 따라서 일부 절차 및 항목은 만료되거나 올바르지 않을 수 있습니다. 최신 정보를 보려면 온라인 설명서 색인에서 관심 있는 항목을 검색하는 것이 좋습니다.

`IOleCommandTarget` 인터페이스에서 개체 및 해당 컨테이너 명령을 서로 수 있습니다. 예를 들어 개체의 도구 모음 포함 될 수 있습니다 명령에 대 한 단추와 같은 `Print`, `Print Preview`를 `Save`합니다 `New`, 및 `Zoom`합니다. 이러한 개체가 지 원하는 컨테이너에 포함 된 경우 `IOleCommandTarget`, 개체 수 해당 단추를 사용 하도록 설정 하 고 사용자를 클릭 하면 해당 처리에 대 한 컨테이너에 명령을 전달 합니다. 통해 명령을 전송 하 여이 요청을 만들 수는 컨테이너 자체를 인쇄 하려면 포함된 된 개체를 원하는 `IOleCommandTarget` 포함된 된 개체의 인터페이스입니다.

`IOleCommandTarget` 서버에서 메서드를 호출할 클라이언트에서 사용 되는 Automation 비슷한 인터페이스가입니다. 그러나 `IOleCommandTarget` 프로그래머는 일반적으로 비용이 많이 드는 데 없으므로 자동화 인터페이스를 통해 호출의 오버 헤드를 줄여 `Invoke` 메서드의 `IDispatch`합니다.

MFC에서는 `IOleCommandTarget` 인터페이스는 액티브 문서 서버에서 명령을 서버로 발송 하는 데 액티브 문서 컨테이너를 허용 하도록 사용 됩니다. 액티브 문서 서버 클래스 `CDocObjectServerItem`, MFC의 인터페이스 맵을 사용 하 여 (참조 [TN038: IUnknown 구현 MFC/OLE](../mfc/tn038-mfc-ole-iunknown-implementation.md))를 구현 하는 `IOleCommandTarget` 인터페이스입니다.

`IOleCommandTarget` 에서도 구현 됩니다는 `COleFrameHook` 클래스입니다. `COleFrameHook` 내부 편집 컨테이너의 프레임 창 기능을 구현 하는 문서화 되지 않은 MFC 클래스가입니다. `COleFrameHook` 또한 MFC 인터페이스 맵을 사용 하 여 구현 된 `IOleCommandTarget` 인터페이스입니다. `COleFrameHook`구현의 `IOleCommandTarget` OLE 명령을 전달 `COleDocObjectItem`-액티브 문서 컨테이너를 파생 합니다. 따라서 모든 MFC 액티브 문서 컨테이너를 포함 된 액티브 문서 서버에서 메시지를 받을 수 있습니다.

## <a name="mfc-ole-command-maps"></a>MFC OLE 명령 맵

MFC 개발자가 활용할 수 `IOleCommandTarget` 를 사용 하 여 MFC OLE maps 명령입니다. OLE 명령 맵 OLE 명령 명령 맵을 포함 하는 클래스의 멤버 함수에 매핑할 사용할 수 있으므로 메시지 맵 처럼 됩니다. 이 작업을 하려면 처리 하려는 명령, OLE 명령 및 명령 ID의 OLE 명령 그룹을 지정 하도록 명령 맵에서 매크로 추가 합니다 [WM_COMMAND](/windows/desktop/menurc/wm-command) OLE 명령의 받을 때 전송 될 메시지입니다. MFC는 또한 표준 OLE 명령에 대 한 다양 한 미리 정의 된 매크로 제공합니다. 표준 OLE 목록은 용으로 설계 된 원래 명령 Microsoft Office 응용 프로그램을 사용, docobj.h에 정의 되어 있는 OLECMDID 열거형을 참조 하세요.

OLE 명령 OLE 명령 지도 포함 하는 MFC 응용 프로그램에서 수신 되 면 MFC OLE 명령 맵의 응용 프로그램의 요청 된 명령에 대 한 명령 ID 및 명령 그룹을 찾으려고 합니다. 일치 하는 항목이 없으면 요청 된 명령 ID 사용 하 여 명령을 맵이 포함 된 응용 프로그램에 WM_COMMAND 메시지를 디스패치 됩니다. (설명을 참조 `ON_OLECMD` 아래.) 이러한 방식으로 응용 프로그램에 디스패치할 OLE 명령은 MFC에서 WM_COMMAND 메시지로 되어 있습니다. WM_COMMAND 메시지 MFC 표준을 사용 하 여 응용 프로그램의 메시지 맵을 통해 다음 라우팅됩니다 [명령 라우팅](../mfc/command-routing.md) 아키텍처입니다.

메시지 맵 달리 MFC OLE 명령 맵 classwizard 함께 사용 하 여 지원 되지 않습니다. MFC 개발자 OLE 명령 지도 지원 및 OLE 명령 맵 엔트리를 수동으로 추가 해야 합니다. OLE 명령 체인에 있는 WM_COMMAND 메시지 라우팅 시 활성 문서 클래스에서 MFC 액티브 문서 서버에 지도 추가할 수 있습니다에 컨테이너에 있는 전체 활성 상태입니다. 이러한 클래스에서 파생 된 응용 프로그램의 클래스를 포함 [CWinApp](../mfc/reference/cwinapp-class.md), [CView](../mfc/reference/cview-class.md)합니다 [CDocument](../mfc/reference/cdocument-class.md), 및 [COleIPFrameWnd](../mfc/reference/coleipframewnd-class.md)합니다. 액티브 문서 컨테이너에 OLE 명령 맵만 추가할 수 있습니다 합니다 [COleDocObjectItem](../mfc/reference/coledocobjectitem-class.md)-클래스를 파생 합니다. 또한 액티브 문서 컨테이너에 WM_COMMAND 메시지는만 디스패치되고를 메시지 맵에 `COleDocObjectItem`-클래스를 파생 합니다.

## <a name="ole-command-map-macros"></a>OLE 명령 맵 매크로

클래스에 명령 맵 기능을 추가 하려면 다음 매크로 사용 합니다.

```cpp
DECLARE_OLECMD_MAP ()
```

이 매크로 (일반적으로 헤더 파일)에 명령을 맵을 포함 하는 클래스의 클래스 선언에서 이동 합니다.

```cpp
BEGIN_OLECMD_MAP(theClass, baseClass)
```

*theClass*<br/>
명령 맵을 포함 하는 클래스의 이름입니다.

*baseClass*<br/>
명령 맵을 포함 하는 클래스의 기본 클래스의 이름입니다.

이 매크로 명령 맵의 시작을 표시 합니다. 명령 맵을 포함 하는 클래스의 구현 파일에서이 매크로 사용 합니다.

```
END_OLECMD_MAP()
```

이 매크로 명령 map의 끝을 표시합니다. 명령 맵을 포함 하는 클래스의 구현 파일에서이 매크로 사용 합니다. 이 매크로 BEGIN_OLECMD_MAP 매크로 항상 따라야 합니다.

```
ON_OLECMD(pguid, olecmdid, id)
```

*pguid*<br/>
OLE 명령의 명령 그룹의 GUID에 대 한 포인터입니다. 이 매개 변수가 **NULL** 표준 OLE 명령 그룹에 대 한 합니다.

*olecmdid*<br/>
호출할 명령의 OLE 명령 ID입니다.

*ID*<br/>
이 OLE 명령을 호출할 때 명령 맵이 포함 된 응용 프로그램에 보낼 WM_COMMAND 메시지의 ID입니다.

처리 하려는 OLE 명령에 대 한 항목을 추가 하려면 명령 구조의 ON_OLECMD 매크로 사용 합니다. OLE 명령 수신 되 면 이러한 지정된 된 WM_COMMAND 메시지 변환 되며 표준 MFC 명령 라우팅 아키텍처를 사용 하 여 응용 프로그램의 메시지 맵을 통해 라우팅됩니다.

## <a name="example"></a>예제

다음 예제에서는 OLE 명령 처리 기능을 처리 하도록 MFC 액티브 문서 서버를 추가 하는 방법을 보여 줍니다 합니다 [OLECMDID_PRINT](/windows/desktop/api/docobj/ne-docobj-olecmdid) OLE 명령입니다. 이 예제는 액티브 문서 서버는 MFC 응용 프로그램을 생성 하려면 응용 프로그램 마법사를 사용 하는 것을 가정 합니다.

1. 사용자 `CView`-파생 클래스의 헤더 파일을 클래스 선언에 DECLARE_OLECMD_MAP 매크로 추가 합니다.

    > [!NOTE]
    > 사용 된 `CView`-WM_COMMAND 메시지 라우팅 체인에 있는 활성 문서 서버의 클래스 중 하나 이기 때문에 클래스를 파생 합니다.

    ```cpp
    class CMyServerView : public CView
    {
    protected: // create from serialization only
        CMyServerView();
        DECLARE_DYNCREATE(CMyServerView)
        DECLARE_OLECMD_MAP()
        // . . .
    };
    ```

2. 구현 파일에는 `CView`-파생 클래스인 BEGIN_OLECMD_MAP 및 END_OLECMD_MAP 매크로 추가:

    ```cpp
    BEGIN_OLECMD_MAP(CMyServerView, CView)

    END_OLECMD_MAP()
    ```

3. 표준 OLE 인쇄 명령을 처리 하려면 추가 된 [ON_OLECMD](reference/message-map-macros-mfc.md#on_olecmd) 명령 맵에 표준 인쇄 명령에 대 한 OLE 명령 ID를 지정 하는 매크로 및 **ID_FILE_PRINT** WM_COMMAND id **ID_FILE_PRINT** 는 MFC 응용 프로그램 마법사에서 생성 된 응용 프로그램에서 인쇄 명령 ID를 사용 하는 표준.

    ```
    BEGIN_OLECMD_MAP(CMyServerView, CView)
        ON_OLECMD(NULL, OLECMDID_PRINT, ID_FILE_PRINT)
    END_OLECMD_MAP()
    ```

afxdocob.h를에 정의 된 표준 OLE 명령 매크로 중 수 사용할 ON_OLECMD 매크로 대신 때문에 **OLECMDID_PRINT** 표준 OLE 명령 ID입니다. ON_OLECMD_PRINT 매크로 위에 표시 된 ON_OLECMD 매크로와 동일한 작업을 수행 합니다.

컨테이너 응용 프로그램을이 서버를 전송 하는 경우는 **OLECMDID_PRINT** 서버를 통해 명령을 `IOleCommandTarget` 인터페이스, 명령 처리기를 인쇄 하는 MFC 응용 프로그램을 인쇄 서버, 서버에서 호출 됩니다. 위의 단계에서 추가한 인쇄 명령을 호출 하는 액티브 문서 컨테이너의 코드는 다음과 같이 보입니다.

```cpp
void CContainerCntrItem::DoOleCmd()
{
    IOleCommandTarget *pCmd = NULL;
    HRESULT hr = E_FAIL;
    OLECMD ocm={OLECMDID_PRINT, 0};

    hr = m_lpObject->QueryInterface(
        IID_IOleCommandTarget,reinterpret_cast<void**>(&pCmd));

    if (FAILED(hr))
        return;

    hr = pCmd->QueryStatus(NULL, 1, &ocm, NULL);

    if (SUCCEEDED(hr) && (ocm.cmdf& OLECMDF_ENABLED))
    {
        //Command is available and enabled so call it
        COleVariant vIn;
        COleVariant vOut;
        hr = pCmd->Exec(NULL, OLECMDID_PRINT,
            OLECMDEXECOPT_DODEFAULT, &vIn, &vOut);
        ASSERT(SUCCEEDED(hr));
    }
    pCmd->Release();
}
```

## <a name="see-also"></a>참고자료

[번호별 기술 참고 사항](../mfc/technical-notes-by-number.md)<br/>
[범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)
