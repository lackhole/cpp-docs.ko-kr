---
title: '방법: 기호 관리'
ms.date: 02/14/2019
f1_keywords:
- vc.editors.symbol.changing
- vc.editors.symbol.restrictions.name
- vc.editors.symbol.changing.value
- vc.editors.symbol.restrictions.value
- vc.editors.symbol.changing.header
- vc.editors.symbol.changing.unassigned
- vc.editors.symbol.shared.calculated
helpviewer_keywords:
- symbol names
- symbols [C++], names
- restrictions, symbol names
- numeric values
- symbols [C++], numeric values
- numeric values, changing symbols
- symbols [C++], value restrictions
- restrictions, symbol values
- resource files [C++], multiple
- Resource Includes dialog box [C++]
- symbol header files [C++], changing names
- symbols [C++], symbol header files
- Resource.h
- symbols [C++], unassigned
- Change Symbol dialog box [C++]
- unassigned symbols
- symbols [C++], deleting
- symbols [C++], read-only
- symbols [C++], shared
- symbols [C++], calculated
- read-only symbols
- symbol directives
- calculated symbols
- shared symbols
ms.assetid: 26541832-8dba-4177-b642-e08f94502ea7
ms.openlocfilehash: f2edafb0b60cfafcf7ad53b8402ffc39a6fc2f7c
ms.sourcegitcommit: c1f646c8b72f330fa8cf5ddb0f8f261ba10d16f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2019
ms.locfileid: "58328846"
---
# <a name="how-to-manage-symbols"></a>방법: 기호 관리

새 리소스 또는 리소스 개체를 만들 때 개발 환경 기본 기호 이름을 할당, 예를 들어 `IDD_DIALOG1`합니다. 사용할 수는 [속성 창](/visualstudio/ide/reference/properties-window) 기본 기호 이름을 변경 하거나 이미 리소스와 연결 된 기호의 이름을 변경 합니다.

단일 리소스와 연결 된 기호를 사용할 수도 있습니다는 **속성** 기호 값을 변경 하는 창입니다. 사용할 수는 [리소스 기호 대화 상자](../windows/resource-symbols-dialog-box.md) 리소스에 할당 되어 있지 않은 기호의 값을 변경 합니다.

일반적으로 모든 기호 정의에 저장 됩니다 `Resource.h`합니다. 그러나 예를 들어 같은 디렉터리에서 둘 이상의 리소스 파일을 사용할 수 있도록 이 포함 파일 이름을 변경해야 할 수 있습니다.

> [!NOTE]
> 프로젝트에.rc 파일이 없으면 참조 [방법: 리소스 만들기](../windows/how-to-create-a-resource-script-file.md)합니다.

## <a name="symbol-name-restrictions"></a>기호 이름 제한

기호 이름에 대한 제한은 다음과 같습니다.

- 모든 [기호](../windows/symbols-resource-identifiers.md) 헤더 파일에서 기호 정의 충돌을 방지 하기 위해 응용 프로그램의 범위 내에서 고유 해야 합니다.

- 기호 이름에 유효한 문자는 A-Z, a-z, 0-9 및 밑줄(_)입니다.

- 기호 이름은 숫자로 시작할 수 없습니다 하며 247 자로 제한 됩니다.

- 기호 이름에 공백이 없어야 합니다.

- 기호 이름은 대/소문자 구분, 아니지만 첫 번째 기호 정의의 대/소문자는 유지 합니다.

   기호를 정의하는 헤더 파일은 리소스 컴파일러/편집기 및 C++ 프로그램에서 리소스 파일에 정의된 리소스를 참조하는 데 사용됩니다. 대/소문자만 다른 두 기호 이름에 대해 C++ 프로그램은 별도의 두 기호로 보지만 리소스 컴파일러/편집기는 두 이름이 하나의 단일 기호를 나타내는 것으로 봅니다.

> [!NOTE]
> 표준 기호 이름 체계를 따르지 않으면 (아래 keyword 되며 기호 이름이 리소스 스크립트 파일을 빌드하는 동안 리소스 스크립트 컴파일러에 알려진 키워드 하면 임의의 오류가 발생할 때 동일 하도록 진단 하기가 어렵습니다. 이를 방지하려면 표준 이름 지정 체계를 준수하세요.

기호 이름에는 해당 이름이 나타내는 리소스 또는 개체의 종류를 나타내는 설명 접두사가 있습니다. 이러한 설명 접두사는 텍스트 조합 ID로 시작합니다. Microsoft Foundation 클래스 (MFC) 라이브러리 명명 규칙은 다음 표에 표시 된 기호를 사용 합니다.

|범주|접두사|사용|
|--------------|------------|---------|
|자료|IDR_, IDD_, IDC_, IDI_, IDB_|액셀러레이터 키 또는 메뉴 (및 연결 또는 사용자 지정 리소스) 비트맵, 아이콘, 커서, 대화 상자|
|메뉴 항목|ID_|Menu item|
|명령|ID_|명령|
|컨트롤 및 자식 창|IDC_|Control|
|문자열|IDS_|문자열 테이블의 문자열|
|MFC|AFX_|미리 정의된 MFC 기호에 예약됨|

### <a name="to-change-a-symbol-name-id"></a>기호 이름 (ID)를 변경 하려면

1. [리소스 뷰](how-to-create-a-resource-script-file.md#create-resources), 리소스를 선택 합니다.

1. 에 **속성** 창에서 새 기호 이름을 입력 하거나 기존 기호 목록에서 선택 합니다 **ID** 상자입니다.

   새 기호 이름을 입력 하는 경우 값이 자동으로 할당 되기 것입니다.

> [!NOTE]
> 사용할 수는 [리소스 기호 대화 상자](../windows/resource-symbols-dialog-box.md) 리소스에 할당 되지 않은 기호의 이름을 변경할 수 있습니다.

## <a name="symbol-value-restrictions"></a>기호 값 제한

기호 값에 대 한 일반적인 방식으로 표현 된 정수일 수 `#define` 전처리기 지시문입니다. 다음은 기호 값의 몇 가지 예입니다.

```
18
4001
0x0012
-3456
```

액셀러레이터 키, 비트맵, 커서, 대화 상자, 아이콘, 메뉴, 문자열 테이블 및 버전 정보를 0에서 32,767 사이의 10 진수 숫자 여야 16 진수일 수 없습니다 등의 리소스에 대 한 기호 값입니다. 대화 상자 컨트롤이나 문자열 테이블의 개별 문자열 같이 리소스 일부에 대한 기호 값은 0에서 65,534 사이이거나 -32,768에서 32,767 사이일 수 있습니다. 숫자 범위에 대 한 자세한 내용은 참조 하세요. [TN023: 표준 MFC 리소스](../mfc/tn023-standard-mfc-resources.md)합니다.

리소스 기호는 16 비트 숫자입니다. 그러나 부호 있는 숫자나 부호 없는 입력할 수 있습니다, 사용 내부적으로 부호 없는 정수로 음수는 해당 양수 값으로 캐스팅 됩니다 있도록 합니다.

기호 값의 일부 제한은 다음과 같습니다.

- Visual Studio 개발 환경 및 MFC에서는 일부 숫자 범위를 특별한 용도로 사용합니다. 가장 중요한 비트 세트를 사용하는 모든 숫자(부호에 따라 -32,768 ~ -1 또는 32,768 ~ 65,534)는 MFC에 의해 예약되었습니다.

- 다른 기호 문자열을 사용 하 여 기호 값을 정의할 수 없습니다. 예를 들어, 다음과 같은 기호 정의 지원 되지 않습니다.

    ```cpp
    #define IDC_MYEDIT  IDC_OTHEREDIT  //not supported
    ```

- 값 정의로 인수를 사용 하 여 전처리기 매크로 사용할 수 없습니다. 다음 예제에서는 결과 관계 없이 유효한 식이 아님을 `ID` 컴파일 시에 평가 합니다.

    ```cpp
    #define   IDD_ABOUT  ID(7) //not supported
    ```

- 응용 프로그램에 식으로 정의된 기호를 포함하는 기존 파일이 있을 수 있습니다.

### <a name="to-change-a-symbol-value"></a>기호 값을 변경 하려면

1. [리소스 뷰](how-to-create-a-resource-script-file.md#create-resources), 리소스를 선택 합니다.

1. 에 **속성** 창, 형식 기호 이름 뒤에 등호 기호와 정수를 합니다 **ID** 상자 예를 들어:

    ```
    IDC_EDITNAME=5100
    ```

   새 값은 다음에 프로젝트를 저장할 때 기호 헤더 파일에 저장됩니다. 기호 이름만 ID 상자에서에 표시 하는 상태로 유지 됩니다 하 고 유효성을 검사 하는 등호와 값을 표시 되지 않습니다.

## <a name="change-or-delete-symbols"></a>변경 또는 삭제 기호

에 있는 동안 합니다 [리소스 기호 대화 상자](../windows/resource-symbols-dialog-box.md), 편집 하거나 이미 리소스 또는 개체에 할당 되지 않은 기존 기호를 삭제할 수 있습니다.

### <a name="to-change-an-unassigned-symbol"></a>할당되지 않은 기호를 변경하려면

1. 에 **이름을** 상자, 할당 되지 않은 기호를 선택 하 고 선택 **변경**합니다.

1. 기호 이름 또는 값에 제공 된 상자에서 편집 합니다 **기호 변경** 대화 상자.

> [!NOTE]
> 리소스 또는 개체에 할당 되는 기호를 변경 하려면 리소스 편집기를 사용 해야 하거나 **속성** 창입니다.

### <a name="to-delete-an-unassigned-unused-symbol"></a>할당되지 않은(사용되지 않은) 기호를 삭제하려면

에 **리소스 기호** 대화 상자에서 기호를 삭제 하 고 선택 하려는 선택 **삭제**합니다.

> [!NOTE]
> 리소스 파일에는 사용 되지 않은 기호를 삭제 하기 전에 컴파일 시간에 포함 된 리소스 파일 또는 프로그램의 다른 곳에서 사용 되지 않습니다 해야 합니다.

## <a name="include-symbols"></a>기호를 포함 합니다.

다른 응용 프로그램에서 만든 리소스 파일을 처음으로 개발 환경에서 읽는 경우 포함된 헤더 파일을 모두 읽기 전용으로 표시합니다. 사용할 수 있지만 합니다 [리소스 내용 대화 상자](../windows/resource-includes-dialog-box.md) 추가 읽기 전용 기호 헤더 파일을 추가 합니다.

읽기 전용 기호 정의를 사용하려는 한 가지 이유는 여러 프로젝트에서 공유하려고 하는 기호 파일 때문입니다.

또한 단순 정수 대신 식을 사용하여 기호 값을 정의하는 기호 정의를 사용하는 기존 리소스가 있는 경우에 포함된 기호 파일을 사용할 수 있습니다. 예를 들어:

```cpp
#define   IDC_CONTROL1 2100
#define   IDC_CONTROL2 (IDC_CONTROL1+1)
```

다음과 같은 경우 환경에서 이러한 계산된 기호를 올바르게 해석합니다.

- 계산된 기호가 읽기 전용 기호 파일에 배치됩니다.

- 리소스 파일에 이러한 계산된 기호가 이미 할당된 리소스가 포함되어 있습니다.

- 숫자 식이 필요합니다.

> [!NOTE]
> 문자열이나 숫자 식이 필요한 경우에는 식이 계산되지 않습니다.

### <a name="to-include-shared-read-only-symbols-in-your-resource-file"></a>리소스 파일에 공유(읽기 전용) 기호를 포함하려면

1. [리소스 뷰](how-to-create-a-resource-script-file.md#create-resources)를 마우스 오른쪽 단추로 클릭 하 *.rc* 파일을 선택 [리소스 내용](../windows/resource-includes-dialog-box.md)합니다.

1. 에 **읽기 전용 기호 지시문** 상자를 사용 하 여는 `#include` 컴파일러 지시문을 읽기 전용 기호를 저장할 파일을 지정 합니다.

   파일을 호출 하지 마십시오 `Resource.h`주 기호 헤더 파일에서 일반적으로 사용 하는 파일 이름 이므로, 합니다.

   > [!NOTE]
   > 에 입력 합니다 **읽기 전용 기호 지시문** 입력 한 대로 정확 하 게 리소스 파일에 포함 됩니다. 입력한 내용에 맞춤법이나 구문 오류가 없는지 확인하세요.

   사용 된 **읽기 전용 기호 지시문** 상자 기호 정의가 있는 파일을 포함 합니다. 리소스 정의 포함 하지 않습니다, 그리고 파일을 저장 하는 경우 다른 중복 된 리소스 정의가 생성 됩니다.

1. 지정한 파일에 기호를 배치합니다.

   이러한 방식으로 포함 된 파일의 기호는 리소스 파일을 열 때마다 평가 됩니다 있지만 파일을 저장할 때 디스크에서 교체 되지 않습니다.

1. **확인**을 선택합니다.

### <a name="to-change-the-name-of-the-resource-symbol-header-file"></a>리소스 기호 헤더 파일의 이름을 변경하려면

1. [리소스 뷰](how-to-create-a-resource-script-file.md#create-resources)를 마우스 오른쪽 단추로 클릭 하 *.rc* 파일을 선택 [리소스 내용](../windows/resource-includes-dialog-box.md)합니다.

1. 에 **기호 헤더 파일** 포함 파일에 대 한 새 이름을 입력 합니다.

## <a name="requirements"></a>요구 사항

Win32

## <a name="see-also"></a>참고 항목

[리소스 식별자(기호)](../windows/symbols-resource-identifiers.md)<br/>
[방법: 기호 만들기](../windows/creating-new-symbols.md)<br/>
[미리 정의된 기호 ID](../windows/predefined-symbol-ids.md)<br/>