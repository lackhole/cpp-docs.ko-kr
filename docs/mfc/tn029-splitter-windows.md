---
title: 'TN029: 분할 창'
ms.date: 11/04/2016
f1_keywords:
- vc.windows.splitter
helpviewer_keywords:
- TN029
- splitter windows [MFC], about splitter windows
ms.assetid: 2c57ce99-2a3c-4eff-9cea-baccb13af075
ms.openlocfilehash: 6c2f619d9cd619ca598c66ca657faa1b9dccaaa2
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58781733"
---
# <a name="tn029-splitter-windows"></a>TN029: 분할 창

이 여기서 설명 MFC [CSplitterWnd 클래스](../mfc/reference/csplitterwnd-class.md), 분할 창과 다른 창 창의 크기 조정 관리를 제공 하는 합니다.

## <a name="splitter-styles"></a>분할자 스타일

`CSplitterWnd` windows 분할의 두 가지 다른 스타일을 지원 합니다.

"정적 분할 창 에서는" 분할 창 만들어질 때 창을 만듭니다. 순서 및 창 수를 변경 되지 않습니다. 분할 막대의 다양 한 창 크기를 조정 하는 데 사용 됩니다. 각 창에 서로 다른 뷰 클래스를 표시 하려면이 스타일을 사용할 수 있습니다. Visual c + + 그래픽 편집기 및 Windows 파일 관리자는이 분할자 스타일을 사용 하는 프로그램의 예입니다. 이 스타일 분할자 창 분할기 상자를 사용 하지 않습니다.

"동적 분할 창 에서는" 추가 창이 만들어지고 사용자 분할 및 분할 취소 새 뷰를 제거 합니다. 이 분할기 단일 보기를 시작 하 고 분할을 시작 하려면 사용자에 대 한 분할 상자를 제공 합니다. 분할기 창 뷰는 한 방향으로 분할 될 때 동적으로 새 뷰 개체를 만듭니다. 이 새 뷰 개체를 새 창을 나타냅니다. 두 방향에서 키보드 인터페이스를 사용 하 여 뷰를 분할 하는 경우 분할 창 있는 세 개의 새 창에 대 한 3 개의 새 뷰 개체를 만듭니다. 분할 활성 상태인 동안 Windows 창 사이 분할 막대로 분할자 상자를 표시 합니다. Windows 사용자는 분할 제거 있지만 분할자 창 자체 될 때까지 원래 뷰를 그대로 유지 됩니다는 손상 추가 뷰 개체를 제거 합니다. Microsoft Excel 및 Microsoft Word은 동적 분할 스타일을 사용 하는 응용 프로그램의 예입니다.

두 종류의 분할 창을 만들 때 최대 분할자는 관리 되는 행과 열을 지정 해야 합니다. 정적 분할의 행과 열 모두에 맞게 창을 만듭니다. 동적 분할만 첫 번째 창 만들어집니다 때는 `CSplitterWnd` 만들어집니다.

정적 분할 창에 지정할 수 있는 창의 최대 수는 16 16 개의 열을 행 합니다. 권장된 구성은 다음과 같습니다.

- 1 개 행 x 2 열: 서로 다른 창을 사용 하 여 일반적으로

- 열 2 행 x 1: 서로 다른 창을 사용 하 여 일반적으로

- 열 2 행 x 2: 유사한 창을 사용 하 여 일반적으로

동적 분할 창에 대해 지정할 수 있는 창의 최대 수는 2 열을 기준으로 2 개 행입니다. 권장된 구성은 다음과 같습니다.

- 1 개 행 x 2 열: 칼럼 형식 데이터에 대 한

- 열 2 행 x 1: 텍스트 또는 기타 데이터에 대 한

- 열 2 행 x 2: 표 또는 테이블에 대 한 데이터 지향

## <a name="splitter-examples"></a>분할 예제

MFC 샘플 프로그램의 대부분 직접 또는 간접적으로 분할자 창을 사용합니다. MFC 일반 샘플 [VIEWEX](../overview/visual-cpp-samples.md) 정적 분할자, 분할자 분할자에 배치 하는 방법 등의 몇 가지 사용 방법을 보여 줍니다.

또한 여러 문서 MDI (인터페이스) 자식 프레임 창 클래스는 분할자 창을 포함 하는 새 만들려면 클래스 마법사를 사용할 수 있습니다. 분할 창에 대 한 자세한 내용은 참조 하세요. [여러 문서 형식, 뷰 및 프레임 Windows](../mfc/multiple-document-types-views-and-frame-windows.md)합니다.

## <a name="terminology-used-by-implementation"></a>구현에서 사용 되는 용어

분할 창 관련이 있는 용어 목록은 다음과 같습니다.

`CSplitterWnd`: 창 분할 컨트롤 및 모든 창 행 또는 열 간에 공유 되는 스크롤 막대를 제공 하는 창입니다. 0부터 시작 숫자를 사용 하 여 행 및 열을 지정 (첫 번째 창에 행이 = 0, 열 = 0).

창: 응용 프로그램별 창 하는 `CSplitterWnd` 관리 합니다. 창에서 파생 된 개체는 일반적으로 [CView 클래스](../mfc/reference/cview-class.md), 모든 수 있지만 [CWnd](../mfc/reference/cwnd-class.md) 적절 한 자식 창 ID를 가진 개체를

사용 하는 `CWnd`-파생 개체를 개체의 RUNTIME_CLASS 전달를 `CreateView` 함수를 사용한 경우 처럼를 `CView`-파생 클래스. 클래스는 프레임 워크 런타임 시 동적 생성을 사용 하기 때문에 DECLARE_DYNCREATE 및 IMPLEMENT_DYNCREATE 사용 해야 합니다. 코드를 많이 있지만 `CSplitterWnd` 에 고유 합니다 `CView` 클래스 [CObject::IsKindOf](../mfc/reference/cobject-class.md#iskindof) 이러한 작업을 수행 하기 전에 항상 사용 됩니다.

분할 막대: 컨트롤 창의 행과 열 사이 배치 됩니다. 이 창의 열 또는 행의 크기를 조정 하려면 사용할 수 있습니다.

분할자 상자: 동적 컨트롤을 `CSplitterWnd` 는 창의 새 행 또는 열을 만드는 데 사용할 수 있습니다. 세로 스크롤 막대 또는 가로 스크롤 막대의 왼쪽에 위쪽에 있는 경우

분할자 교집합: 세로 분할 막대와 가로 분할 막대의 교집합입니다. 동시에 행 및 열 창의 크기를 조정 하려면 끌 수 있습니다.

## <a name="shared-scroll-bars"></a>공유 스크롤 막대

`CSplitterWnd` 클래스도 공유 스크롤 막대를 지원 합니다. 이러한 스크롤 막대 컨트롤의 자식인는 `CSplitterWnd` 분할자에 서로 다른 창을 공유 됩니다.

예를 들어, 1 개 행 x 2 열 창에서 지정할 수 있습니다 WS_VSCROLL 만들면는 `CSplitterWnd`합니다. Windows에는 두 개의 창이 간에 공유 되는 특별 한 스크롤 막대 컨트롤을 만듭니다.

```
[      ][      ][^]
[pane00][pane01][|]
[      ][      ][v]
```

사용자가 스크롤 막대를 움직이면 WM_VSCROLL 메시지 모두 보기에 보내집니다. 뷰 스크롤 막대 위치를 설정 하면 공유 스크롤 막대 설정 됩니다.

공유 스크롤 막대는 유사한 뷰 개체를 사용 하 여 가장 유용한 note 합니다. 분할자의 형식이 서로 다른 뷰를 혼합 하면 스크롤 위치를 조정 하기 위해 특별 한 코드를 작성 해야 있습니다. 모든 `CView`-파생 클래스를 사용 하 여 `CWnd` 스크롤 막대가 있는 경우 Api 공유 스크롤 막대를 위임 합니다. 합니다 `CScrollView` 구현은의 예로 `CView` 지 원하는 클래스는 스크롤 막대를 공유 합니다. 클래스에서 파생 되지 않은 `CView`, 컨트롤이 아닌 스크롤 막대를 사용 하는 클래스 또는 표준 Windows 구현을 사용 하는 클래스 (예를 들어 `CEditView`)의 공유 스크롤 막대 기능을 통해 작동 하지 것입니다 `CSplitterWnd`합니다.

## <a name="minimum-sizes"></a>최소 크기

각 행에 대해 최소 행 높이 되며 각 열에는 최소 열 너비입니다. 이 최소는 창이 너무 작아서 전체 세부 정보에 표시 되지 않으면 보장 합니다.

정적 분할 창은, 초기 최소 행 높이 및 열 너비는 0입니다. 동적 분할 창 초기 최소 행 높이 및 열 너비를 설정 합니다 *sizeMin* 의 매개 변수는 `CSplitterWnd::Create` 함수.

사용 하 여 이러한 최소 크기를 변경할 수 있습니다 합니다 [CSplitterWnd::SetRowInfo](../mfc/reference/csplitterwnd-class.md#setrowinfo) 하 고 [CSplitterWnd::SetColumnInfo](../mfc/reference/csplitterwnd-class.md#setcolumninfo) 함수입니다.

## <a name="actual-vs-ideal-sizes"></a>실제 및 이상적인 크기

분할기 창에서 창 레이아웃은 포함 된 프레임의 크기에 따라 달라 집니다. 사용자를 포함 하는 프레임의 크기를 조정 하는 경우는 `CSplitterWnd` 위치를 변경 하 고 가능한 저장할 수 있도록 창 크기를 조정 합니다.

수동으로 설정 하면 행 높이 및 열 너비 크기 또는 프로그램을 사용 하 여 이상적인 크기를 설정할 수는 `CSplitterWnd` 클래스입니다. 실제 크기는 이상적인 보다 크거나 작을 수 있습니다. 공간이 부족 하 여 이상적인 크기를 표시 하지 않은 경우 또는 분할자 창 맨 오른쪽에 빈 공간이 너무 많은 경우 Windows에서 실제 크기를 조정 됩니다.

## <a name="custom-controls"></a>사용자 지정 컨트롤

사용자 지정 된 동작 및 사용자 지정된 인터페이스를 제공 하기 위해 여러 함수를 재정의할 수 있습니다. 분할기 창에 다양 한 그래픽 구성 요소에 대 한 대체 이미지를 제공 합니다.이 첫 번째 집합을 재정의할 수 있습니다.

- `virtual void OnDrawSpltter(CDC* pDC, ESplitType nType, const CRect& rect);`

- `virtual void OnInvertTracker(const CRect& rect);`

공유 scroll bar 컨트롤을 만들려면이 함수를 호출 합니다. 스크롤 막대 옆에 있는 추가 컨트롤을 만드는 데이 재정의할 수 있습니다.

- `virtual BOOL CreateScrollBarCtrl(DWORD dwStyle, UINT nID);`

이러한 함수는 동적 분할 창은의 논리를 구현 합니다. 고급 분할 논리를 제공 하도록이 재정의할 수 있습니다.

- `virtual void DeleteView(int row, int col);`

- `virtual BOOL SplitRow(int cyBefore);`

- `virtual BOOL SplitColumn(int cxBefore);`

- `virtual void DeleteRow(int rowDelete);`

- `virtual void DeleteColumn(int colDelete);`

## <a name="cview-functionality"></a>CView 기능

`CView` 클래스에 대 한 위임 높은 수준의 명령을 사용 합니다 `CSplitterWnd` 구현 합니다. 이러한 명령은 가상 있기 때문에 표준 `CView` 구현에는 전체를 사용 해야 합니다. `CSplitterWnd` 구현을 연결할 수 있습니다. 사용 하는 응용 프로그램에 대 한 `CView` 있지만 `CSplitterWnd`는 `CSplitterWnd` 구현 응용 프로그램과 연결 되지 것입니다.

- `virtual BOOL CanActivateNext(BOOL bPrev = FALSE);`

   ID_NEXT_PANE 또는 ID_PREV_PANE 현재 가능한 지 여부를 확인 합니다.

- `virtual void ActivateNext(BOOL bPrev = FALSE);`

   "다음 창" 또는 "이전 창" 명령을 실행합니다.

- `virtual BOOL DoKeyboardSplit();`

   키보드 분할 명령을, 일반적으로 "창 분할"을 실행 합니다.

## <a name="see-also"></a>참고자료

[번호별 기술 참고 사항](../mfc/technical-notes-by-number.md)<br/>
[범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)
