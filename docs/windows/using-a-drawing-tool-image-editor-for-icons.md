---
title: '방법: 그리기 도구 사용'
ms.date: 02/15/2019
f1_keywords:
- vc.editors.image.drawing
helpviewer_keywords:
- Image editor [C++], selecting drawing tools
- Image editor [C++], toolbar
- drawing tools
- Image editor [C++], drawing lines
- shapes, drawing
- colors [C++], brush
- brushes, colors
- brushes, creating custom
- images [C++], creating custom brushes
- graphics [C++], custom brushes
- custom brushes
ms.assetid: 1f8c6eef-7760-45a9-a5cb-9e15c6f91245
ms.openlocfilehash: 7b362749c9a5cb1c7ec77e5cac8625aa7eb260f0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62387840"
---
# <a name="how-to-use-a-drawing-tool"></a>방법: 그리기 도구 사용

합니다 **이미지 편집기** 자유 그리기 및 지우기 도구 모두 동일한 방식으로 작동 합니다. 도구를 선택 하 고 필요한 경우 [전경색 및 배경색을 선택](../windows/selecting-foreground-or-background-colors-image-editor-for-icons.md) 크기 및 모양 옵션입니다. 다음 이미지에 포인터를 이동 하 고 클릭 하거나 그리기 및 지우기으로 끌어 옵니다.

## <a name="drawing-tools"></a>그리기 도구

그리기 도구 중에서 선택할 수 있습니다 합니다 **이미지 편집기** 도구 모음 또는 **이미지** 메뉴. 선택 하는 경우는 **지우개** 도구인 **브러시** 도구인 또는 **에 어 브러시** 도구, 옵션 선택기에는 해당 도구의 옵션이 표시 됩니다.

> [!TIP]
>  단추 위에 커서를 올려 놓으면 도구 설명이 표시 합니다 [이미지 편집기 도구 모음](../windows/toolbar-image-editor-for-icons.md)합니다. 이러한 팁은 여기에 언급 된 특정 단추를 식별 하는 데 도움이 됩니다.

### <a name="to-select-and-use-a-drawing-tool-from-the-image-editor-toolbar"></a>선택 하 고 이미지 편집기 도구 모음에서 그리기 도구 사용

1. 단추를 선택 합니다 **이미지 편집기** 도구 모음입니다.

   - 합니다 **지우개** 마우스 왼쪽된 단추를 누를 때 현재 배경색을 사용 하 여 이미지 그리기 도구입니다.

      > [!TIP]
      > 사용 하는 대신 합니다 **지우개** 도구인 있습니다 더 편리할 수 것 그리기 도구 중 하나를 사용 하 여 배경색으로 그리는 것입니다.

   - 합니다 **연필** 도구 상수 1 픽셀 너비의 자유형 그립니다.

   - 합니다 **브러시** 도구에는 다양 한 형태와 규모에 있습니다.

   - 합니다 **에 어 브러시** 도구 색 픽셀 브러시의 중심을 임의로 분산 합니다.

1. 필요한 경우 색상 및 브러시를 선택 합니다.

   - 에 [색상표](../windows/colors-window-image-editor-for-icons.md), 전경색을 선택 하려면 마우스 왼쪽된 단추 또는 배경 색을 선택 하려면 마우스 오른쪽 단추를 선택 합니다.

   - 에 [옵션 선택기](../windows/toolbar-image-editor-for-icons.md), 사용 하려는 브러시를 나타내는 셰이프를 선택 합니다.

1. 그리기 또는 이미지 그리기를 시작 하려는 위치를 가리킵니다. 포인터는 선택한 도구에 따라 셰이프를 변경 합니다.

1. (전경색)에 대 한 왼쪽된 마우스 단추를 누르거나 (배경색)에 대 한 마우스 오른쪽 단추를 누른 상태로 그리기 합니다.

### <a name="to-select-and-use-a-drawing-tool-from-the-image-menu"></a>선택 하 고 이미지 메뉴에서 그리기 도구 사용

1. 메뉴로 이동 **이미지** > **도구**합니다.

1. 연계 하위 메뉴를 사용 하려면이 도구를 선택 합니다.

## <a name="lines-or-closed-figures"></a>선 또는 닫힌된 그림

합니다 **이미지 편집기** 선 및 닫힌된 그림 그리기 도구는 동일한 방식으로 작동 합니다: 특정 시점에 삽입 포인터를 두고 다른 위치로 이동할입니다. 줄에 대 한 이러한 지점은 끝점입니다. 닫힌된 그림에서 이러한 지점은 그림 경계 사각형의 모퉁이 반대 됩니다.

현재 브러시 선택에 따라 결정 되는 너비에서 선이 그려집니다 및 프레임된 그림 현재 두께 선택할 때 결정에 그려집니다. 선과 모든 그림을 모두 틀이 있고 채워진 그려집니다 왼쪽된 마우스 단추를 누르면 현재 전경색 또는 배경색 현재 마우스 오른쪽 단추를 누를 경우.

### <a name="to-draw-a-line"></a>선 그리기

1. 사용 하 여는 [이미지 편집기 도구 모음](../windows/toolbar-image-editor-for-icons.md) 메뉴로 이동 하거나 **이미지**> **도구** 선택 합니다 **줄** 도구.

1. 필요한 경우 색상 및 브러시를 선택 합니다.

   - 에 [색상표](../windows/colors-window-image-editor-for-icons.md), 전경색을 선택 하려면 마우스 왼쪽된 단추 또는 배경 색을 선택 하려면 마우스 오른쪽 단추를 선택 합니다.

   - 에 [옵션 선택기](../windows/toolbar-image-editor-for-icons.md), 사용 하려는 브러시를 나타내는 셰이프를 선택 합니다.

1. 선의 시작점에 포인터를 놓습니다.

1. 선의 끝점을 끕니다.

### <a name="to-draw-a-closed-figure"></a>닫힌된 그림 그리기를

1. 사용 합니다 **이미지 편집기** 도구 모음이 나 메뉴 이동 **이미지** > **도구** 선택한를 **닫힌 그림 그리기** 도구입니다.

   합니다 **닫힌 그림 그리기** 도구는 각 단추에 표시 된 대로 그림을 만듭니다.

1. 필요한 경우 색과 선 두께 선택 합니다.

1. 그림을 그릴 원하는 사각형 영역의 한쪽 모퉁이에 대 한 포인터를 이동 합니다.

1. 대각선 방향으로 반대쪽 모퉁이에 대 한 포인터를 끕니다.

## <a name="custom-brushes"></a>사용자 지정 브러시

사용자 지정 브러시는 선택 하 고와 같이 사용할 수 있는 이미지의 사각형 부분을 **이미지 편집기**의 포함 되어 있는 브러시입니다. 선택 영역에서 수행할 수 있는 모든 작업을 사용자 지정 브러시도 수행할 수 있습니다.

### <a name="to-create-a-custom-brush-from-a-portion-of-an-image"></a>이미지의 일부에서 사용자 지정 브러시를 만들려면

1. 브러시에 사용 하려는 이미지의 일부를 선택 합니다.

1. 저장 합니다 **Shift** 아래로 키, 선택 영역에서 선택 하 고 이미지에서 끌어 놓거나 메뉴로 이동 하 **이미지** > **사용 하 여 선택 항목을 브러시로**.

   선택한은 이미지에 색 선택 영역에 분산 하는 사용자 지정 브러시 됩니다. 선택 항목의 복사본은 끌기 경로 남아 있습니다. 끌면 더 느린, 많은 복사본이 만들어집니다.

   > [!NOTE]
   > 선택 하는 **브러시로 사용** 먼저 이미지의 부분의 선택 하는 전체 이미지를 브러시로 사용 하지 않고 있습니다. 사용자 지정 브러시를 사용 하면 선택 하는지에 따라 달라 집니다를 [불투명 또는 투명 한 배경을](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md)합니다.

현재 배경색을 일치 하는 사용자 지정 브러시 픽셀은 일반적으로 투명 한: 기존 이미지 그리기 하지 있습니다. 기존 이미지 그리기 배경색 픽셀 수 있도록이 동작을 변경할 수 있습니다.

다른 특수 효과 만들려면 스탬프 또는 스텐실와 같은 사용자 지정 브러시를 사용할 수 있습니다.

### <a name="to-draw-custom-brush-shapes-in-the-background-color"></a>배경색에 사용자 지정 브러시 모양을 그리는

1. 불투명 또는 투명 한 배경을 선택 합니다.

1. 배경색 그릴 원하는 색으로 설정 합니다.

1. 그리기를 사용자 지정 브러시를 배치 합니다.

1. 마우스 오른쪽 단추를 선택 합니다. 사용자 지정 브러시의 모든 불투명 영역 배경색에 그려집니다.

### <a name="to-double-or-halve-the-custom-brush-size"></a>두 번 또는 사용자 지정 브러시 크기를 절반으로 줄일

키를 눌러 합니다 **더하기** (**+**) 브러시 크기를 두 배로 키 또는 **빼기 기호** (**-**) 키를이 절반으로 줄일 .

### <a name="to-cancel-the-custom-brush"></a>사용자 지정 브러시를 취소 하려면

키를 눌러 **Esc** 하거나 다른 그리기 도구를 선택 합니다.

## <a name="requirements"></a>요구 사항

없음

## <a name="see-also"></a>참고자료

[아이콘에 대한 이미지 편집기](../windows/image-editor-for-icons.md)<br/>
[방법: 아이콘 또는 기타 이미지 만들기](../windows/creating-an-icon-or-other-image-image-editor-for-icons.md)<br/>
[방법: 이미지 편집](../windows/selecting-an-area-of-an-image-image-editor-for-icons.md)<br/>
[방법: 색 작업](../windows/working-with-color-image-editor-for-icons.md)<br/>
[액셀러레이터 키](../windows/accelerator-keys-image-editor-for-icons.md)<br/>