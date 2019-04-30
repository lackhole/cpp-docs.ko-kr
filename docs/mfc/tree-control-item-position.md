---
title: 트리 컨트롤 항목 위치
ms.date: 11/04/2016
helpviewer_keywords:
- CTreeCtrl class [MFC], item position
- item position in tree controls
- tree controls [MFC], item position
- position, CTreeCtrl items
ms.assetid: cd264344-2cf9-4d90-9ea8-c6900b6f60e7
ms.openlocfilehash: 238cb40319d28a53592a594a72947f400720f935
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62392481"
---
# <a name="tree-control-item-position"></a>트리 컨트롤 항목 위치

트리 컨트롤에 항목이 추가 되 면 항목의 초기 위치로 설정 됩니다 ([CTreeCtrl](../mfc/reference/ctreectrl-class.md))를 사용 하 여는 `InsertItem` 멤버 함수입니다. 멤버 함수 호출 이후에 새 항목을 삽입 하는 항목의 핸들과 부모 항목의 핸들을 지정 합니다. 이러한 값 중 하나 또는 두 번째 핸들로 지정 된 부모의 자식 항목을 식별 해야 합니다. `TVI_FIRST`, `TVI_LAST`, 또는 `TVI_SORT`합니다.

때 `TVI_FIRST` 또는 `TVI_LAST` 지정 된 경우 트리 컨트롤 시작 또는 끝의 자식 항목의 지정 된 부모 항목의 목록에 새 항목을 배치 합니다. 때 `TVI_SORT` 지정 된 경우 트리 컨트롤 항목 레이블 텍스트를 기준으로 알파벳 순서에 자식 항목의 목록에 새 항목을 삽입 합니다.

호출 하 여 자식 항목의 부모 항목의 목록이 사전순에 추가할 수는 [SortChildren](../mfc/reference/ctreectrl-class.md#sortchildren) 멤버 함수입니다. 이 함수는 지정 된 부모 항목 으로부터 내림차순 자식 항목의 모든 수준 사전순으로 정렬 되는지 여부를 지정 하는 매개 변수를 포함 합니다.

합니다 [SortChildrenCB](../mfc/reference/ctreectrl-class.md#sortchildrencb) 멤버 함수를 사용 하면 사용자가 정의한 기준에 따라 자식 항목을 정렬할 수 있습니다. 이 함수를 호출 하는 경우 트리 컨트롤은 두 자식 항목의 상대 순서를 결정 해야 할 때마다 호출할 수 있는 응용 프로그램에서 정의 된 콜백 함수를 지정 합니다. 비교 되는 항목에 대 한 두 개의 32 비트 응용 프로그램 정의 값 및 호출 하는 경우를 지정 하는 세 번째 32 비트 값을 수신 하는 콜백 함수 `SortChildrenCB`합니다.

## <a name="see-also"></a>참고자료

[CTreeCtrl 사용](../mfc/using-ctreectrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
