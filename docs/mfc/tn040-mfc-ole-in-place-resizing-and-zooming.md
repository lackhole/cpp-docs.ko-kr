---
title: 'TN040: MFC OLE 내부 크기 조정 및 확대/축소'
ms.date: 11/04/2016
helpviewer_keywords:
- resizing in-place
- TN040
- zooming and in-place activation
- in-place activation, zooming and resizing
ms.assetid: 4d7859bd-0b2e-4254-be62-2735cecf02c6
ms.openlocfilehash: 9d5c87e6d5daff34a479ba61c0c275b48a8bba4d
ms.sourcegitcommit: 934cb53fa4cb59fea611bfeb9db110d8d6f7d165
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2019
ms.locfileid: "65611120"
---
# <a name="tn040-mfcole-in-place-resizing-and-zooming"></a>TN040: MFC/OLE 내부 크기 조정 및 확대/축소

> [!NOTE]
>  다음 기술 노트는 온라인 설명서에 먼저 포함되어 있었으므로 업데이트되지 않았습니다. 따라서 일부 절차 및 항목은 만료되거나 올바르지 않을 수 있습니다. 최신 정보를 보려면 온라인 설명서 색인에서 관심 있는 항목을 검색하는 것이 좋습니다.

이 내부 편집와 관련 된 문제 및 서버 올바른 확대/축소를 수행 및 하는 방법의 전체 크기 조정 설명 합니다. 내부 활성화를 사용 하 여 wysiwyg (위지윅) 개념은 해당 컨테이너에서 한 단계 더 가져오며 서버 서로 협력 하 고 특히 대부분의 OLE 사양이 동일한 방식으로 해석 합니다.

컨테이너 및 내부 활성화를 지 원하는 서버 간의 닫기 상호 작용으로 인해 유지 해야 하는 최종 사용자의 기대 사항이 있습니다.

- 프레젠테이션 표시 (에 그릴 메타 파일의 `COleServerItem::OnDraw` 재정의)는 정확히 같습니다 (한다는 편집 도구 표시 되지 않음)를 편집 하는 것에 대 한 그리기로 합니다.

- 컨테이너에 확대/축소 하는 경우 서버 창도 그래야 합니다!

- 컨테이너와 서버 모두 동일한 메트릭을 사용 하 여 편집에 대 한 개체에 표시 됩니다. 이 수에 따라 매핑 모드를 사용 하 여 의미 *논리* 인치당 픽셀-물리적 인치 당 픽셀 수를 디스플레이 장치에서 렌더링 하는 경우.

> [!NOTE]
>  내부 활성화 (연결 되지 않은) 포함 된 항목에만 적용, 확대/축소 포함 된 개체에만 적용 됩니다. 둘 다에서 Api를 보면 `COleServerDoc` 고 `COleServerItem` 확대/축소에 사용 되는 합니다. 이 디버거가 분리이 되며 이유는 연결 및 포함 된 항목에 대 한 유효한 함수만에 `COleServerItem` (이 통해 공용 구현을 할 수) 포함 된 개체에 대해서만 사용할 수 있는 함수에는 및를 `COleServerDoc` 클래스 (서버의 관점에서의 **문서** 포함 되어 있는).

대부분의 작업은 컨테이너의 확대/축소 비율에 유의 하 고 적절 하 게 편집 해당 인터페이스를 수정 해야 한다는 server 구현자에 배치 됩니다. 하지만 서버에서는 컨테이너를 사용 하는 확대/축소 비율을 확인 하는 방법

## <a name="mfc-support-for-zooming"></a>확대/축소에 대 한 MFC 지원

현재 확대/축소 비율을 호출 하 여 확인할 수 있습니다 `COleServerDoc::GetZoomFactor`합니다. 문서 전체 활성 없을 때이 호출 하면 항상 100% 확대/축소 비율 (또는 1:1 비율) 결과가 발생 합니다. 전체 활성 100% 이외의 반환 하는 동안 호출 합니다.

올바르게 확대/축소의 예로 MFC OLE 샘플을 참조 하세요 [HIERSVR](../overview/visual-cpp-samples.md)합니다. 텍스트를 표시 하 고 텍스트를 일반적으로 (힌트, 인쇄 규칙, 디자인 너비 및 높이 모든 중요 복잡 해질) 선형으로 확장 되지 않습니다 한다는 사실에 복잡 HIERSVR에서 확대/축소 합니다. 그러나 HIERSVR 올바르게 확대/축소를 구현 하는 것에 대 한 적절 한 참조 이며 따라서 MFC 자습서 [SCRIBBLE](../overview/visual-cpp-samples.md) (7 단계).

`COleServerDoc::GetZoomFactor` 다른 메트릭 사용할 수 있는 컨테이너 또는 구현에서의 수를 기준으로 확대/축소 비율을 결정 하 `COleServerItem` 고 `COleServerDoc` 클래스입니다. 즉, 현재 확대/축소 비율을 다음 수식에 의해 결정 됩니다.

```
Position Rectangle (PR) / Container Extent (CE)
```

위치 사각형 컨테이너에 의해 결정 됩니다. 내부 활성화 동안 서버에 반환 됩니다 때 `COleClientItem::OnGetItemPosition` 이라고 하며 서버를 호출 하는 컨테이너 때 업데이트 됩니다 `COleServerDoc::OnSetItemRects` (에 대 한 호출을 사용 하 여 `COleClientItem::SetItemRects`).

컨테이너 범위는 계산을 약간 더 복잡 합니다. 컨테이너에 호출 되는 경우 `COleServerItem::OnSetExtent` (에 대 한 호출을 사용 하 여 `COleClientItem::SetExtent`), 컨테이너 범위 논리 인치 당 픽셀 수를 기준으로 픽셀로 변환이 값이 됩니다. 컨테이너 (이 일반적으로 대/소문자) SetExtent를 호출 하지 않은 경우 컨테이너 범위에서 반환 되는 크기는 `COleServerItem::OnGetExtent`합니다. 따라서 컨테이너 SetExtent를 호출 하지 않은, 경우 프레임 워크를 가정는 경우 컨테이너는가 호출한 자연 스러운 범위의 100% (에서 반환 되는 값 `COleServerItem::GetExtent`). 또 다른 방법은 명시 된 프레임 워크는 컨테이너의 100% (더 이상, no less) 항목의 표시 하는 것으로 가정 합니다.

있지만 반드시 `COleServerItem::OnSetExtent` 및 `COleServerItem::OnGetExtent` 비슷한 이름의 항목의 동일한 특성을 조작 하지 않습니다. `OnSetExtent` 서버 개체의 표시 되는 (확대/축소 비율)에 관계 없이 컨테이너에서 알 수 있도록 호출 되 고 `OnGetExtent` 개체의 이상적인 크기를 결정 하는 컨테이너에 의해 호출 됩니다.

각 관련된 Api를 보면 명확 하 게 그림을 얻을 수 있습니다.

## <a name="coleserveritemongetextent"></a>COleServerItem::OnGetExtent

이 함수는 항목의 HIMETRIC 단위에서 "자연 스러운 크기"를 반환 해야 합니다. "기본 크기" 생각 하는 가장 좋은 방법은 인쇄할 때 나타나는 크기로 정의 방법은입니다. 여기에 반환 되는 크기는 흡사는 메타 파일에는 특정 항목에 대 한 상수는 특정 항목 내용에 대 한 상수입니다. 이 크기는 항목에 적용 되는 확대/축소 변경 되지 않습니다. 일반적으로 바뀌지 않는 컨테이너를 제공 하면 항목이 더 많거나 적은 공간이 호출 하 여 `OnSetExtent`입니다. 변경의 예로 컨테이너에서 보낸 마지막 범위를 기준으로 텍스트 래핑 없습니다 "여백" 기능을 사용 하 여 간단한 텍스트 편집기를 수 있습니다. 서버 아마도 시스템 레지스트리에 비트 OLEMISC_RECOMPOSEONRESIZE를 설정 해야 하는 서버를 변경 하는 경우 (이 옵션에 대 한 자세한 내용은 OLE SDK 설명서를 참조).

## <a name="coleserveritemonsetextent"></a>COleServerItem::OnSetExtent

이 함수는 컨테이너 "보다" 개체의 표시 되 면 호출 됩니다. 대부분의 컨테이너 호출 하지 않는다면이 전혀 합니다. 기본 구현에서 사용 되는 'm_sizeExtent' 컨테이너에서 받은 마지막 값을 저장 `COleServerDoc::GetZoomFactor` 위에서 설명한 컨테이너 범위 값을 계산 하는 경우.

## <a name="coleserverdoconsetitemrects"></a>COleServerDoc::OnSetItemRects

이 함수는 내부 활성 문서가 있는 경우에 호출 됩니다. 컨테이너의 항목 위치 또는 항목에 적용 되는 클리핑 업데이트 될 때 호출 됩니다. 위치 사각형, 위에서 설명한 것 처럼 제공 분자 확대/축소 비율 계산 합니다. 호출 하 여 항목 위치를 변경 하는 서버를 요청할 수 있습니다 `COleServerDoc::RequestPositionChange`합니다. 컨테이너를 호출 하 여이 요청에 응답 하지 않을 수도 `OnSetItemRects` (에 대 한 호출을 사용 하 여 `COleServerItem::SetItemRects`).

## <a name="coleserverdocondraw"></a>COleServerDoc::OnDraw

메타 파일의 재정의 하 여 만들어졌는지 실현 해야 `COleServerItem::OnDraw` 정확히 동일한 메타 파일을 현재 확대/축소 비율에 관계 없이 생성 합니다. 컨테이너 메타 파일을 적절 하 게 확장 됩니다. 이 중요 한 차이 뷰의 `OnDraw` 및 서버 항목의 `OnDraw`합니다. 확대/축소 하 여 보기 핸들을 만들기만 항목을 *가능한* 메타 파일 및 확대/축소 적절 한 작업을 수행 하는 컨테이너의 몫입니다.

구현을 사용 하는 서버에 올바르게 작동 하는지 확인 하는 가장 좋은 방법은 `COleServerDoc::GetZoomFactor` 문서가 현재 위치에서 활성화 하는 경우.

## <a name="mfc-support-for-in-place-resizing"></a>전체 크기를 조정 하는 것에 대 한 MFC 지원

MFC OLE 2 사양에 설명 된 대로 완벽 하 게 내부 크기 조정 인터페이스를 구현 합니다. 사용자 인터페이스에서 지원 되는 `COleResizeBar` 클래스, 사용자 지정 메시지 WM_SIZECHILD, 및에서이 메시지의 특별 한 처리가 `COleIPFrameWnd`합니다.

프레임 워크에서 제공 하는 것 보다이 메시지의 다른 처리를 구현할 수도 있습니다. 프레임 워크 전체 컨테이너까지 크기 조정의 결과 유지 위에서 설명한 대로-서버는 확대/축소 비율 변경에 응답 합니다. 모두 설정 하 여 컨테이너에 반응 하는 경우 컨테이너 범위 및 위치 사각형이 처리 하는 동안 해당 `COleClientItem::OnChangeItemPosition` (에 대 한 호출 결과로 호출 `COleServerDoc::RequestPositionChange`) 하면 전체 크기 조정에서 편집 "보다" 항목의 표시 창입니다. 처리 하는 동안 위치 사각형을 설정 하 여 컨테이너에 반응 하는 경우 `COleClientItem::OnChangeItemPosition`확대/축소 비율 변경 되 고 "확대 하거나 축소" 항목이 표시 됩니다,

서버는이 협상 과정 (어느 정도)을 제어할 수 있습니다. 예를 들어 스프레드시트 셀을 표시 더 많거나 적은 항목을 편집 하는 동안 사용자가 창의 크기 조정 진행 하도록 선택할 수 있습니다. word-processor 여백 "페이지" 창으로 동일 하 고 새 여백으로 텍스트를 다시 조정할 수 있도록 하도록 선택할 수 있습니다. 서버는이 자연스럽 게 범위를 변경 하 여 구현 (에서 반환 되는 크기 `COleServerItem::OnGetExtent`) 크기 조정 완료 되 면 합니다. 이렇게 하면 위치 사각형이 동일한 확대/축소 비율을 하지만 큰 결과 또는 더 작은 보기 영역을 같은 크기 만큼 변경 하는 컨테이너 정도입니다. 또한, 더 많거나 적은 문서에 표시 됩니다에서 생성 된 메타 파일 `OnDraw`합니다. 이 경우 문서 자체는 사용자의 보기 영역 대신 항목 크기가 조정 될 때 변경 됩니다.

사용자 지정 크기 조정 구현 하 고 제공한 사용자 인터페이스를 활용할 수 있습니다 `COleResizeBar` WM_SIZECHILD 메시지를 재정의 하 여 프로그램 `COleIPFrameWnd` 클래스입니다. WM_SIZECHILD의 세부 사항에 자세한 내용은 참조 [Technical Note 24](../mfc/tn024-mfc-defined-messages-and-resources.md)합니다.

## <a name="see-also"></a>참고자료

[번호별 기술 참고 사항](../mfc/technical-notes-by-number.md)<br/>
[범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)
