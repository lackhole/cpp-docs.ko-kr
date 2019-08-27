---
title: 'MFC ActiveX 컨트롤: 고급 항목'
ms.date: 09/12/2018
helpviewer_keywords:
- MFC ActiveX controls [MFC], error codes
- MFC ActiveX controls [MFC], accessing invisible dialog controls
- MFC ActiveX controls [MFC], advanced topics
- FireError method [MFC]
- MFC ActiveX controls [MFC], database classes
- MFC ActiveX controls [MFC], special keys
- PreTranslateMessage method [MFC]
- MFC ActiveX controls [MFC], parameterized property
- ThrowError method [MFC]
ms.assetid: e9e34abb-8e2d-461e-bb9c-a1aec5dcecbd
ms.openlocfilehash: df71e2e59763644bd4aefb5d3e3afa46f82f538a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62392715"
---
# <a name="mfc-activex-controls-advanced-topics"></a>MFC ActiveX 컨트롤: 고급 항목

이 문서에서는 ActiveX 컨트롤을 개발 하는 관련 된 고급 항목을 다룹니다. 여기에는 다음이 포함됩니다.

- [ActiveX 컨트롤의 데이터베이스 클래스 사용](#_core_using_database_classes_in_activex_controls)

- [매개 변수화 된 속성 구현](#_core_implementing_a_parameterized_property)

- [ActiveX 컨트롤에서 오류 처리](#_core_handling_errors_in_your_activex_control)

- [컨트롤에서 특수 키를 처리합니다.](#_core_handling_special_keys_in_your_control)

- [런타임 시 표시 되는 대화 상자 컨트롤 액세스](#_core_accessing_dialog_controls_that_are_invisible_at_run_time)

>[!IMPORTANT]
> ActiveX는 새로운 개발에 사용 되지 해야 하는 레거시 기술입니다. ActiveX를 대체 하는 최신 기술에 대 한 자세한 내용은 참조 하세요. [ActiveX 컨트롤](activex-controls.md)합니다.

##  <a name="_core_using_database_classes_in_activex_controls"></a> ActiveX 컨트롤의 데이터베이스 클래스 사용

ActiveX 컨트롤 클래스는 클래스 라이브러리의 일부 이기 때문에 동일한 절차 및 데이터베이스 클래스를 사용 하 여 MFC 데이터베이스 클래스를 사용 하는 ActiveX 컨트롤을 개발 하는 표준 MFC 응용 프로그램에서에 대 한 규칙을 적용할 수 있습니다.

MFC 데이터베이스 클래스의 일반적인 개요를 참조 하세요 [MFC 데이터베이스 클래스 (DAO 및 ODBC)](../data/mfc-database-classes-odbc-and-dao.md)합니다. 문서 MFC ODBC 클래스를 소개 하 고 MFC DAO 클래스 및 중 하나에 대 한 자세한 내용은 알려 줍니다.

> [!NOTE]
>  시각적 개체 C++ 환경 및 마법사 지원 하지 않습니다 DAO (하지만 DAO 클래스에 포함 되어 있으며 계속 사용할 수 있습니다). 사용 하는 것이 좋습니다 [OLE DB Templates](../data/oledb/ole-db-programming.md) 하거나 [ODBC 및 MFC](../data/odbc/odbc-and-mfc.md) 새 프로젝트에 대 한 합니다. DAO 기존 응용 프로그램 유지 관리에 사용 해야 합니다.

##  <a name="_core_implementing_a_parameterized_property"></a> 매개 변수화 된 속성 구현

매개 변수화 된 속성 (속성 배열 라고도 함)는 컨트롤의 단일 속성으로 값의 유형이 같은 컬렉션을 노출 하는 것에 대 한 메서드입니다. 예를 들어, 배열 또는 사전 속성으로 노출 하도록 매개 변수화 된 속성을 사용할 수 있습니다. Visual basic에서는 이러한 속성은 배열 표기법을 사용 하 여 액세스 합니다.

[!code-vb[NVC_MFC_AxVb#1](../mfc/codesnippet/visualbasic/mfc-activex-controls-advanced-topics_1.vb)]

속성 추가 마법사를 사용 하 여 매개 변수화 된 속성을 구현 합니다. 속성 추가 마법사 컨트롤 사용자가 위 표기법을 사용 하 여 속성에 액세스 하도록 허용 하는 Get/Set 함수 또는 표준 방식으로 쌍을 추가 하 여 속성을 구현 합니다.

비슷한 메서드 및 속성을 매개 변수화 된 속성에 허용 되는 매개 변수의 수에 제한이 수도 있습니다. 매개 변수화 된 속성의 경우 제한은 15 매개 변수 (하나의 매개 변수 속성 값을 저장 하는 것에 대 한 예약 된)입니다.

다음 절차는 정수의 2 차원 배열로 액세스할 수 있는 배열 이라는 매개 변수화 된 속성을 추가 합니다.

#### <a name="to-add-a-parameterized-property-using-the-add-property-wizard"></a>속성 추가 마법사를 사용 하 여 매개 변수가 있는 속성을 추가 하려면

1. 컨트롤의 프로젝트를 로드합니다.

1. 클래스 뷰에서 컨트롤의 라이브러리 노드를 확장합니다.

1. 컨트롤의 인터페이스 노드(라이브러리 노드의 두 번째 노드)를 마우스 오른쪽 단추로 클릭하여 바로 가기 메뉴를 엽니다.

1. 바로 가기 메뉴에서 클릭 **추가** 을 클릭 한 다음 **속성 추가**합니다.

1. 에 **속성 이름이** 상자에 입력 `Array`합니다.

1. 에 **속성 형식** 상자에서 **짧은**합니다.

1. 에 대 한 **구현** 유형을 클릭 **Get/Set 메서드가**합니다.

1. 에 **Get 함수가** 및 **설정 함수** 상자, Get 및 Set 함수의 고유 이름을 입력 하거나 기본 이름을 적용 합니다.

9. 호출 매개 변수를 추가 *행* (형식 *짧은*)를 사용 하 여 합니다 **매개 변수 이름** 및 **매개 변수 형식** 컨트롤입니다.

10. 두 번째 매개 변수를 추가 *열* (형식 *짧은*).

11. **마침**을 클릭합니다.

### <a name="changes-made-by-the-add-property-wizard"></a>변경 된 속성 추가 마법사

사용자 지정 속성에 추가 하면 속성 추가 마법사 변경한 컨트롤 클래스 헤더 (합니다. H) 및 구현 (합니다. CPP) 파일입니다.

다음 줄은 컨트롤 클래스에 추가 됩니다. H 파일:

[!code-cpp[NVC_MFC_AxUI#35](../mfc/codesnippet/cpp/mfc-activex-controls-advanced-topics_2.h)]

이 코드 라는 두 개의 함수를 선언 `GetArray` 고 `SetArray` 사용자 속성에 액세스 하는 경우 특정 행과 열을 요청할 수 있도록 합니다.

속성 추가 마법사 컨트롤 클래스 구현에 있는 컨트롤 디스패치 맵에 다음 줄을 추가 하는 또한 (합니다. Cpp) 됩니다.

[!code-cpp[NVC_MFC_AxUI#36](../mfc/codesnippet/cpp/mfc-activex-controls-advanced-topics_3.cpp)]

마지막으로 구현 합니다 `GetArray` 및 `SetArray` 함수 끝에 추가 되는 합니다. CPP 파일입니다. 대부분의 경우에서 속성의 값을 반환 하는 Get 함수를 수정 합니다. Set 함수에는 대개 전이나 속성이 변경 된 후 실행 해야 하는 코드가 포함 됩니다.

유용 하 게이 속성에 대 한 형식의 컨트롤 클래스에 2 차원 배열 멤버 변수를 선언할 수 있습니다 **짧은**매개 변수가 있는 속성에 대 한 값을 저장 합니다. 그런 다음 매개 변수로 표시 된 대로 적절 한 행과 열에 저장 된 값을 반환 하는 Get 함수를 수정 하 고 행 및 열 매개 변수에서 참조 하는 값을 업데이트 하는 집합 함수를 수정할 수 없습니다.

##  <a name="_core_handling_errors_in_your_activex_control"></a> ActiveX 컨트롤에서 오류 처리

컨트롤에서 오류 조건이 발생 하는 경우 컨트롤 컨테이너에 오류를 보고 하는 것이 해야 합니다. 오류가 발생 하는 상황에 따라 오류를 보고 하는 방법은 두 가지가 있습니다. 오류가 발생 하는 경우 속성의 Get 또는 함수를 설정 하거나 OLE Automation 메서드의 구현 내에서 컨트롤을 호출 해야 [COleControl::ThrowError](../mfc/reference/colecontrol-class.md#throwerror), 오류가 발생 하는 컨트롤 사용자에 게는 신호입니다. 컨트롤을 언제 든 지 오류가 발생 하는 경우 호출 [COleControl::FireError](../mfc/reference/colecontrol-class.md#fireerror), 주식 오류 이벤트를 발생 하는 합니다.

발생 한 오류의 종류를 나타내기 컨트롤 오류 코드를 전달 해야 합니다 `ThrowError` 또는 `FireError`합니다. 오류 코드는 32 비트 값에는 OLE 상태 코드입니다. 가능한 경우 오류 코드는 OLECTL에 정의 된 코드의 표준 집합에서 선택 합니다. H 헤더 파일입니다. 다음 표에서 이러한 코드를 보여 줍니다.

### <a name="activex-control-error-codes"></a>ActiveX 컨트롤 오류 코드

|Error|설명|
|-----------|-----------------|
|CTL_E_ILLEGALFUNCTIONCALL|잘못 된 함수 호출|
|CTL_E_OVERFLOW|오버플로|
|CTL_E_OUTOFMEMORY|메모리 부족|
|CTL_E_DIVISIONBYZERO|0으로 나누기|
|CTL_E_OUTOFSTRINGSPACE|문자열 공간이 부족 합니다.|
|CTL_E_OUTOFSTACKSPACE|스택 공간이 부족 합니다.|
|CTL_E_BADFILENAMEORNUMBER|파일 이름 또는 번호가 잘못되었습니다.|
|CTL_E_FILENOTFOUND|파일이 없습니다.|
|CTL_E_BADFILEMODE|파일 모드가 잘못되었습니다.|
|CTL_E_FILEALREADYOPEN|파일이 이미 열려 있습니다.|
|CTL_E_DEVICEIOERROR|디바이스 입/출력(I/O) 오류입니다.|
|CTL_E_FILEALREADYEXISTS|파일이 이미 있습니다.|
|CTL_E_BADRECORDLENGTH|레코드 길이가 잘못되었습니다.|
|CTL_E_DISKFULL|디스크가 꽉 찼습니다.|
|CTL_E_BADRECORDNUMBER|레코드 개수가 잘못되었습니다.|
|CTL_E_BADFILENAME|잘못 된 파일 이름|
|CTL_E_TOOMANYFILES|파일이 너무 많습니다.|
|CTL_E_DEVICEUNAVAILABLE|디바이스를 사용할 수 없습니다.|
|CTL_E_PERMISSIONDENIED|사용 권한이 거부됨|
|CTL_E_DISKNOTREADY|디스크가 준비되지 않았습니다.|
|CTL_E_PATHFILEACCESSERROR|경로/파일 액세스 오류입니다.|
|CTL_E_PATHNOTFOUND|경로를 찾을 수 없습니다.|
|CTL_E_INVALIDPATTERNSTRING|잘못된 패턴 문자열|
|CTL_E_INVALIDUSEOFNULL|잘못 된 NULL 사용|
|CTL_E_INVALIDFILEFORMAT|잘못 된 파일 형식|
|CTL_E_INVALIDPROPERTYVALUE|잘못 된 속성 값|
|CTL_E_INVALIDPROPERTYARRAYINDEX|잘못 된 속성 배열 인덱스|
|CTL_E_SETNOTSUPPORTEDATRUNTIME|Set은 런타임에 지원되지 않습니다.|
|CTL_E_SETNOTSUPPORTED|Set은 지원되지 않습니다(읽기 전용 속성).|
|CTL_E_NEEDPROPERTYARRAYINDEX|속성 배열 인덱스가 필요합니다.|
|CTL_E_SETNOTPERMITTED|Set은 허용되지 않습니다.|
|CTL_E_GETNOTSUPPORTEDATRUNTIME|Get은 런타임에 지원되지 않습니다.|
|CTL_E_GETNOTSUPPORTED|Get은 지원되지 않습니다(쓰기 전용 속성).|
|CTL_E_PROPERTYNOTFOUND|속성을 찾을 수 없습니다.|
|CTL_E_INVALIDCLIPBOARDFORMAT|클립보드 형식이 잘못 되었습니다|
|CTL_E_INVALIDPICTURE|그림이 잘못 되었습니다.|
|CTL_E_PRINTERERROR|프린터 오류|
|CTL_E_CANTSAVEFILETOTEMP|파일을 TEMP에 저장할 수 없습니다.|
|CTL_E_SEARCHTEXTNOTFOUND|검색 텍스트를 찾을 수 없습니다.|
|CTL_E_REPLACEMENTSTOOLONG|대체 텍스트가 너무 깁니다.|

필요한 경우 표준 코드 중 하나에서 다루지 않는 조건에 대 한 사용자 지정 오류 코드를 정의 하려면 CUSTOM_CTL_SCODE 매크로 사용 합니다. 이 매크로 매개 변수가 1000 사이의 정수 여야 합니다.과 32767을 포함 합니다. 예를 들어:

[!code-cpp[NVC_MFC_AxUI#37](../mfc/codesnippet/cpp/mfc-activex-controls-advanced-topics_4.cpp)]

기존 VBX 컨트롤을 대체 하기 위해 ActiveX 컨트롤을 만드는 경우 VBX 컨트롤이 오류 코드 호환 되는지 확인 하는 데 사용 하 여 동일한 숫자 값을 사용 하 여 ActiveX 컨트롤 오류 코드에 정의 합니다.

##  <a name="_core_handling_special_keys_in_your_control"></a> 컨트롤에서 특수 키를 처리합니다.

일부 경우에 특정 키 입력 조합을; 특별 한 방식에서으로 처리 하려는 insert 여러 줄 텍스트에서 ENTER 키를 누르면 새 줄 상자 컨트롤 또는 편집 그룹 간에 이동할 때 방향을 제어 하는 예를 들어 키 누름 ID입니다.

ActiveX 컨트롤의 기본 클래스가 `COleControl`를 재정의할 수 있습니다 [cwnd:: Pretranslatemessage](../mfc/reference/cwnd-class.md#pretranslatemessage) 컨테이너 처리 되기 전에 메시지를 처리 하 합니다. 이 기법을 사용 하는 경우 항상 반환 **TRUE** 의 재정의에서 메시지를 처리 하는 경우 `PreTranslateMessage`합니다.

다음 코드 예제에 있는 방향 키와 관련 된 모든 메시지를 처리 하는 한 가지 방법을 보여 줍니다.

[!code-cpp[NVC_MFC_AxUI#38](../mfc/codesnippet/cpp/mfc-activex-controls-advanced-topics_5.cpp)]

ActiveX 컨트롤에 대 한 키보드 인터페이스를 처리 하는 방법은 ActiveX SDK 설명서를 참조 하세요.

##  <a name="_core_accessing_dialog_controls_that_are_invisible_at_run_time"></a> 런타임 시 표시 되는 대화 상자 컨트롤 액세스

사용자 인터페이스가 없는 없고 런타임에 표시 되지 않은 대화 상자 컨트롤을 만들 수 있습니다. 대화 상자를 사용 하 여 런타임에 ActiveX 컨트롤을 보이지 않는 추가 하는 경우 [cwnd:: Getdlgitem](../mfc/reference/cwnd-class.md#getdlgitem) 컨트롤에 액세스 하려면 컨트롤이 제대로 작동 하지 것입니다. 대신 컨트롤을 나타내는 개체를 가져오려면 다음 방법 중 하나를 사용 해야 있습니다.

- 멤버 변수 추가 마법사를 사용 하 여 선택할 **제어 변수** 를 선택한 다음 컨트롤의 id입니다. 멤버 변수 이름을 입력 하 고 컨트롤의 래퍼 클래스를 선택 합니다 **컨트롤 형식**합니다.

     또는

- 대화 상자 항목으로 지역 변수 및 하위 클래스를 선언 합니다. 다음과 유사한 코드를 삽입 (`CMyCtrl` 래퍼 클래스인 IDC_MYCTRL1은 컨트롤의 ID):

   [!code-cpp[NVC_MFC_AxCont#19](../mfc/codesnippet/cpp/mfc-activex-controls-advanced-topics_6.cpp)]

## <a name="see-also"></a>참고자료

[MFC ActiveX 컨트롤](../mfc/mfc-activex-controls.md)
