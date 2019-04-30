---
title: '방법: 빠른 실행 도구 모음 사용자 지정'
ms.date: 11/19/2018
helpviewer_keywords:
- quick access toolbar [MFC], customization
ms.assetid: 2554099b-0c89-4605-9249-31bf9cbcefe0
ms.openlocfilehash: c53e405eafe310c0bfc03a916ab85181ae67a34b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62396436"
---
# <a name="how-to-customize-the-quick-access-toolbar"></a>방법: 빠른 실행 도구 모음 사용자 지정

QAT(빠른 실행 도구 모음)는 응용 프로그램 단추 옆 또는 범주 탭 아래에 표시된 명령 집합이 포함된 사용자 지정 가능한 도구 모음입니다. 다음 그림에서는 일반적인 빠른 실행 도구 모음을 보여 줍니다.

![MFC 리본 빠른 실행 도구 모음](../mfc/media/quick_access_toolbar.png "MFC 리본 빠른 실행 도구 모음")

빠른 실행 도구 모음을 사용자 지정 하려면 열에 **속성** 창에서 해당 명령을 수정한 다음 리본 컨트롤을 미리 봅니다.

### <a name="to-open-the-quick-access-toolbar-in-the-properties-window"></a>속성 창에서 빠른 실행 도구 모음을 열려면

1. Visual Studio에서에 **뷰** 메뉴에서 클릭 **리소스 뷰**합니다.

1. **리소스 뷰**, 디자인 화면에 표시할 리본 리소스를 두 번 클릭 합니다.

1. 디자인 화면에서 빠른 실행 도구 모음 메뉴를 마우스 오른쪽 단추로 클릭 하 고 클릭 **속성**합니다.

## <a name="quick-access-toolbar-properties"></a>빠른 실행 도구 모음 속성

다음 표에서는 빠른 실행 도구 모음의 속성을 정의합니다.

|속성|정의|
|--------------|----------------|
|QAT 위치|응용 프로그램이 시작될 때 빠른 실행 도구 모음의 위치를 지정합니다. 위치 일 수 있습니다 **위에** 하거나 **아래** 리본 컨트롤입니다.|
|QAT 항목|빠른 실행 도구 모음에 사용할 수 있는 명령을 지정합니다.|

#### <a name="to-add-or-remove-commands-on-the-quick-access-toolbar"></a>빠른 실행 도구 모음에서 명령을 추가 또는 제거하려면

1. 에 **속성** 창에서 클릭 **QAT 항목**, 줄임표 단추를 클릭 하 고 **(...)** .

1. 에 **QAT 항목 편집기** 대화 상자를 사용 하 여는 **추가** 하 고 **제거** 빠른 실행 도구 모음에서 명령의 목록을 수정 하려면 단추.

1. 빠른 실행 도구 모음과 빠른 실행 도구 모음 메뉴 모두에 나타나는 명령을 원하는 경우 명령 옆의 상자를 선택하십시오. 메뉴에만 명령을 표시하려면 상자 선택을 취소합니다.

## <a name="previewing-the-ribbon"></a>리본 미리 보기

디자인 화면에 빠른 실행 도구 모음 명령이 나타나지 않습니다. 해당 명령을 보려면 리본을 미리 보거나 응용 프로그램을 실행해야 합니다.

#### <a name="to-preview-the-ribbon-control"></a>리본 컨트롤을 미리 보려면

- 에 **Ribbon 편집기 도구 모음**, 클릭 **Ribbon 테스트**합니다.

## <a name="see-also"></a>참고자료

[리본 디자이너(MFC)](../mfc/ribbon-designer-mfc.md)
