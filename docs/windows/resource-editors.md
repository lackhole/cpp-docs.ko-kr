---
title: 리소스 편집기 (C++)
ms.date: 02/14/2019
f1_keywords:
- vs.editors.resource
- vc.resvw.resource.editors
- vs.resvw.resource.editors
- vs.resourceview
- vc.resvw.resource.previewing
- vs.resvw.resource.previewing
helpviewer_keywords:
- editors [C++], resource
- editors [C++]
- resource editors
- Windows [C++], application resource editing
- resources [C++], viewing
- layouts, previewing resource
- resource editors [C++], viewing resources
- .rc files [C++], viewing resources
- resources [C++], editing
- properties [C++], resources
- resources [C++], properties
ms.assetid: e20a29ec-d6fb-4ead-98f3-431a0e23aaaf
ms.openlocfilehash: 774575e978a8e7f94868eb1b5dad90c6ac345460
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62388178"
---
# <a name="resource-editors-c"></a>리소스 편집기 (C++)

리소스 편집기는 Visual Studio 프로젝트에 포함 된 리소스를 만들거나 수정에 대 한 특수 한 환경입니다. Visual Studio 리소스 편집기는 애플리케이션 리소스를 쉽고 빠르게 만들고 수정할 수 있도록 기술 및 인터페이스를 공유합니다. 리소스 편집기를 사용 하면 적절 한 편집기 및 미리 보기 리소스의 리소스 보기 및 편집 합니다.

리소스를 만들거나 열면 적절한 편집기가 자동으로 열립니다.

> [!NOTE]
> 리소스를 관리 되는 프로젝트는 리소스 스크립트 파일을 사용 하지 않으므로 열어야 **솔루션 탐색기**합니다. 사용할 수는 [이미지 편집기](../windows/image-editor-for-icons.md) 하며 [바이너리 편집기](binary-editor.md) 관리 되는 프로젝트에서에서 리소스 파일을 사용 하 합니다. 편집할 관리되는 리소스는 연결된 리소스여야 합니다. Visual Studio 리소스 편집기에서는 포함된 리소스를 편집할 수 없습니다.

|사용...|편집...|
|----------------|----------------|
|[액셀러레이터 키 편집기](../windows/accelerator-editor.md)|Visual C++ 프로젝트의 액셀러레이터 키 테이블입니다.|
|[Binary Editor](binary-editor.md)|Visual C++, Visual Basic 또는 Visual C# 프로젝트의 이진 데이터 정보 및 사용자 지정 리소스입니다.|
|[대화 상자 편집기](../windows/dialog-editor.md)|Visual C++ 프로젝트의 대화 상자입니다.|
|[Image Editor](../windows/image-editor-for-icons.md)|Visual C++, Visual Basic 또는 Visual C# 프로젝트의 비트맵, 아이콘, 커서 및 기타 이미지 파일입니다.|
|[메뉴 편집기](../windows/menu-editor.md)|Visual C++ 프로젝트의 메뉴 리소스입니다.|
|[리본 편집기](../mfc/ribbon-designer-mfc.md)|MFC 프로젝트의 리본 리소스입니다.|
|[문자열 편집기](../windows/string-editor.md)|Visual C++ 프로젝트의 문자열 표입니다.|
|[도구 모음 편집기](../windows/toolbar-editor.md)|Visual C++ 프로젝트의 도구 모음 리소스입니다. 합니다 **도구 모음 편집기** 의 일부인 합니다 **이미지 편집기**합니다.|
|[버전 정보 편집기](../windows/version-information-editor.md)|Visual C++ 프로젝트의 버전 정보입니다.|

> [!NOTE]
> 프로젝트에.rc 파일이 없으면 하세요 [방법: 리소스 만들기](../windows/how-to-create-a-resource-script-file.md)합니다.

## <a name="view-and-edit-resources"></a>보기 및 편집 리소스

각 리소스 종류에 해당 리소스 형식에 특정 리소스 편집기입니다. 다시 정렬의 크기를 조정 하거나 컨트롤 및 기능을 추가 합니다. 그렇지 않으면 연결된 된 편집기를 사용 하 여 리소스의 기능을 수정할 수 있습니다. 리소스를 편집할 수도 있습니다 [텍스트 형식](../windows/how-to-open-a-resource-script-file-in-text-format.md) 하 고 [이진 형식](../windows/opening-a-resource-for-binary-editing.md)합니다.

일부 리소스 종류는 개별 파일을 가져오고; 다양 한 방식에서으로 사용할 수 있습니다. 여기에 비트맵, 아이콘, 커서, 도구 모음 및 html 파일이 포함 됩니다. 이러한 리소스에 파일 이름이 고 [리소스 식별자](../windows/symbols-resource-identifiers.md)합니다. 다른 Win32 프로젝트에 있는 문자열 테이블 대화 상자, 메뉴 등 존재 리소스 스크립트 (.rc) 파일 또는 리소스 템플릿 (.rct) 파일의 일부로 합니다.

리소스 수도 있습니다 참조 프로젝트를 열고 하지 않고도 프로젝트 외부에서 편집 [방법: 리소스 만들기](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)합니다.

> [!NOTE]
> 사용 하 여 리소스의 속성을 수정할 수는 **속성** 창입니다.

- 리소스의 속성을 편집 하려면 [리소스 뷰](how-to-create-a-resource-script-file.md#create-resources)을 편집 하 고 선택 하려는 리소스를 마우스 오른쪽 단추로 클릭 **속성**합니다.  그런 다음 합니다 [속성 창](/visualstudio/ide/reference/properties-window), 리소스의 속성을 변경 합니다.

- 리소스의 속성에 대 한 변경을 취소 하려면 리소스에 포커스를가지고 있는지 확인 **리소스 뷰** 선택한 **실행 취소** 에서 합니다 **편집** 메뉴.

### <a name="win32-resources"></a>Win32 리소스

Win32 리소스에 액세스할 수 있습니다 합니다 [리소스 뷰](how-to-create-a-resource-script-file.md#create-resources) 창입니다.

#### <a name="to-view-a-win32-resource-in-a-resource-editor"></a>리소스 편집기에서 Win32 리소스를 보려면

1. 메뉴로 이동 **뷰** > **리소스 뷰**합니다.

1. 경우는 **리소스 뷰** 선택 최상위 창이 아닌 합니다 **리소스 뷰** 를 맨 위로 이동 하려면 탭 합니다.

1. **리소스 뷰**를 보려는 리소스를 포함 하는 프로젝트에 대 한 폴더를 확장 합니다. 대화 상자 리소스를 보려는 경우 확장 하는 예를 들어 합니다 **대화 상자** 폴더입니다.

1. 예를 들어 리소스를 두 번 클릭 **IDD_ABOUTBOX**합니다.

   리소스가 해당 편집기에서 열립니다. 예를 들어, 대화 상자 리소스에서 열립니다는 **대화 상자 편집기**합니다.

#### <a name="to-delete-an-existing-win32-resource"></a>기존 Win32 리소스를 삭제 하려면

1. **리소스 뷰**, 리소스 종류에 대 한 노드를 확장 합니다.

1. 선택한 삭제 하려는 리소스를 마우스 오른쪽 단추로 클릭 **삭제**합니다.

> [!TIP]
> .Rc 파일이 프로젝트 외부에서 문서 창에 열려 있는 경우에이 메서드를 사용할 수 있습니다.

### <a name="managed-project-resources"></a>관리 되는 프로젝트 리소스

리소스를 관리 되는 프로젝트에서 리소스 스크립트 파일을 사용 하지 않으므로 열어야 **솔루션 탐색기**합니다. 사용 하 여는 [이미지 편집기](../windows/image-editor-for-icons.md) 하며 [바이너리 편집기](binary-editor.md) 관리 프로젝트에서 리소스 파일로 작업 하 합니다. 모든 관리 되는 리소스를 편집 하려면 연결 된 리소스 및 Visual Studio 리소스 편집기 포함 된 리소스 편집을 지원 하지 않습니다.

- 리소스 편집기에서 관리 되는 리소스에서 보려는 **솔루션 탐색기**, 예를 들어 리소스를 두 번 클릭 *Bitmap1.bmp*, 및 리소스가 해당 편집기에서 열립니다.

- 기존 관리 되는 리소스를 삭제할 **솔루션 탐색기**를 선택 하 고 삭제 하려는 리소스를 마우스 오른쪽 단추로 클릭 **삭제**합니다.

## <a name="preview-resources"></a>리소스 미리 보기

그래픽 리소스를 열지 않고 볼 수 있도록 리소스를 미리 봅니다. 미리 보기에 유용 실행 파일을 컴파일한 후 리소스 식별자를 숫자로 변경 합니다. 종종 이러한 숫자 식별자는 충분 한 정보를 제공 하지 않습니다, 이후 리소스를 미리 보기 사용 하면 신속 하 게 식별할 수 있습니다.

다음과 같은 리소스 유형을 시각적 레이아웃 미리 보기를 제공 합니다. 비트맵, 대화 상자, 아이콘, 메뉴, 커서, 도구 모음

다음 리소스를 미리 보려면 제공 하지 않습니다. 액셀러레이터 키를 문자열 테이블 매니페스트 버전 정보

> [!NOTE]
> 리소스를 미리 보려면 Win32 필요 합니다.

### <a name="to-preview-resources"></a>리소스를 미리 보려면

1. [리소스 뷰](how-to-create-a-resource-script-file.md#create-resources) 또는 문서 창에 예를 들어, 리소스 선택 **IDD_ABOUTBOX**합니다.

1. 에 [속성 창](/visualstudio/ide/reference/properties-window)를 선택 합니다 **속성 페이지** 단추입니다.

   > [!TIP]
   > 바로 가기를 사용 하 여, 메뉴로 이동 **뷰** > **속성 페이지**합니다.

   합니다 **속성** 리소스 페이지가 열리고 해당 리소스의 미리 보기를 표시 합니다. 사용할 수는 **위로** 및 **아래로** 에서 트리를 탐색 하려면 화살표 키를 제어할 **리소스 뷰** 나 문서 창을 합니다. 합니다 **속성** 페이지를 열린 상태로 포커스가 생기 며 미리 볼 수 있는 모든 리소스를 표시 합니다.

## <a name="requirements"></a>요구 사항

없음

## <a name="see-also"></a>참고자료

[리소스 파일 작업](../windows/working-with-resource-files.md)<br/>
[리소스 파일](../windows/resource-files-visual-studio.md)<br/>
[리소스 식별자(기호)](../windows/symbols-resource-identifiers.md)<br/>