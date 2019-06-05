---
title: 문자열 편집기 (C++)
ms.date: 02/14/2019
f1_keywords:
- vc.editors.string.F1
- vc.editors.string
helpviewer_keywords:
- String editor
- string tables
- string tables [C++], String editor
- string editing
- string editing, string tables
- resource editors [C++], String editor
- strings [C++], editing
- strings [C++], searching
- strings [C++]
- strings [C++], adding to string tables
- string tables [C++], deleting strings
- strings [C++], deleting in string tables
- string tables [C++], adding strings
- strings [C++], moving between files
- resource script files [C++], moving strings
- string editing, moving strings between resources
- String editor [C++], moving strings between files
- resource identifiers, string properties
- string tables [C++], changing strings
- strings [C++], properties
- String editor [C++], changing properties of multiple strings
- string tables [C++], changing caption of multiple strings
- special characters, adding to strings
- ASCII characters, adding to strings
- strings [C++], formatting
- strings [C++], special characters
ms.assetid: f71ab8de-3068-4e29-8e28-5a33d18dd416
ms.openlocfilehash: e596aa475f0fb08609a0772ecc3f8a302e849275
ms.sourcegitcommit: ecf274bcfe3a977c48745aaa243e5e731f1fdc5f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2019
ms.locfileid: "66504815"
---
# <a name="string-editor-c"></a>문자열 편집기 (C++)

문자열 테이블은 애플리케이션의 모든 문자열에 대한 ID, 값 및 캡션 목록이 포함된 Windows 리소스입니다. 예를 들어 상태 표시줄 프롬프트는 문자열 테이블에 있습니다.

애플리케이션을 개발하는 동안 각 언어 또는 조건에 하나씩 여러 문자열 테이블을 만들 수 있습니다. 그러나 실행 가능 모듈에는 문자열 테이블이 하나만 포함됩니다. 테이블을 서로 다른 DLL에 삽입하면 실행 중인 애플리케이션이 여러 문자열 테이블을 참조할 수 있습니다.

문자열 테이블을 사용하면 애플리케이션을 여러 언어로 쉽게 지역화할 수 있습니다. 모든 문자열이 한 문자열 테이블에 있으면 소스 코드를 변경하지 않고 문자열과 기타 리소스를 번역하여 애플리케이션을 지역화할 수 있습니다. 이 상황은 수동으로 찾고 소스 파일에서 다양 한 문자열을 바꾸는 방법 보다 더 바람직합니다.

> [!NOTE]
> Windows는 빈 문자열 테이블 생성을 허용 하지 않습니다. 항목 없이 문자열 테이블을 만들면 리소스 파일을 저장할 때 해당 테이블이 자동으로 삭제됩니다.

## <a name="how-to"></a>방법

합니다 **문자열 편집기** 있습니다.

### <a name="to-find-a-string-resource-in-the-string-table"></a>문자열 테이블의 문자열 리소스를 찾으려면

1. 문자열 테이블에서 해당 아이콘을 두 번 클릭 하 여 [리소스 뷰](how-to-create-a-resource-script-file.md#create-resources)합니다.

1. 메뉴로 이동 **편집할** > **찾기 및 바꾸기** 선택 **찾기**합니다.

1. 에 **찾을 내용** 상자, 드롭 다운 목록에서 이전에 검색 문자열을 선택 하거나 찾으려는 문자열의 캡션 텍스트 또는 리소스 식별자를 입력 합니다.

1. 중 하나를 선택 합니다 **찾을** 옵션을 선택 **다음 찾기**합니다.

> [!TIP]
> 사용 하도록 [정규식](/visualstudio/ide/using-regular-expressions-in-visual-studio) 파일을 검색할 때 사용 합니다 **파일에서 찾기** 명령을 **편집** 메뉴.
>
> 오른쪽의 단추를 누르거나 패턴과 일치 하는 정규식을 입력 합니다 **찾을 내용** 정규 검색 식의 목록을 표시 하려면 상자입니다. 검색 텍스트로 대체 식을이 목록에서를 선택 하면 합니다 **찾을 내용** 상자입니다.
>
> 정규식을 사용 하는 경우는 **사용: Regular Expressions** 확인란을 선택 합니다.

### <a name="to-add-or-delete-a-string-resource"></a>추가 또는 문자열 리소스를 삭제 하려면

빠르게 삽입 하거나 사용 하 여 문자열 테이블에 항목을 삭제 합니다 **문자열 편집기**합니다. 새 문자열 테이블의 끝에 배치 되 고 사용 가능한 식별자가 지정 됩니다. 편집할 수 있습니다 합니다 **ID**, **값**, 또는 **캡션** 속성에는 [속성 창](/visualstudio/ide/reference/properties-window) 필요에 따라 합니다.

합니다 **문자열 편집기** 이미 사용 하는 ID를 사용 하지 않는 했는지 확인 합니다. ID를 이미 선택 하면 사용에서 된 **문자열 편집기** 를 표시 하 고 예를 들어 일반 고유 ID를 할당 `IDS_STRING58113`합니다.

#### <a name="to-add-a-string-table-entry"></a>문자열 테이블 항목을 추가 하려면

1. 문자열 테이블에서 해당 아이콘을 두 번 클릭 하 여 [리소스 뷰](how-to-create-a-resource-script-file.md#create-resources)합니다.

1. 문자열 테이블 내에서 마우스 오른쪽 단추로 클릭 하 고 선택 **새 문자열**합니다.

1. 에 **문자열 편집기**를 선택는 **ID** 에서 **ID** 드롭다운 목록 또는 형식은 *ID* 제 위치에 바로.

1. 편집 된 **값**필요한 경우.

1. 항목을 입력 합니다 **캡션**합니다.

   > [!NOTE]
   > Null 문자열은 Windows 문자열 테이블에서 허용 되지 않습니다. 묻는 메시지를 받게가 null 문자열을 문자열 테이블에 항목을 만들면 **이 테이블 엔트리에 대해 문자열을 입력 하십시오**합니다.

#### <a name="to-delete-a-string-table-entry"></a>문자열 테이블 항목을 삭제 하려면

삭제 하 고 다음 중 하나를 수행 하려는 항목을 선택 합니다.

- 메뉴로 이동 **편집할** > **삭제**합니다.

- 삭제 하 고 선택 하는 문자열을 마우스 오른쪽 단추로 클릭 **삭제**합니다.

- 키를 눌러 합니다 **삭제** 키입니다.

### <a name="to-move-a-string-from-one-resource-script-file-to-another"></a>다른 리소스 스크립트 파일에서 문자열을 이동 하려면

1. [두.rc 파일에서 문자열 테이블을 엽니다](../windows/how-to-create-a-resource-script-file.md)합니다.

1. 이동 및 선택 하는 문자열을 마우스 오른쪽 단추로 클릭 **잘라내기**합니다.

1. 대상 커서를 놓고 **문자열 편집기** 창입니다.

1. 에 *.rc* 문자열을 이동 하 마우스 오른쪽 단추로 클릭 한 다음 선택 하려는 파일 **붙여넣기**합니다.

> [!NOTE]
> 경우는 **ID** 또는 **값** 기존 이동한 문자열 충돌 **ID** 하거나 **값** 에 대상 파일 중 하나는 **ID** 나 **값** 이동한 문자열 변경 합니다.

### <a name="to-change-the-properties-of-a-string-resource"></a>문자열 리소스의 속성을 변경 하려면

내부 편집 하 여 변경 된 **ID**, **값**, 및 **캡션** 속성입니다.

> [!NOTE]
>  문자열의 속성을 편집할 수도 있습니다는 [속성 창](/visualstudio/ide/reference/properties-window)합니다.

#### <a name="to-change-a-string-or-its-identifier"></a>문자열 또는 식별자를 변경 하려면

1. 문자열 테이블에서 해당 아이콘을 두 번 클릭 하 여 [리소스 뷰](how-to-create-a-resource-script-file.md#create-resources)합니다.

1. 편집 하 고 두 번 클릭 하려는 문자열을 선택 합니다 **ID**를 **값**, 또는 **캡션** 을 열 수:

   - 선택는 **ID** 에서 합니다 **ID** 드롭 다운 목록 또는 형식은 *ID* 직접에서.

   - 다른 숫자를 입력 합니다 **값** 열입니다.

   - 편집을 입력 합니다 **캡션** 열입니다.

#### <a name="to-change-the-caption-property-of-multiple-string-resources"></a>여러 문자열 리소스의 caption 속성을 변경 하려면

1. 문자열 테이블에서 해당 아이콘을 두 번 클릭 하 여 [리소스 뷰](how-to-create-a-resource-script-file.md#create-resources)합니다.

1. 누른 변경 하려는 문자열을 선택 합니다 **Ctrl** 키를 선택 합니다.

1. 에 [속성 창](/visualstudio/ide/reference/properties-window), 변경할 속성에 대 한 새 값을 입력 합니다.

1. **Enter** 키를 누릅니다.

### <a name="to-add-formatting-or-special-characters-to-a-string-resource"></a>문자열 리소스에 형식 지정 또는 특수 문자를 추가 하려면

1. 문자열 테이블에서 해당 아이콘을 두 번 클릭 하 여 [리소스 뷰](how-to-create-a-resource-script-file.md#create-resources)합니다.

1. 수정 하려는 문자열을 선택 합니다.

1. 에 [속성 창](/visualstudio/ide/reference/properties-window), 표준 이스케이프 시퀀스 아래에 나열 된 텍스트에 추가 합니다 **캡션** 상자 및 키를 누릅니다 **Enter**.

   |이 중...|이 입력...|
   |-----------------|---------------|
   | 줄 바꿈 | \\n |
   | 캐리지 리턴 | \\r |
   | 탭 | \\t |
   | 백슬래시(\\) | \\\\ |
   | ASCII 문자 | \\ddd (8 진수 표기법) |
   | 경고 (벨) | \\a |

   > [!NOTE]
   > 합니다 **문자열 편집기** 이스케이프 ASCI 문자로의 전체 집합을 지원 하지 않습니다. 위에 나열 된만 사용할 수 있습니다.

## <a name="requirements"></a>요구 사항

Win32

## <a name="see-also"></a>참고자료

[리소스 편집기](../windows/resource-editors.md)
[문자열](/windows/desktop/menurc/strings)<br/>
[문자열 정보](/windows/desktop/menurc/about-strings)<br/>
[창 레이아웃 사용자 지정](/visualstudio/ide/customizing-window-layouts-in-visual-studio)