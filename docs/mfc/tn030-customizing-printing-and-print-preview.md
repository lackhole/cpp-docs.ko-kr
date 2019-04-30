---
title: 'TN030: 인쇄 및 인쇄 미리 보기 사용자 지정'
ms.date: 06/28/2018
f1_keywords:
- vc.print
helpviewer_keywords:
- TN030
- customizing printing and print preview
- printing [MFC], views
- printing views [MFC]
- print preview [MFC], customizing
ms.assetid: 32744697-c91c-41b6-9a12-b8ec01e0d438
ms.openlocfilehash: 09938c5cec2812998d5e76e15154754ad3ac3e0b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62305686"
---
# <a name="tn030-customizing-printing-and-print-preview"></a>TN030: 인쇄 및 인쇄 미리 보기 사용자 지정

> [!NOTE]
> 다음 기술 노트는 온라인 설명서에 먼저 포함되어 있었으므로 업데이트되지 않았습니다. 따라서 일부 절차 및 항목은 만료되거나 올바르지 않을 수 있습니다. 최신 정보를 보려면 온라인 설명서 색인에서 관심 있는 항목을 검색하는 것이 좋습니다.

이 참고 인쇄 및 인쇄 미리 보기를 사용자 지정 하는 프로세스를 설명 하 고 목적에 사용 되는 콜백 루틴에 대해 설명 합니다 `CView` 콜백 루틴 및 멤버 함수의 `CPreviewView`합니다.

## <a name="the-problem"></a>문제

MFC는 대부분의 인쇄에 대 한 완전 한 솔루션을 제공 하며 인쇄 미리 보기. 대부분의 경우 약간의 추가 코드에서는 뷰를 인쇄 하 고 미리 볼 수 있어야 합니다. 그러나 개발자의 중요 한 작업을 필요로 하는 인쇄를 최적화 하는 방법 되며 일부 응용 프로그램에서 인쇄 미리 보기 모드에 특정 사용자 인터페이스 요소를 추가 해야 합니다.

## <a name="efficient-printing"></a>효율적인 인쇄

표준 메서드를 사용 하 여 MFC 응용 프로그램을 인쇄 하는 경우 Windows는 메모리 내 메타 파일에 모든 인터페이스 GDI (Graphical Device) 출력 호출을 전달 합니다. 때 `EndPage` 는 호출 Windows 프린터 한 페이지를 인쇄 하는 데 필요한 각 실제 밴드에 한 번씩 메타 파일을 재생 합니다. 이 렌더링 하는 동안 GDI를 계속 해야 하는지 결정 하는 중단 절차 자주 쿼리 합니다. 일반적으로 중단 프로시저 사용자는 인쇄 대화 상자를 사용 하 여 인쇄 작업을 중단 될 수 있도록 처리할 메시지를 허용 합니다.

그러나 인쇄 프로세스를 느려질 수 있습니다. 응용 프로그램에서 인쇄를 표준 기술을 사용 하 여 수행할 수 있습니다 보다 더 빠르게 수 있어야 하면 수동 밴드를 구현 해야 합니다.

## <a name="print-banding"></a>밴드 인쇄

수동으로 대역 외, 하기 위해 다시 구현 해야 인쇄 루프는 `OnPrint` 페이지당 (대역 외) 마다 한 번씩 여러 번 호출 됩니다. 인쇄 루프에서 구현 되는 `OnFilePrint` viewprnt.cpp의 함수입니다. 프로그램 `CView`-파생 클래스인 인쇄 명령 처리에 대 한 메시지 맵 항목 인쇄 함수 호출 되도록이 함수를 오버 로드 합니다. 복사를 `OnFilePrint` 루틴 및 밴드를 구현 하는 인쇄 루프를 변경 합니다. 것 그리기 인쇄 페이지의 섹션에 따라 최적화할 수 있도록 줄무늬 사각형 인쇄 함수에 전달할 수도 있습니다.

둘째, 자주를 호출 해야 `QueryAbort` 밴드를 그리는 동안. 이 고, 그렇지 중단 프로시저를 호출 하지 않아도 됩니다 하 고 사용자가 인쇄 작업을 취소할 수 없습니다.

## <a name="print-preview-electronic-paper-with-user-interface"></a>인쇄 미리 보기: 사용자 인터페이스를 사용 하 여 전자 문서

인쇄 미리 보기를 기본적으로 변환 프린터의 에뮬레이션을 표시 합니다. 기본적으로 주 창의 클라이언트 영역 창 내에서 완벽 하 게 하나 또는 두 개의 페이지를 표시할 사용 됩니다. 사용자가 좀 더 자세히 보려는 페이지의 영역을 확대 수 있습니다. 추가 지원으로 미리 보기 모드에서 문서를 편집 하려면 사용자도 수 있습니다.

## <a name="customizing-print-preview"></a>인쇄 미리 보기를 사용자 지정

인쇄 미리 보기 수정의 측면 중 하나를 사용 하 여이 하나만 처리 합니다. 미리 보기 모드로 UI를 추가 합니다. 다른 수정 가능 하지만, 이러한 변경이이 토론의 범위를 벗어납니다.

## <a name="to-add-ui-to-the-preview-mode"></a>UI의 미리 보기 모드를 추가 하려면

1. 뷰 클래스를 파생 `CPreviewView`합니다.

2. 원하는 UI 측면에 대 한 명령 처리기를 추가 합니다.

3. 디스플레이에 보이는 측면을 추가 하는 경우 재정의 `OnDraw` 호출 후에 그리기를 수행 하 고 `CPreviewView::OnDraw`입니다.

## <a name="onfileprintpreview"></a>OnFilePrintPreview

인쇄 미리 보기에 대 한 명령 처리기입니다. 해당 기본 구현은 다음과 같습니다.

```cpp
void CView::OnFilePrintPreview()
{
    // In derived classes, implement special window handling here
    // Be sure to Unhook Frame Window close if hooked.

    // must not create this on the frame. Must outlive this function
    CPrintPreviewState* pState = new CPrintPreviewState;

    if (!DoPrintPreview(AFX_IDD_PREVIEW_TOOLBAR, this,
        RUNTIME_CLASS(CPreviewView), pState))
    {
        // In derived classes, reverse special window handling
        // here for Preview failure case

        TRACE0("Error: DoPrintPreview failed");
        AfxMessageBox(AFX_IDP_COMMAND_FAILURE);
        delete pState;  // preview failed to initialize, delete State now
    }
}
```

`DoPrintPreview` 응용 프로그램의 기본 창은 숨겨집니다. 컨트롤 막대, 상태 표시줄 같은 유지 될 수는 pState에 지정 하 여->*dwStates* 멤버 (이 비트 마스크와 비트 개별 컨트롤 막대 AFX_CONTROLBAR_MASK (AFX_IDW_MYBAR)에서 정의 된에 대 한). -> 창 pState*nIDMainPane* 는 자동으로 숨기 거 나 reshown 창입니다. `DoPrintPreview` 표준 미리 보기 UI에 대 한 단추 모음을 만듭니다. 특별 한 창을 처리에 필요한 경우 숨기 거 나 표시 하기 전에 수행 해야 하는 다른 windows 가령 `DoPrintPreview` 라고 합니다.

기본적으로 인쇄 미리 보기에는 다음이 완료 되 면 반환 컨트롤 막대 원래 상태로 표시 되도록 주 창 하 합니다. 특별 한 처리가 필요한 경우 재정의에서 수행할 수 해야 `EndPrintPreview`합니다. 경우 `DoPrintPreview` 실패도 특별 한 처리를 제공 합니다.

사용 하 여 DoPrintPreview 라고 합니다.

- 미리 보기 도구 모음에 대 한 대화 상자 템플릿의 리소스 ID입니다.

- 인쇄 미리 보기에 대 한 인쇄를 수행 하는 보기에 대 한 포인터입니다.

- 미리 보기 뷰 클래스의 런타임 클래스입니다. 이 DoPrintPreview에서 동적으로 생성 됩니다.

- CPrintPreviewState 포인터입니다. CPrintPreviewState 구조 (또는 응용 프로그램에 자세한 상태를 유지 해야 하는 경우 파생된 구조) 해야 하는 참고 *되지* 프레임에 만들어집니다. DoPrintPreview 모덜리스 이며 EndPrintPreview 호출 될 때까지이 구조에도 유지 되어야 합니다.

  > [!NOTE]
  > 인쇄 지원을 위한 개별 보기 또는 뷰 클래스를 필요한 경우 해당 개체에 대 한 포인터는 두 번째 매개 변수로 전달 되어야 합니다.

## <a name="endprintpreview"></a>EndPrintPreview

인쇄 미리 보기 모드를 종료 하는이 호출 됩니다. 마지막으로 인쇄 미리 보기에 표시 된 문서의 페이지로 이동 하는 것이 좋습니다. `EndPrintPreview` 이렇게 하려면 응용 프로그램의 가능성이 높습니다. ->는 pInfo*m_nCurPage* 멤버는 마지막 (가장 왼쪽에 있는 두 페이지가 표시 된 경우)에 표시 된 페이지가 고 포인터가 있는 페이지의 사용자와 관련에 관한 힌트입니다. 아니므로 응용 프로그램의 보기의 구조는 프레임 워크에 알려진 선택한 지점으로 이동 하는 코드를 제공 해야 합니다.

대부분의 동작 호출 하기 전에 수행 해야 `CView::EndPrintPreview`합니다. 이 호출의 결과 반대로 바꿉니다. `DoPrintPreview` pView, pDC 및 pInfo 삭제 합니다.

```cpp
// Any further cleanup should be done here.
CView::EndPrintPreview(pDC, pInfo, point, pView);
```

## <a name="cwinapponfileprintsetup"></a>CWinApp::OnFilePrintSetup

이 인쇄 설정 메뉴 항목에 매핑해야 합니다. 대부분의 경우에서 구현을 재정의 하는 데 필요한 아닙니다.

## <a name="page-nomenclature"></a>페이지 용어 체계

또 다른 문제는 페이지 번호 매기기 및 순서입니다. 간단한 워드 프로세서 유형 응용 프로그램에서 간단한 문제입니다. 대부분의 인쇄 미리 보기 시스템 문서의 한 페이지에 인쇄 된 페이지 마다 해당 가정 합니다.

일반화 된 솔루션을 제공 하는 동안에서 고려해 야 할 몇 가지 사항이 있습니다. CAD 시스템을 가정해 보겠습니다. 사용자는 여러 전자 크기 시트를 포함 하는 그리기를 갖습니다. E-크기가 하 여 (또는 보다 작은, 확장) 간단한 경우와 같이 플로터, 페이지 번호 매기기 것입니다. 아니지만 시트 당 16 크기는 페이지를 인쇄 레이저 프린터에서 새로운 인쇄 미리 보기 "페이지"를

소개 문단에서 알 수 있듯이 인쇄 미리 보기는 프린터와 같은 역할을 하 합니다. 따라서 사용자는 선택한 특정 프린터 나오는 새로운 표시 됩니다. 뷰에서 이미지는 각 페이지에 인쇄 됩니다.

페이지 설명 문자열을 `CPrintInfo` 페이지당 하나의 수로 나타낼 수 있는 경우 사용자에 게 페이지 번호를 표시 하는 수단을 제공 하는 구조 ("1 페이지"와 같이 또는 "페이지 1-2"). 이 문자열은의 기본 구현에 의해 사용 `CPreviewView::OnDisplayPageNumber`합니다. 다른 디스플레이 필요한 경우에 예를 들어, "Sheet1 섹션 A, B"를 제공 하려면이 가상 함수를 재정의할 수 있습니다 하나.

## <a name="see-also"></a>참고자료

[번호별 기술 참고 사항](../mfc/technical-notes-by-number.md)<br/>
[범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)
