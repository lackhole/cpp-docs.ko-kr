---
title: 액티브 문서
ms.date: 11/04/2016
helpviewer_keywords:
- active documents [MFC]
- active documents [MFC], requirements
- view objects [MFC], requirements
- OLE [MFC], active documents
- views [MFC], active documents
- active documents [MFC], views
ms.assetid: 1378f18e-aaa6-420b-8501-4b974905baa0
ms.openlocfilehash: 519dd51ab9b46adf862999104e97c6e478ccd86b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62394951"
---
# <a name="active-documents"></a>액티브 문서

액티브 문서는 OLE의 복합 문서 기술을 확장합니다. 이러한 확장은 보기를 관리하는 추가 인터페이스의 형태로 제공되므로, 개체가 컨테이너 내에서 작동하면서 해당 표시 및 인쇄 기능에 대한 제어를 계속 유지할 수 있습니다. 이 프로세스는 외부 프레임(예: Microsoft Office Binder 또는 Microsoft Internet Explorer) 및 고유 프레임(예: 제품의 고유 보기 포트)에서 문서를 표시할 수 있게 해줍니다.

이 섹션에서는 기능 설명 [액티브 문서의 요구 사항](#requirements_for_active_documents)합니다. 액티브 문서는 데이터 집합을 소유하고 데이터를 저장 및 검색할 수 있는 저장소에 대한 액세스 권한을 갖습니다. 액티브 문서는 해당 데이터에 대해 하나 이상의 보기를 만들고 관리할 수 있습니다. OLE 문서에 대해 일반적인 포함 및 현재 위치 활성화 인터페이스를 지원하는 것 외에도, 액티브 문서는 해당 기능을 통신하여 `IOleDocument`를 통해 보기를 만듭니다. 이 인터페이스를 통해 컨테이너는 액티브 문서가 표시할 수 있는 보기를 만들도록(그리고 가능한 경우 열거하도록) 요청할 수 있습니다. 이 인터페이스를 통해 액티브 문서는 다중 뷰 또는 복합 사각형 지원 여부와 같은 자체에 대한 여러 정보도 제공할 수 있습니다.

다음은는 `IOleDocument` 인터페이스입니다. 유의 합니다 `IEnumOleDocumentViews` 인터페이스에 대 한 표준 OLE 열거자는 `IOleDocumentView*` 형식입니다.

```
interface IOleDocument : IUnknown
    {
    HRESULT CreateView(
        [in] IOleInPlaceSite *pIPSite,
        [in] IStream *pstm,
        [in] DWORD dwReserved,
        [out] IOleDocumentView **ppView);

    HRESULT GetDocMiscStatus([out] DWORD *pdwStatus);

    HRESULT EnumViews(
        [out] IEnumOleDocumentViews **ppEnum,
        [out] IOleDocumentView **ppView);
    }
```

모든 액티브 문서는 이 인터페이스를 지원하는 보기 프레임 공급자가 있어야 합니다. 문서가 컨테이너 내에 포함되어 있지 않으면 액티브 문서 서버 자체에서 보기 프레임을 제공해야 합니다. 하지만 액티브 문서가 액티브 문서 컨테이너에 포함되어 있으면 컨테이너가 보기 프레임을 제공합니다.

활성 문서에는 하나 이상의 유형을 만들 수 [뷰](#requirements_for_view_objects) 데이터 (예를 들어, 보통, 개요, 레이아웃 페이지 및 등). 보기는 데이터를 볼 수 있는 필터처럼 작동합니다. 문서에 보기 유형이 하나만 있는 경우에 새로운 창 기능을 지 원하는 방식으로 여러 뷰를 지원 하려는 여전히 (예를 들어 합니다 **새 창** 항목는 **창** office에서 메뉴 응용 프로그램)입니다.

##  <a name="requirements_for_active_documents"></a> 활성 문서에 대 한 요구 사항

액티브 문서 컨테이너에 표시할 수 있는 액티브 문서의 요구 사항은 다음과 같습니다.

- `IPersistStorage`를 구현하여 OLE의 복합 파일을 저장 메커니즘으로 사용해야 합니다.

- OLE 포함 한 문서의 기본 포함 기능을 지 원하는 **파일에서 만들기**합니다. 이를 위해서는 `IPersistFile`, `IOleObject` 및 `IDataObject` 인터페이스가 필요합니다.

- 현재 위치 활성화가 가능한 하나 이상의 보기를 지원해야 합니다. 즉, 뷰 인터페이스를 지원 해야 합니다 `IOleDocumentView` 인터페이스 뿐만 아니라 `IOleInPlaceObject` 및 `IOleInPlaceActiveObject` (컨테이너의를 사용 하 여 `IOleInPlaceSite` 및 `IOleInPlaceFrame` 인터페이스).

- 표준 액티브 문서 인터페이스 `IOleDocument`, `IOleCommandTarget` 및 `IPrint`를 지원해야 합니다.

컨테이너 쪽 인터페이스를 사용하는 경우 및 방법에 대한 지식은 이러한 요구 사항에 암시적으로 포함됩니다.

##  <a name="requirements_for_view_objects"></a> 뷰 개체에 대 한 요구 사항

액티브 문서는 해당 데이터에 대해 하나 이상의 보기를 만들 수 있습니다. 기능적으로 이러한 보기는 데이터를 표시하기 위해 특정 메서드로 가는 포트와 비슷합니다. 액티브 문서가 단일 보기만 지원하는 경우 액티브 문서 및 해당 단일 보기는 단일 클래스를 사용해서 구현할 수 있습니다. `IOleDocument::CreateView` 동일한 개체를 반환 `IOleDocumentView` 인터페이스 포인터입니다.

액티브 문서 컨테이너 내에 나타내야, 뷰 구성 요소를 지원 해야 합니다 `IOleInPlaceObject` 하 고 `IOleInPlaceActiveObject` 외에 `IOleDocumentView`:

```
interface IOleDocumentView : IUnknown
    {
    HRESULT SetInPlaceSite([in] IOleInPlaceSite *pIPSite);
    HRESULT GetInPlaceSite([out] IOleInPlaceSite **ppIPSite);
    HRESULT GetDocument([out] IUnknown **ppunk);
    [input_sync] HRESULT SetRect([in] LPRECT prcView);
    HRESULT GetRect([in] LPRECT prcView);
    [input_sync] HRESULT SetRectComplex(
        [in] LPRECT prcView,
        [in] LPRECT prcHScroll,
        [in] LPRECT prcVScroll,
        [in] LPRECT prcSizeBox);
    HRESULT Show([in] BOOL fShow);
    HRESULT UIActivate([in] BOOL fUIActivate);
    HRESULT Open(void);
    HRESULT CloseView([in] DWORD dwReserved);
    HRESULT SaveViewState([in] IStream *pstm);
    HRESULT ApplyViewState([in] IStream *pstm);
    HRESULT Clone(
        [in] IOleInPlaceSite *pIPSiteNew,
        [out] IOleDocumentView **ppViewNew);
    }
```

모든 보기에는 보기 프레임 및 보기 포트(HWND 및 해당 창의 사각형 영역)를 캡슐화하는 연관된 보기 사이트가 포함됩니다. 사이트에서는 이러한 기능 제공 하지만 표준 `IOleInPlaceSite` 인터페이스입니다. 단일 HWND에서는 두 개 이상의 보기 포트를 가질 수 있습니다.

일반적을 각 보기 유형에는 서로 다른 인쇄된 표현이 포함됩니다. 따라서 보기 및 해당 보기 사이트는 인쇄 인터페이스 `IPrint` 및 `IContinueCallback`을 각각 구현해야 합니다. 보기 프레임을 통해 보기 공급자와 협상 해야 `IPrint` 인쇄가 시작 될 때, 머리글, 바닥글, 여백 및 관련된 요소가 올바르게 인쇄 되도록 합니다. 보기 공급자는 프레임에 `IContinueCallback`을 통해 인쇄 관련 이벤트를 알립니다. 이러한 인터페이스의 사용에 자세한 내용은 참조 하세요. [프로그래밍 방식 인쇄](../mfc/programmatic-printing.md)합니다.

액티브 문서에서 단일 보기만 지원될 경우에는 하나의 구체적 클래스를 사용해서 액티브 문서 및 해당 단일 보기를 구현할 수 있습니다. `IOleDocument::CreateView` 단순히 동일한 개체를 반환 `IOleDocumentView` 인터페이스 포인터입니다. 간단히 말해서, 보기가 하나만 필요할 때는 별도의 개체 인스턴스가 두 개 있을 필요가 없습니다.

또한 보기 개체는 명령 대상일 수 있습니다. 구현 하 여 `IOleCommandTarget` 뷰는 컨테이너의 사용자 인터페이스에서 발생 하는 명령을 받을 수 있습니다 (같은 **새로 만들기**, **열기**, **이름으로 저장**,  **인쇄** 에 **파일** 메뉴 및 **복사**를 **붙여넣기**, **취소** 에 **편집** 메뉴). 자세한 내용은 [메시지 처리 및 명령 대상](../mfc/message-handling-and-command-targets.md)합니다.

## <a name="see-also"></a>참고자료

[활성 문서 포함](../mfc/active-document-containment.md)
