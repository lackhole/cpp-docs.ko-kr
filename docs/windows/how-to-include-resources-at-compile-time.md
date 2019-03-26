---
title: '방법: (C + +) 컴파일 타임에 리소스 포함'
ms.date: 02/14/2019
f1_keywords:
- vs.resvw.resource.including
- vc.resvw.resource.including
- vc.editors.resourceincludes
helpviewer_keywords:
- comments [C++], compiled files
- resources [C++], including at compile time
- projects [C++], including resources
- '#include directive'
- include directive (#include)
- Resource Includes dialog box [C++]
- rc files [C++], changing storage
- symbol header files [C++], changing
- .rc files [C++], changing storage
- symbol header files [C++], read-only
- symbols [C++], symbol header files
- directories [C++], specifying include paths for resources
- include files [C++], specifying for resources
- resources [C++], including in projects
- symbols [C++], finding
- resources [C++], searching for symbols
ms.assetid: 357e93c2-0a29-42f9-806f-882f688b8924
ms.openlocfilehash: cd2f05b4944e26d8a96b3f96e4e39fda0ad8ee48
ms.sourcegitcommit: c1f646c8b72f330fa8cf5ddb0f8f261ba10d16f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2019
ms.locfileid: "58328391"
---
# <a name="how-to-include-resources-at-compile-time-c"></a>방법: (C + +) 컴파일 타임에 리소스 포함

하지만 모든 리소스는 하나의 리소스 스크립트 (.rc) 파일에 기본적으로 여러 가지 이유가 있습니다 주.rc 파일이 아닌 파일에 리소스를 배치 합니다.

- .Rc 파일을 저장할 때 삭제 되지 않는 리소스 문에 주석을 추가 합니다.

- 이미 개발 되 고 테스트 하는 리소스를 포함할 필요 하지 않습니다 추가 수정 합니다. 포함 되었지만.rc 확장명이 없는 모든 파일은 리소스 편집기에서 편집할 수 없습니다.

- 다른 프로젝트에서 사용 중인는 또는 소스 코드 버전 제어 시스템의 일부인 리소스를 포함 합니다. 이러한 리소스는 수정 모든 프로젝트에 적용 됩니다 중앙 위치에 있어야 합니다.

- 사용자 지정 형식에는 리소스 (예: RCDATA 리소스)를 포함 합니다. RCDATA 리소스에 대 한 값으로 식을 사용할 수 없습니다 위치 하는 특별 한 요구 사항이 `nameID` 필드입니다.

섹션에서는 이러한 조건 중 하나라도 충족 하는 기존.rc 파일에 있는 경우이 섹션에서는 하나에 배치 또는 별도.rc 파일 및 사용 하 여 프로젝트에 포함 된 **리소스 내용** 대화 상자.

## <a name="resource-includes"></a>리소스 내용

하면 리소스를 추가할 수 다른 파일에서 프로젝트 컴파일 타임에 나열 합니다 **컴파일 시간 지시문** 상자에 **리소스 내용** 대화 상자. 사용 합니다 **리소스 내용** 프로젝트 환경의 기본 수정할 작업에서 프로젝트.rc 파일 및 모든 리소스를 모두 저장 대화 상자 [기호](../windows/symbols-resource-identifiers.md) 에서 `Resource.h`합니다.

시작 하려면 열기를 **리소스 내용** .rc 파일에서 마우스 오른쪽 단추로 클릭 하 여 대화 상자 [리소스 뷰](how-to-create-a-resource-script-file.md#create-resources)를 선택 **리소스 내용** 다음 속성 및:

| 속성 | 설명 |
|---|---|
| **기호 헤더 파일** | 리소스 파일에 대 한 기호 정의가 저장 된 헤더 파일의 이름을 변경할 수 있습니다.<br/><br/>자세한 내용은 [기호 헤더 파일의 이름 변경](../windows/changing-the-names-of-symbol-header-files.md)합니다. |
| **읽기 전용 기호 지시문** | 수정 하지 않아야 하는 기호를 포함 하는 헤더 파일을 포함할 수 있습니다.<br/><br/>예를 들어, 기호 파일을 다른 프로젝트와 공유할 수 있습니다. 이 MFC.h 파일을 포함할 수도 있습니다. 자세한 내용은 [비롯 한 공유 (읽기 전용) 또는 계산 된 기호](../windows/including-shared-read-only-or-calculated-symbols.md)합니다. |
| **컴파일 시간 지시문** | 만들어지고 주 리소스 파일에 리소스에서 개별적으로 편집 되는 리소스 파일을 포함할 수 있습니다 (예: 해당 지시문 조건에 따라), 컴파일 시간 지시문을 포함 하거나 사용자 지정 형식에서 리소스를 포함할 수도 있습니다.<br/><br/>사용할 수도 있습니다는 **컴파일 시간 지시문 상자** 표준 MFC 리소스 파일을 포함 합니다. |

> [!NOTE]
> 이러한 텍스트 상자에 항목으로 표시.rc 파일에 나타나는 `TEXTINCLUDE 1`, `TEXTINCLUDE 2`, 및 `TEXTINCLUDE 3` 각각. 자세한 내용은 참조 하세요. [TN035: Visual c + +를 사용 하 여 여러 리소스 파일과 헤더 파일을 사용 하 여](../mfc/tn035-using-multiple-resource-files-and-header-files-with-visual-cpp.md)입니다.

사용 하 여 리소스 파일에 변경 되 면 합니다 **리소스 내용** 대화 상자를 닫은 후 다시 열어야 합니다 *.rc* 파일 변경 내용을 적용 하려면.

### <a name="to-include-resources-in-your-project-at-compile-time"></a>컴파일 시간에 프로젝트에 리소스를 포함하려면

1. 고유한 파일 이름으로 리소스 스크립트 파일에 리소스를 배치합니다. 사용 하지 마세요 *projectname.rc*이므로 주 리소스 스크립트 파일에 사용 되는 파일의 이름입니다.

1. 마우스 오른쪽 단추로 클릭 합니다 *.rc* 파일 [리소스 뷰](how-to-create-a-resource-script-file.md#create-resources) 선택한 **리소스 내용**합니다.

1. 에 **컴파일 시간 지시문** 상자에서 추가 합니다 [#include](../preprocessor/hash-include-directive-c-cpp.md) 컴파일러 지시문을 개발 환경에서 주 리소스 파일에 새 리소스 파일을 포함 합니다.

이러한 방식으로 포함 된 파일에 리소스 컴파일 타임에만 실행 파일의 일부를 구성 및 프로젝트의 주.rc 파일에서 작업 하는 경우 편집 또는 수정은 사용할 수 없습니다. 포함 된.rc 파일을 별도로 열어야 해야 하 고.rc 확장명이 없는 포함 된 모든 파일은 리소스 편집기에서 편집할 수 없습니다.

### <a name="to-specify-include-directories-for-a-specific-resource-rc-file"></a>지정 하는 특정 리소스 (.rc) 파일에 대 한 디렉터리를 포함 합니다.

1. 마우스 오른쪽 단추로 클릭 합니다 *.rc* 파일 **솔루션 탐색기** 선택한 **속성**합니다.

1. 선택는 **리소스** 왼쪽된 창에서 노드 추가 지정 디렉터리를 포함 합니다 **추가 포함 디렉터리** 속성입니다.

### <a name="to-find-symbols-in-resources"></a>리소스에서 기호를 찾으려면

1. 메뉴로 이동 **편집할** > [기호 찾기](/visualstudio/ide/go-to)합니다.

   > [!TIP]
   > 사용 하도록 [정규식](/visualstudio/ide/using-regular-expressions-in-visual-studio) 검색 범위를 선택 [파일에서 찾기](/visualstudio/ide/reference/find-command) 에 **편집** 대신 메뉴 **기호 찾기**합니다. 선택 된 **사용: Regular Expressions** 확인란을 [찾기 대화 상자](/visualstudio/ide/finding-and-replacing-text) 및 합니다 **찾을 내용** 상자는 정규 검색 식 드롭 다운 목록에서 선택할 수 있습니다. 검색 텍스트로 대체 식을이 목록에서를 선택 하면 합니다 **찾을 내용** 상자입니다.

1. 에 **찾을 내용** 상자, 드롭 다운 목록에서 이전에 검색 문자열을 선택 하거나 찾으려는, 예를 들어, 액셀러레이터 키 입력 `ID_ACCEL1`합니다.

1. 중 하나를 선택 합니다 **찾을** 선택한 옵션 **다음 찾기**합니다.

> [!NOTE]
> 문자열, 액셀러레이터 또는 이진 리소스에서 기호를 검색할 수 없습니다.

## <a name="requirements"></a>요구 사항

Win32

## <a name="see-also"></a>참고 항목

[리소스 파일](../windows/resource-files-visual-studio.md)<br/>
[방법: 리소스 만들기](../windows/how-to-create-a-resource-script-file.md)<br/>
[방법: 리소스 관리](../windows/how-to-copy-resources.md)<br/>