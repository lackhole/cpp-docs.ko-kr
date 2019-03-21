---
title: '방법: 색 작업'
ms.date: 02/15/2019
f1_keywords:
- vc.editors.image.color
- vc.editors.customcolorselector
- vc.editors.loadcolorpalette
- vc.editors.colorswindow
helpviewer_keywords:
- images [C++], background colors
- Image editor [C++], Colors Palette
- colors [C++], image
- Colors Palette, Image editor
- palettes, Image editor colors
- foreground colors [C++], Image editor
- colors [C++]
- Image editor [C++], colors
- colors [C++], Image editor
- colors [C++], image
- images [C++], colors
- Image editor [C++], colors
- Fill tool
- colors [C++], image
- images [C++], colors
- colors [C++], selection tools
- Image editor [C++], colors
- Select Color tool
- dithered color, Image editor
- Custom Color Selector dialog box [C++]
- Image editor [C++], Colors Palette
- colors [C++], image
- bitmaps [C++], colors
- images [C++], colors
- HSL values
- Colors Palette, Image editor
- RGB color values
- Adjust Colors command [C++]
- Image editor [C++], dithered color
- Image editor [C++], Colors Palette
- Colors Palette, Image editor
- colors [C++], inverting
- colors [C++]
- Color Indicator
- colors [C++], Colors window
- Colors window, hiding colors
- Show Colors Window command
- Colors window, displaying colors
- color palettes [C++]
- palettes
- palettes, Image editor
- colors [C++], Image editor
- Image editor [C++], palettes
- color palettes
- Load Palette Colors dialog box [C++]
- opaque backgrounds [C++]
- colors [C++], image
- Image editor [C++], transparent or opague backgrounds
- images [C++], transparency
- images [C++], opaque background
- colors [C++], image
- Image editor [C++], color inversion
- images [C++], colors
- colors [C++], inverting
ms.assetid: d34ff96f-241d-494f-abdd-13811ada8cd3
ms.openlocfilehash: f50d734ab35968aa107e23b8450d60f316b6002e
ms.sourcegitcommit: b4645761ce5acf8c2fc7a662334dd5a471ea976d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/07/2019
ms.locfileid: "57563149"
---
# <a name="how-to-work-with-color"></a>방법: 색 작업

합니다 **이미지 편집기** 처리 하 고 색을 사용자 지정 하는 많은 기능이 포함 되어 있습니다. 전경 또는 배경 색을 설정 하, 색을 사용 하 여 제한 된 영역을 입력 하거나 현재 전경 또는 배경 색으로 사용할 이미지의 색을 선택할 수 있습니다. 도구를 사용할 수는 [이미지 편집기 도구 모음](../windows/toolbar-image-editor-for-icons.md) 색상표에 함께 합니다 **색** 창 이미지 만들기.

흑백 및 컬러 16 이미지에 대 한 모든 색에 표시 됩니다는 **색** 색상표에는 **색** 창입니다. 16 개의 표준 색이 함께 사용자 지정 색을 만들 수 있습니다. 즉시 색상표의 색을 변경 그림과에서 해당 색을 변경 합니다.

256 색 아이콘 및 커서 이미지를 사용 하 여 작업 하는 경우는 **색** 속성에는 [속성 창](/visualstudio/ide/reference/properties-window) 사용 됩니다. 자세한 내용은 [256 색 아이콘이 나 커서 만들기](creating-a-256-color-icon-or-cursor-image-editor-for-icons.md)합니다.

True-컬러 이미지를 만들 수도 있습니다. 하지만 True 색상 샘플의 전체 팔레트에 나타나지 않습니다 합니다 **색** 창 전경 또는 배경 색 표시기 영역에만 나타납니다. True 색을 사용 하 여 만들어집니다 합니다 **사용자 지정 색 선택** 대화 상자.

사용자 지정된 색상표를 디스크에 저장 하 고 필요에 따라 다시 로드 수 있습니다. 가장 최근에 사용한 색 색상표를 레지스트리에 저장 하 고에 Visual Studio를 시작할 때 자동으로 로드 합니다.

합니다 **색** 창에 두 부분으로 구성 합니다.

- 합니다 **색상표**를 사용할 수 있는 색을 나타내는 색상 샘플의 배열입니다. 그래픽 도구를 사용 하는 경우 전경색 및 배경색을 선택 하는 샘플을 선택할 수 있습니다.

- 합니다 **색 표시기**, 전경색 및 배경색 및 화면색 및 반전색 선택 기가 보여 줍니다.

   ![색상 창은](../windows/media/vccolorswindow.gif "vcColorsWindow")<br/>
   **색** 창

> [!NOTE]
> **색 화면** 하 고 **반전색** 도구 아이콘 및 커서에만 사용할 수 있습니다.

사용할 수는 **색** 창에는 [이미지 편집기 도구 모음](../windows/toolbar-image-editor-for-icons.md)합니다.

- 표시할 합니다 **색** 창에서 마우스 오른쪽 단추로 클릭은 **이미지 편집기** 창 선택 **색상 창 표시**, 메뉴로 이동 하거나 [이미지](../windows/image-menu-image-editor-for-icons.md)  >  **색상 창 표시**합니다.

- 숨기려면를 **색** 창 (이 작업을 통해 자동 숨기기 창을 사용 하 여에 없는 경우) 창 고정을 해제 하거나 선택 합니다 **닫기** 단추.

합니다 **색** 16 개의 표준 색 팔레트에 처음에 표시 됩니다. 표시 된 색을 사용 하 여 사용자 지정 색도 만들 수 있습니다. 그런 다음 저장 하 고 사용자 지정된 색상표를 로드할 수 있습니다.

합니다 **사용자 지정 색 선택** 대화 상자를 사용 하면 다음 속성을 사용 하 여 이미지에 사용할 색을 사용자 지정할 수 있습니다.

|속성|설명|
|--------------------------|--------------------------|
|**그라데이션 색 디스플레이**|선택한 색의 값을 변경 합니다.<br/><br/>십자선 변경 하 고 명도 또는 색의 RGB 값을 변경 하려면 슬라이더를 위나 아래로 이동 하려는 색에 배치 합니다.|
|**명도 막대**|선택한 색의 명도 설정 합니다 **그라데이션 색 디스플레이** 상자입니다.<br/><br/>밝기 모음을 흰색 화살표를 끌어서 선택 또는 작은 중단 되었습니다. 합니다 **Color** 선택한 색 및 효과 설정한 명도를 상자에 표시 됩니다.|
|**색**|정의 하는 색의 색상 (컬러 휠 값)를 나열 합니다. 값 범위는 0부터 240 여기서 0은 빨강, 60은 노란색, 120은 녹색, 180은 녹청, 200은 자홍, 240는 파란색입니다.|
|**Hue**|정의 하는 색의 색상 (컬러 휠 값)를 나열 합니다. 값 범위는 0부터 240 여기서 0은 빨강, 60은 노란색, 120은 녹색, 180은 녹청, 200은 자홍, 240는 파란색입니다.|
|**Sat**|정의 하는 색의 채도 값을 지정 합니다. 채도 색을 지정한 색상의 크기입니다. 값은 0에서 240 까지입니다.|
|**Lum**|정의 하는 색의 명도 (밝기)를 나열 합니다. 값은 0에서 240 까지입니다.|
|**빨간색**|정의 하는 색의 빨강 값을 지정 합니다. 0에서 255 사이의 값입니다.|
|**녹색**|정의 하는 색의 녹색 값을 지정 합니다. 0에서 255 사이의 값입니다.|
|**Blue**|정의 하는 색의 파랑 값을 지정 합니다. 0에서 255 사이의 값입니다.|

저장 하 고 로드할 수는 **색** 사용자 지정된 색이 들어 있는 색상표입니다. 기본적으로 **색** 가장 최근에 사용한 팔레트는 Visual Studio를 시작 하는 경우에 자동으로 로드 됩니다.

> [!TIP]
> 이후 합니다 **이미지 편집기** 기본값 복원에 **색** 색상표를 기본 저장 해야 **색** 와 같은 이름으로 색상표  *standard.pal* 나 *default.pal과* 기본 설정을 쉽게 복원할 수 있도록 합니다.

사용 된 **색상표 로드** 다음 속성을 사용 하 여 c + + 프로젝트에서 사용 하려면 특별 한 색상표 로드 대화 상자:

|속성|설명|
|-----------------|-----------------|
|**Look in**|파일 또는 폴더를 찾을 위치를 지정 합니다.<br/><br/>다른 위치를 선택 하 고 화살표 또는 한 수준 위로 이동 하려면 도구 모음의 폴더 아이콘을 선택 합니다.|
|**파일 이름**|열려는 파일의 이름을 입력할 공간을 제공 합니다.<br/><br/>이전에 열었던 파일을 빨리 찾으려면 사용 가능한 경우 드롭 다운 목록에서 파일 이름을 선택 합니다.<br/><br/>파일을 검색 하는 경우에 와일드 카드로 별표 (*)를 사용할 수 있습니다. 예를 들어 입력할 수 있습니다 \*.\* 모든 파일의 목록을 볼 수 있습니다. 파일의 전체 경로 예를 들어 입력할 수도 있습니다 *C:\My Documents\MyColorPalette.pal* 하거나  *\\\NetworkServer\MyFolder\MyColorPalette.pal*합니다.|
|**파일 형식**|표시할 파일의 목록을 표시 합니다.<br/><br/>색상표 (*.pal) 색상표의 기본 파일 형식입니다.|

## <a name="how-to"></a>방법

### <a name="to-select-foreground-or-background-colors"></a>전경색 또는 배경색 선택

제외 하 고는 **지우개**에서 도구를 **이미지 편집기** 현재 전경 또는 배경 색을 각각 마우스 왼쪽 또는 오른쪽 단추를 누를 때를 사용 하 여 도구 모음 그립니다.

- 마우스 왼쪽된 단추를 사용 하 여 전경색 선택에서 원하는 색을 선택 합니다 **색** 색상표입니다.

- 마우스 오른쪽 단추를 사용 하 여 배경색을 선택 하려면에서 원하는 색을 선택 합니다 **색** 색상표입니다.

### <a name="to-fill-a-bounded-area-of-an-image-with-a-color"></a>이미지 경계 영역 색을 채울

**이미지 편집기** 를 제공 합니다 **채우기** 도구가 포함 된 현재 그리기 색 또는 현재 배경색을 사용 하 여 이미지 영역입니다.

### <a name="to-use-the-fill-tool"></a>채우기 도구를 사용 하려면

1. 사용 하 여는 **이미지 편집기** 도구 모음이 나 메뉴 이동 **이미지** > **도구** 선택한 합니다 **채우기** 도구.

1. 필요한 경우 그리기 색을 선택 합니다. 에 [색상표](../windows/colors-window-image-editor-for-icons.md), 전경색을 선택 하려면 마우스 왼쪽된 단추 또는 배경 색을 선택 하려면 마우스 오른쪽 단추를 선택 합니다.

1. 이동 합니다 **채우기** 채울 영역에는 도구입니다.

1. 전경색 또는 배경색을 사용 하 여 입력을 각각 왼쪽 또는 오른쪽 마우스 단추를 선택 합니다.

### <a name="to-pick-up-a-color-from-an-image-to-use-elsewhere"></a>다른 곳에서 사용 하는 이미지에서 색을 선택 하려면

합니다 **색 선택**, 색-pickup 도구를 사용 하면 이미지에서 색 현재 전경색 또는 배경색을 왼쪽 또는 오른쪽 마우스 단추를 눌러 여부에 따라 또는 합니다. 취소 하는 **색 선택** 도구, 다른 도구를 선택 합니다.

1. 사용 하 여는 **이미지 편집기** 도구 모음이 나 메뉴 이동 **이미지** > **도구** 선택한 합니다 **색 선택** 도구입니다.

1. 이미지에서 선택 하려는 색을 선택 합니다.

   > [!NOTE]
   > 색을 선택 하 고 나면 합니다 **이미지 편집기** 가장 최근에 사용한 데이터 센터가 정상화 도구입니다.

1. 마우스 왼쪽된 단추를 사용 하 여, 전경색 또는 배경색에 대 한 마우스 오른쪽 단추를 그립니다.

### <a name="to-choose-the-background"></a>배경 선택

을 이동 하거나 이미지에서 선택 영역 복사 기본적으로 투명 한 현재 배경색과 일치 하는 모든 픽셀을 선택 되 고 대상 위치에 픽셀 숨깁니다 하지 않습니다.

불투명 한 배경으로 투명 한 배경을 (기본값)에서 전환 하 고 다시 수 있습니다. 선택 도구를 사용 하는 경우는 **투명 한 배경을** 및 **불투명 한 배경** 옵션에 표시 합니다 **옵션** 선택기는 **이미지 편집기** 도구 모음입니다.

![배경 옵션 &#45; 불투명 또는 투명](../windows/media/vcimageeditoropaqtranspback.gif "백그라운드 옵션 &#45; 불투명 또는 투명")<br/>
**투명 한 픽셀과 불투명 한 옵션** 에 **이미지 편집기 도구 모음**

#### <a name="to-switch-between-a-transparent-and-opaque-background"></a>투명 한 픽셀과 불투명 한 배경 사이 전환 하려면

에 **이미지 편집기** 도구 모음을 선택 합니다 **옵션** 선택기를 선택한 다음 적절 한 백그라운드:

- **불투명 한 배경 (O)**: 기존 이미지를 선택 영역의 모든 부분이 가립니다.

- **투명 한 배경을 (T)**: 기존 이미지는 선택 영역의 현재 배경색과 일치 하는 부분을 통해 보여 줍니다.

> [!TIP]
> 바로 가기,에 **이미지** 메뉴에서 선택 하거나 선택을 취소 **불투명 하 게 그리기**.

이미지의 어느 요소가 투명 하 게 변경 효과에 이미 선택 하는 동안 배경색을 변경할 수 있습니다.

### <a name="to-invert-the-colors-in-a-selection"></a>선택 영역에서 색을 반전

합니다 **이미지 편집기** 반전 된 색을 사용 하 여 이미지로 형태가 나타나는 방법을 알릴 수 있도록 이미지의 선택한 부분에서 색을 반전 하는 편리한 방법을 제공 합니다.

현재 선택 영역에서 색을 반전, 메뉴로 이동 **이미지** > **색 반전**합니다.

### <a name="to-customize-or-change-colors-on-the-colors-palette"></a>또는 사용자 지정 색 색상표에서 색을 변경 하려면

1. 메뉴로 이동 **이미지** > **색 조정**합니다.

1. 에 **사용자 지정 색 선택** 대화 상자, 적절 한 텍스트 상자에 RGB 또는 HSL 값을 입력 하 여 색을 정의 하거나에서 색을 선택 합니다 **그라데이션 색 디스플레이** 상자입니다.

1. 슬라이더를 이동 하 여 명도 설정 합니다 **명도** 모음입니다.

1. 많은 사용자 지정 색이 디더링됩니다. 디더링된 색에 가장 가까운 단색을 원하면 두 번 클릭 합니다 **Color** 상자입니다.

   디더링된 색을 원하는 나중에에서 슬라이더를 이동 합니다 **명도** 가로 막대형 또는 십자에서 이동를 **그라데이션 색 디스플레이** 상자 하 여 디더링을 복원 합니다.

1. 선택 **확인** 새로운 색을 추가 합니다.

### <a name="to-save-a-custom-colors-palette"></a>사용자 지정 색 색상표를 저장하려면

1. 메뉴로 이동 **이미지** > **색상표 저장**합니다.

1. 색상표를 저장할 디렉터리로 이동하고 색상표의 이름을 입력합니다.

1. **저장**을 선택합니다.

### <a name="to-load-a-custom-colors-palette"></a>사용자 지정 색 색상표를 로드하려면

1. 메뉴로 이동 **이미지** > **색상표 로드**합니다.

1. 에 **색상표 로드** 대화 상자 올바른 디렉터리로 이동 하 고 로드할 색상표를 선택 합니다. **색** 색상표는.pal 파일 확장명으로 저장 됩니다.

## <a name="requirements"></a>요구 사항

없음

## <a name="see-also"></a>참고 항목

[아이콘에 대한 이미지 편집기](../windows/image-editor-for-icons.md)<br/>
[방법: 아이콘 또는 기타 이미지 만들기](../windows/creating-an-icon-or-other-image-image-editor-for-icons.md)<br/>
[방법: 이미지 편집](../windows/selecting-an-area-of-an-image-image-editor-for-icons.md)<br/>
[방법: 그리기 도구 사용](../windows/using-a-drawing-tool-image-editor-for-icons.md)<br/>
[액셀러레이터 키](../windows/accelerator-keys-image-editor-for-icons.md)<br/>
