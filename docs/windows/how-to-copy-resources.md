---
title: '방법: 리소스 관리 (C++)'
ms.date: 02/14/2019
f1_keywords:
- vc.resvw.resource.copying
- vs.resvw.resource.copying
- vc.resvw.resource.changing
- vb.xmldesigner.data
- vs.resvw.resource.importing
- vc.resvw.resource.importing
helpviewer_keywords:
- resources [C++], moving between files
- resources [C++], copying
- resource files [C++], copying or moving resources between
- resource files [C++], tiling
- .rc files [C++], copying resources between
- rc files [C++], copying resources between
- Language property [C++]
- .resx files [C++], editing
- resource files [C++], editing
- resx files [C++], editing
- resources [C++], exporting
- graphics [C++], exporting
- graphics [C++], importing
- resources [C++], importing
- bitmaps [C++], importing and exporting
- toolbars [C++], importing
- images [C++], importing
- toolbars [C++], exporting
- cursors [C++], importing and exporting
- images [C++], exporting
ms.assetid: 65f523e8-017f-4fc6-82d1-083c56d9131f
ms.openlocfilehash: 28678b560387fa6b111d60a7487ed44f9244a821
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2019
ms.locfileid: "65449067"
---
# <a name="how-to-manage-resources-c"></a>방법: 리소스 관리 (C++)

## <a name="copy-and-edit-resources"></a>복사 및 편집 리소스

변경 하거나 복사 하는 동안 언어 또는 리소스의 상태를 변경 하지 않고 다른 하나의 파일에서 리소스를 복사할 수 있습니다.

현재 리소스 파일에 기존 리소스 또는 실행 파일에서 리소스를 쉽게 복사할 수 있습니다. 리소스를 복사 하려면 동시에 리소스를 포함 하는 두 파일을 열고 및 다른 하나의 파일에서 항목을 끌어 또는 복사 하는 두 파일 사이 붙여 넣습니다. 이 메서드는 실행 파일 (.exe)와 리소스 스크립트 (.rc) 파일 및 리소스 템플릿 (.rct) 파일에 대 한 작동합니다.

> [!NOTE]
> Visual C++ 응용 프로그램에서 사용할 수 있는 샘플 리소스 파일을 포함 합니다. 자세한 내용은 참조 하세요. [클립 아트. 일반적인 리소스](https://github.com/Microsoft/VCSamples)합니다.

및 삭제, 복사, 잘라내기를 끌거나 수 간의 프로젝트에서 리소스 파일에 붙여 넣습니다 (**리소스 뷰**) 및 문서 창에서 독립 실행형.rc 파일을 엽니다. 이전 버전의 제품에서이 수행할 수 있습니다. 프로젝트 외부에서 열려 있는.rc 파일 간에 끌어서 놓기 메서드만을 사용 합니다.

### <a name="to-copy-resources"></a>리소스 복사

1. 두 리소스 파일을 모두 독립 실행형으로 엽니다. (참조 [리소스 스크립트 파일을 사용 하 여](how-to-create-a-resource-script-file.md#use-resource-script-files)). 예를 들어 열 *Source1.rc* 하 고 *Source2.rc*합니다.

1. 내 첫 번째.rc 파일 중 하나:

   - 끌어서 놓기 메서드를 사용 합니다.

      1. 복사 하려는 리소스를 선택 합니다. 예를 들어 *Source1.rc*를 선택 **IDD_DIALOG1**합니다.

      1. 누른 합니다 **Ctrl** 키 및 두 번째.rc 파일의 리소스를 끕니다. 예를 들어 끌어 **IDD_DIALOG1** 에서 *Source1.rc* 하 *Source2.rc*합니다.

         > [!TIP]
         > 리소스를 누르지 않고 끌기 합니다 **Ctrl** 복사 하는 것이 아니라 리소스 키를 누르면 합니다.

   - 복사 및 붙여넣기 메서드 사용

      1. 리소스를 마우스 오른쪽 단추로 클릭을 복사 하려면 (예를 들어 *Source1.rc*) 선택한 **복사**합니다.

      1. 리소스를 붙여 하려는 리소스 파일을 마우스 오른쪽 단추로 클릭 (예를 들어 *Source2.rc*) 선택한 **붙여**합니다.

> [!NOTE]
> 기호 이름이 나 기존 파일을 시각적 개체의 값을 사용 하 여 충돌을 방지 하려면 C++ 새 파일에 복사 하면 되는 리소스의 기호 값 또는 기호 이름 및 값 변경 될 수 있습니다.

리소스에서 복사하는 동안 언어 속성이나 조건 속성 또는 두 가지 모두를 변경할 수 있습니다.

- 사용 되는 언어를 지정 하는 리소스의 언어 [FindResource](/windows/desktop/api/winbase/nf-winbase-findresourcea) 를 찾고 있는 리소스를 식별 하는 데 있습니다. 가속기는 일본어 자판 에서만 작동할 수 있습니다 하거나 비트맵이 중국어로 지역화 된 적절 하 게 작성 하는 예를 들어을 리소스 텍스트와 연관 되지 않은 각 언어에 대 한 차이점을 가질 수 있습니다.

- 리소스의 조건은 리소스의 해당 특정 복사본이 사용되는 조건을 식별하는 정의된 기호입니다.

언어 및 리소스의 조건은 리소스의 이름 뒤에 오는 괄호 안에 표시 됩니다는 **작업 영역** 창입니다. 다음 명명 된 리소스가 `IDD_AboutBox` 사용 하는 `Finnish` 는 해당 언어 및 조건으로 `XX33`:

```cpp
IDD_AboutBox (Finnish - XX33)
```

### <a name="to-copy-an-existing-resource-and-change-its-language-or-condition"></a>기존 리소스를 복사하고 해당 언어 또는 조건을 변경하려면

에 *.rc* 파일 또는 [리소스 뷰](how-to-create-a-resource-script-file.md#create-resources) 창에서 복사 하 고 선택 하려는 리소스를 마우스 오른쪽 단추로 클릭 **복사본 삽입**합니다. 그리고 다음을 설정 합니다.

- 에 대 한 합니다 **언어** 목록 상자에서 언어를 선택 합니다.

- 에 **조건을** 상자에서 조건을 입력 합니다.

### <a name="to-edit-resources"></a>리소스를 편집 하려면

관리 되는 리소스 (.resx) 파일은 XML 파일입니다. 관리 되는 리소스 파일에서 프로젝트에 추가 되는 경우는 **새 항목 추가** 대화 상자를 **관리 되는 리소스 편집기** 기본적으로 열립니다.

## <a name="import-and-export-resources"></a>가져오기 및 내보내기 리소스

Visual C++에서 사용하도록 그래픽 리소스(비트맵, 아이콘, 커서 및 도구 모음), HTML 파일 및 사용자 지정 리소스를 가져올 수 있습니다. Visual Studio에서 동일한 형식의 파일을 내보낼 수 있습니다 C++ 개발 환경 외부에서 사용할 수 있는 별도의 파일로 프로젝트입니다.

> [!NOTE]
> 액셀러레이터 키, 대화 상자 및 문자열 테이블과 같은 리소스 종류 가져오거나 독립 실행형 파일 형식이 이기 때문에 내보낼 수 없습니다.

### <a name="to-import-a-resource-into-the-resource-script-file"></a>리소스 스크립트 파일에 리소스를 가져오려면

1. [리소스 뷰](how-to-create-a-resource-script-file.md#create-resources) 리소스를 추가 하 고 선택 하려는는 리소스 스크립트 (.rc) 파일의 노드를 마우스 오른쪽 단추로 클릭 **가져오기**합니다.

1. 찾아 비트맵 (.bmp), 아이콘 (.ico), 커서 (.cur), html 파일 (.htm) 또는 가져올 다른 파일의 파일 이름을 선택 합니다.

1. 선택 **확인** 리소스 스크립트 파일에 리소스를 추가 합니다.

> [!NOTE]
> 가져오기 프로세스 선택 하는 리소스 종류에 관계 없이 동일 하 게 작동 합니다. 가져온된 리소스는 해당 리소스 종류의 올바른 노드를 자동으로 추가 됩니다.

### <a name="to-export-a-resource-for-use-outside-of-visual-c"></a>시각적 개체 외부에서 사용할 리소스를 내보내려면C++

1. [리소스 뷰](how-to-create-a-resource-script-file.md#create-resources), 내보내기 및 선택 하려는 리소스를 마우스 오른쪽 단추로 클릭 **내보내기**합니다. 현재 파일 이름을 그대로 사용 하거나 새 이름을 입력 수 있습니다.

1. 선택한 파일을 저장 하려는 폴더로 이동한 후 **내보내기**합니다.

## <a name="requirements"></a>요구 사항

Win32

## <a name="see-also"></a>참고자료

[리소스 파일](../windows/resource-files-visual-studio.md)<br/>
[방법: 리소스 만들기](../windows/how-to-create-a-resource-script-file.md)<br/>
[방법: 컴파일 시간에 리소스 포함](../windows/how-to-include-resources-at-compile-time.md)<br/>