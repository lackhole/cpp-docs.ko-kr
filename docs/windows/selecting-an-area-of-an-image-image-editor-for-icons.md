---
title: '방법: 이미지 편집'
ms.date: 02/15/2019
f1_keywords:
- vc.editors.image.editing
- vc.editors.image.editing
helpviewer_keywords:
- Image editor [C++], image selection
- Image editor [C++], selecting images
- images [C++], selecting
- cursors [C++], selecting areas of
- Image editor [C++], editing images
- Clipboard [C++], pasting
- images [C++], editing
- images [C++], deleting selected parts
- images [C++], copying selected parts
- images [C++], moving selected parts
- images [C++], dragging and replicating selected parts
- images [C++], pasting into
- graphics [C++], editing
- Image editor [C++], flipping and rotating images
- images [C++], flipping
- images [C++], rotating
- Image editor [C++], resizing images
- graphics [C++], resizing
- images [C++], resizing
- resizing images
- size [C++], images
- images [C++], cropping
- images [C++], extending
- Image editor [C++], cropping or extending images
- Image editor [C++], shrinking and stretching images
- images [C++], stretching
- images [C++], shrinking
- bitmaps [C++], shrinking
- bitmaps [C++], stretching
- Image editor [C++], editing images
- images [C++], editing
- images [C++], properties
- Image editor [C++], Properties window
- Properties window, image editor
ms.assetid: 8b6ce4ad-eba1-4ece-86ba-cea92c3edff2
ms.openlocfilehash: 246dee3c7d0c1a5a4f495fddf709833acc2c885e
ms.sourcegitcommit: b4645761ce5acf8c2fc7a662334dd5a471ea976d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/07/2019
ms.locfileid: "57562993"
---
# <a name="how-to-edit-an-image"></a>방법: 이미지 편집

잘라내기, 복사, 지우기, 크기를 조정, 반전, 또는 이동 하려는 이미지의 영역을 정의 하려면 선택 도구를 사용할 수 있습니다. 사용 하 여 합니다 **사각형 선택** 도구를 정의 하 고 이미지의 사각형 영역을 선택할 수 있습니다. 사용 하 여 합니다 **부정형** 도구 잘라내기, 복사 또는 다른 작업에 대 한 선택 하려는 영역의 윤곽선을 자유롭게 그릴 수 있습니다.

> [!NOTE]
> 참조를 **사각형 선택** 하 고 **부정형** 도구에 나온 [이미지 편집기 도구 모음](../windows/toolbar-image-editor-for-icons.md) 합니다 에각단추와연결된도구팁을보거나**이미지 편집기** 도구 모음입니다.

선택 영역에서 사용자 지정 브러시도 만들 수 있습니다. 자세한 내용은 [사용자 지정 브러시 만들기](../windows/creating-a-custom-brush-image-editor-for-icons.md)합니다.

## <a name="how-to"></a>방법

이미지를 편집 하려면 다음을 참조 하는 방법.

### <a name="to-select-an-image"></a>이미지를 선택 합니다.

1. 사용 하 여를 **이미지 편집기** 도구 모음이 나 메뉴 이동 **이미지** > **도구** 원하는 선택 도구를 선택 합니다.

1. 선택 하려는 이미지 영역의 한쪽 모퉁이 삽입 지점을 이동 합니다. 십자 모양 커서를 이미지 위로 가져갈 때 표시 됩니다.

1. 선택 하려는 영역의 반대쪽 모퉁이에 커서를 끕니다. 사각형을 보여 줍니다는 픽셀 선택 됩니다. 아래의 사각형을 포함 하 여 사각형 내에서 모든 픽셀 선택 영역에 포함 됩니다.

1. 마우스 단추를 놓습니다. 선택 영역 테두리 선택된 영역을 포함합니다.

#### <a name="to-select-an-entire-image"></a>전체 이미지를 선택 합니다.

현재 선택 영역 외부의 이미지를 선택 합니다. 선택 영역 테두리 포커스 변경 및 다시 한 번에 전체 이미지를 포함 합니다.

### <a name="to-edit-parts-of-an-image"></a>이미지의 일부를 편집 하려면

표준 편집 작업을 수행할 수 있습니다-잘라내기, 복사, 해제 및 이동-에 [선택](../windows/selecting-an-area-of-an-image-image-editor-for-icons.md)의 일부 또는 전체 이미지 선택 인지, 합니다. 때문에 **이미지 편집기** 사용 하는 **Windows 클립보드**, 간에 이미지를 전송할 수 있습니다를 **이미지 편집기** 및 Windows 용 응용 프로그램입니다.

또한 일부 또는 전체 이미지를 포함 하는지 여부를 선택 항목을 조정할 수 있습니다.

#### <a name="to-cut-the-current-selection-and-move-it-to-the-clipboard"></a>현재 선택 영역을 잘라내어 클립보드에 이동 하려면

메뉴로 이동 **편집할** > **잘라내기**합니다.

#### <a name="to-copy-the-selection"></a>선택 영역 복사

1. 크기 조정 핸들 제외 하 고에 선택 테두리 내에서 또는 어디서 나 포인터를 놓습니다.

1. 누른 합니다 **Ctrl** 키를 새 위치로 선택 항목을 끕니다. 원래 선택 항목의 영역 변경 되지 않습니다.

1. 선택 영역에 현재 위치에 있는 이미지를 복사 하려면 선택 커서 외부 선택 합니다.

#### <a name="to-paste-the-clipboard-contents-into-an-image"></a>에 이미지에 클립보드 내용 붙여넣기

1. 메뉴로 이동 **편집할** > **붙여넣기**합니다.

   클립보드 내용을 선택 테두리가 창의 왼쪽 위 모퉁이에 나타납니다.

1. 선택 영역 테두리 내에 포인터를 배치 하 고 이미지를 이미지에 원하는 위치로 끕니다.

1. 새 위치에 이미지를 고정, 외부 선택 테두리를 선택 합니다.

#### <a name="to-delete-the-current-selection-without-moving-it-to-the-clipboard"></a>클립보드로 이동 하지 않고 현재 선택 영역을 삭제 하려면

메뉴로 이동 **편집할** > **삭제**합니다.

   선택 영역의 원래 현재 배경색으로 채워집니다.

> [!NOTE]
> 액세스할 수 있습니다 합니다 **잘라내기**, **복사**를 **붙여넣기**, 및 **삭제** 명령을 마우스 오른쪽 단추로 클릭 하 여는 **리소스 뷰** 창입니다.

#### <a name="to-move-the-selection"></a>선택 항목

1. 크기 조정 핸들 제외 하 고에 선택 테두리 내에서 또는 어디서 나 포인터를 놓습니다.

1. 선택 항목을 새 위치로 끕니다.

1. 새 위치에 있는 이미지에서 선택 영역 앵커와 선택 테두리 바깥쪽 선택 합니다.

선택 하 여 드로잉에 대 한 자세한 내용은 참조 하세요. [사용자 지정 브러시 만들기](../windows/creating-a-custom-brush-image-editor-for-icons.md)합니다.

### <a name="to-flip-an-image"></a>이미지 대칭 이동

대칭 이동 하거나 원래의 미러 이미지를 만들기, 뒤집어 이미지, 또는 한 번에 이미지를 오른쪽 90도 회전 이미지 회전 수 있습니다.

- 이미지를 가로로 대칭 이동 (미러 이미지) 메뉴로 이동 **이미지** > **좌우 대칭**합니다.

- 이미지를 세로로 대칭 이동 (뒤집어), 메뉴로 이동 **이미지** > **상하 대칭**합니다.

- 메뉴 이미지를 90도 회전 하려면 이동할 **이미지** > **90도 회전**합니다.

   > [!NOTE]
   > 사용할 수도 있습니다는 [액셀러레이터 키](../windows/accelerator-keys-image-editor-for-icons.md) 이러한 명령에 대 한 바로 가기 메뉴에서 명령에 액세스 하거나 (하는 동안 이미지 외부 선택는 **이미지 편집기**).

### <a name="to-resize-an-image"></a>이미지 크기를 조정 하려면

동작을 **이미지 편집기** 인지에 따라 달라 지지만 이미지 크기 조정 [선택한](../windows/selecting-an-area-of-an-image-image-editor-for-icons.md) 전체 이미지 또는의 일부입니다.

이미지의 일부만 포함 하 여 선택 하는 경우는 **이미지 편집기** 픽셀의 행 이나 열을 삭제 하 고 현재 배경색을 사용 하 여 빈된 영역을 입력 하 여 선택 영역을 축소 합니다. 또한 픽셀의 행 이나 열을 복제 하 여 선택 영역을 확장할 수 것.

전체 이미지를 포함 하 여 선택 하는 경우는 **이미지 편집기** 하거나 축소 하 고 이미지를 또는 잘라 내 확장 하 고 있습니다.

메커니즘은 두 가지 이미지 크기 조정에 대 한: 크기 조정 핸들 및 [속성 창](/visualstudio/ide/reference/properties-window)합니다. 이미지의 일부나 모두의 크기를 변경 하려면 크기 조정 핸들을 끌어 있습니다. 끌 수 있는 크기 조정 핸들은 실선입니다. 속이 빈 핸들을 끌 수 없습니다. 사용 된 **속성** 전체 크기를 조정 하려면 창의 이미지만, 선택된 된 부분이 아닌 합니다.

![비트맵의 핸들 크기 조정](../mfc/media/vcimageeditorsizinghandles.gif "vcImageEditorSizingHandles")<br/>
크기 조정 핸들

> [!NOTE]
> 있는 경우는 **바둑판식 모눈** 옵션을 선택 합니다 [모눈 설정 대화 상자](../windows/grid-settings-dialog-box-image-editor-for-icons.md), 다음 바둑판식 모눈에 스냅숏 크기 조정이 합니다. 경우는 **픽셀 모눈** 옵션은 (기본 설정)를 선택 하면 다음 사용 가능한 픽셀 눈금의 크기를 조정 합니다.

#### <a name="to-resize-an-entire-image-using-the-properties-window"></a>속성 창을 사용 하 여 전체 이미지 크기를 조정 하려면

1. 변경할 속성 이미지를 엽니다.

1. 에 **너비** 및 **높이** 상자에 [속성 창](/visualstudio/ide/reference/properties-window)를 원하는 크기를 입력 합니다.

   이미지의 크기를 증가 하는 경우는 **이미지 편집기** 오른쪽 이나 아래쪽 이미지 또는 둘 모두를 확장 하 고 새 영역을 현재 배경색으로 채웁니다. 이미지를 채우도록 확장 되지 않습니다.

   이미지의 크기를 단축 합니다 **이미지 편집기** 오른쪽 가장자리나 아래쪽 가장자리 또는 둘 다에서 이미지를 자릅니다.

   > [!NOTE]
   > 사용할 수는 **너비** 하 고 **높이** 일부 선택 영역이 필요가 전체 이미지, 크기를 조정 하는 속성입니다.

#### <a name="to-crop-or-extend-an-entire-image"></a>자르거나 전체 이미지를 확장 하려면

1. 전체 이미지를 선택 합니다.

   이미지의 일부는 현재 선택한 경우 전체 이미지를 선택 하려는, 현재 선택 영역 경계 외부에 있는 이미지 아무 곳 이나 선택 합니다.

1. 이미지에 적절 한 크기는 때까지 크기 조정 핸들을 끕니다.

일반적으로 **이미지 편집기** 크기 조정 핸들을 이동 하 여 해당 크기를 조정할 때 이미지를 확대 하거나 자릅니다. 누른 채 합니다 **Shift** 크기 조정 핸들을 이동 하면 키를 **이미지 편집기** 를 축소 하거나 확장 하는 이미지입니다.

#### <a name="to-shrink-or-stretch-an-entire-image"></a>전체 이미지를 확장 또는 축소 하려면

1. 전체 이미지를 선택 합니다.

   현재 선택 된 이미지의 부분을 전체 이미지를 선택 하는 경우 현재 선택 영역 경계 외부에 있는 이미지 아무 곳 이나 선택 합니다.

1. 누른 합니다 **Shift** 키 및 크기 조정 핸들을 끌어 이미지의 크기가 적합 합니다.

#### <a name="to-shrink-or-stretch-part-of-an-image"></a>이미지의 일부를 확장 또는 축소 하려면

1. 크기를 조정 하려면 이미지의 일부를 선택 합니다. 자세한 내용은 [이미지 영역 선택](../windows/selecting-an-area-of-an-image-image-editor-for-icons.md)합니다.

1. 선택 영역 오른쪽 크기가 될 때까지 크기 조정 핸들 중 하나를 끕니다.

### <a name="to-edit-an-image-outside-of-a-project"></a>프로젝트 외부의 이미지를 편집 하려면

열고와 마찬가지로 모든 그래픽 응용 프로그램에서 독립 실행형 편집에 대 한 비트맵을 열고 예를 들어 개발 환경에서 이미지를 편집 합니다. 작업할 이미지에는 Visual Studio 프로젝트에 속하지 않아도 됩니다.

1. 메뉴로 이동 **파일** > **오픈**합니다.

1. 에 **파일 형식** 상자에서 **모든 파일**합니다.

1. 찾아 편집 하려는 이미지를 엽니다.

### <a name="to-change-image-properties"></a>이미지 속성을 변경 하려면

설정 하거나 사용 하 여 이미지의 속성을 수정할 수는 [속성 창](/visualstudio/ide/reference/properties-window)합니다.

1. 이미지를 엽니다는 **이미지 편집기**합니다.

1. 에 **속성** 창 이미지에 대 한 모든 속성을 변경 합니다.

   |속성|설명|
   |--------------|-----------------|
   |**색**|이미지의 색 구성표를 지정합니다. 선택 **단색**를 **16**, 또는 **256**, 또는 **색 True**합니다.<br/><br/>이미 16 색 색상표를 사용 하 여 이미지를 그릴 경우 선택 **단색** 흑백 색에 대 한 대체 이미지에 발생 합니다. 대비 항상 유지 되지 않습니다: 예를 들어, 빨강 및 녹색의 인접 한 영역 둘 다로 변환할지 검은색입니다.|
   |**Filename**|이미지 파일의 이름을 지정합니다.<br/><br/>Visual Studio는 기본적으로 기본 리소스 식별자 (IDB_BITMAP1) 및 적절 한 확장을 추가 처음 네 개의 문자 ("IDB_")를 제거 하 여 만든 기본 파일 이름을 할당 합니다. 이 예제 이미지에 대 한 파일 이름은 *BITMAP1.bmp*합니다. 이름을 바꿀 수 있습니다 *MYBITMAP1.bmp*합니다.|
   |**높이**|이미지의 높이 (픽셀)를 설정합니다. 기본값은 48입니다.<br/><br/>이미지가 잘립니다 또는 기존 이미지 아래에 빈 공백을 추가 합니다.|
   |**ID**|리소스의 식별자를 설정합니다.<br/><br/>이미지에 대 한 Microsoft Visual Studio에서 기본적으로 할당 일련의 사용 가능한 다음 식별자: IDB_BITMAP1, IDB_BITMAP2, 및 등입니다. 아이콘 및 커서에 대 한 유사한 이름이 사용 됩니다.|
   |**색상표**|색 속성을 변경 합니다.<br/><br/>색을 선택 하 고 표시를 두 번 클릭 합니다 [사용자 지정 색 선택 대화 상자](../windows/custom-color-selector-dialog-box-image-editor-for-icons.md)합니다. 적절 한 텍스트 상자에 RGB 또는 HSL 값을 입력 하 여 색을 정의 합니다.|
   |**SaveCompressed**|이미지를 압축 된 형식에서 인지 여부를 나타냅니다. 이 속성은 읽기 전용입니다.<br/><br/>Visual Studio을 압축 된 형식으로 이미지를 저장할 수 있도록 하지 Visual Studio에서 만든 모든 이미지에 대해이 속성이 되도록 **False**합니다. 이 속성은 됩니다 (다른 프로그램에서 만든) 압축 된 이미지를 Visual Studio에서 열면 **True**합니다. Visual Studio를 사용 하 여 압축 된 이미지를 저장 하는 경우 압축 되지 것입니다 하 고이 속성은 되돌아갑니다 **False**합니다.|
   |**너비**|이미지의 너비 (픽셀)를 설정합니다. 비트맵에 대 한 기본값은 48입니다.<br/><br/>이미지가 잘립니다 또는 기존 이미지의 오른쪽에 공백이 추가 됩니다.|

## <a name="requirements"></a>요구 사항

없음

## <a name="see-also"></a>참고 항목

[아이콘에 대한 이미지 편집기](../windows/image-editor-for-icons.md)<br/>
[방법: 아이콘 또는 기타 이미지 만들기](../windows/creating-an-icon-or-other-image-image-editor-for-icons.md)<br/>
[방법: 그리기 도구 사용](../windows/using-a-drawing-tool-image-editor-for-icons.md)<br/>
[방법: 색 작업](../windows/working-with-color-image-editor-for-icons.md)<br/>
[액셀러레이터 키](../windows/accelerator-keys-image-editor-for-icons.md)<br/>