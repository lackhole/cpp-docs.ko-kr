---
title: 'ActiveX 컨트롤 컨테이너: ActiveX 컨트롤 컨테이너에서 ActiveX 컨트롤 프로그래밍'
ms.date: 09/12/2018
helpviewer_keywords:
- ActiveX control containers [MFC], accessing ActiveX controls
- Confirm Classes dialog box
- wrapper classes [MFC], ActiveX controls
- ActiveX control containers [MFC], wrapper classes
- ActiveX controls [MFC], accessing
- MFC ActiveX controls [MFC], accessing in containers
- header files [MFC], for ActiveX control wrapper class
- wrapper classes [MFC], using
- ActiveX controls [MFC], wrapper classes
ms.assetid: ef9b2480-92d6-4191-b16e-8055c4fd7b73
ms.openlocfilehash: eaeb5275ce825272e1c605e7ceeefa24db7a32ab
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62378117"
---
# <a name="activex-control-containers-programming-activex-controls-in-an-activex-control-container"></a>ActiveX 컨트롤 컨테이너: ActiveX 컨트롤 컨테이너에서 ActiveX 컨트롤 프로그래밍

이 문서에 노출 된 액세스를 하기 위한 프로세스를 설명 합니다. [메서드](../mfc/mfc-activex-controls-methods.md) 하 고 [속성](../mfc/mfc-activex-controls-properties.md) 포함 된 ActiveX 컨트롤입니다.

>[!IMPORTANT]
> ActiveX는 새로운 개발에 사용 되지 해야 하는 레거시 기술입니다. ActiveX를 대체 하는 최신 기술에 대 한 자세한 내용은 참조 하세요. [ActiveX 컨트롤](activex-controls.md)합니다.

기본적으로 이러한 단계를 수행 합니다.

1. [ActiveX 컨테이너 프로젝트에 ActiveX 컨트롤 삽입](../mfc/inserting-a-control-into-a-control-container-application.md) 갤러리를 사용 하 여 합니다.

1. [멤버 변수를 정의](../mfc/activex-control-containers-connecting-an-activex-control-to-a-member-variable.md) (또는 다른 형식의 액세스) ActiveX와 동일한 형식의 래퍼 클래스를 제어 합니다.

1. [ActiveX 컨트롤 프로그래밍](#_core_programming_the_activex_control) 미리 정의 된 래퍼 클래스의 멤버 함수를 사용 하 여 합니다.

이 문서에서는 ActiveX 컨트롤 지원 (명명 된 컨테이너) 대화 상자 기반 프로젝트를 만든을 가정 합니다. Circ 샘플 컨트롤을 Circ, 결과 프로젝트에 추가 됩니다.

Circ 컨트롤 (1 단계) 프로젝트에 삽입 되 면 응용 프로그램의 주 대화 상자에 Circ 컨트롤의 인스턴스를 삽입 합니다.

## <a name="procedures"></a>절차

#### <a name="to-add-the-circ-control-to-the-dialog-template"></a>Circ 컨트롤 대화 상자 템플릿을 추가 하려면

1. ActiveX 컨트롤 컨테이너 프로젝트를 로드 합니다. 이 예에서 사용 된 `Container` 프로젝트.

1. 리소스 보기 탭을 클릭 합니다.

1. 엽니다는 **대화 상자** 폴더입니다.

1. 주 대화 상자 템플릿을 두 번 클릭 합니다. 예를 들어 사용 하 여 **IDD_CONTAINER_DIALOG**합니다.

1. 도구 상자에 Circ 컨트롤 아이콘을 클릭 합니다.

1. Circ 컨트롤 삽입 대화 상자 내에서 위치를 클릭 합니다.

1. **파일** 메뉴 선택 **모두 저장** 모든 수정 대화 상자 템플릿에 저장 하려면.

## <a name="modifications-to-the-project"></a>프로젝트 수정

Circ 컨트롤, 시각적 개체에 액세스 하려면 컨테이너 응용 프로그램을 사용 하도록 설정 하려면 C++ 자동으로 래퍼 클래스를 추가 (`CCirc`) 구현 파일 (합니다. CPP)를 컨테이너 프로젝트에 래퍼 클래스 헤더 (합니다. H) 대화 상자 헤더 파일에 파일:

[!code-cpp[NVC_MFC_AxCont#1](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_1.h)]

##  <a name="_core_the_wrapper_class_header_28h29_file"></a> 래퍼 클래스 헤더 (합니다. H)

Get 및 속성을 설정 (및 메서드 호출) Circ 컨트롤용는 `CCirc` 래퍼 클래스는 모든 노출 된 메서드 및 속성의 선언을 제공 합니다. 예제에서는 이러한 선언에에서 있습니다. 가변 원형 8. 다음 예제는 클래스의 부분 `CCirc` ActiveX 컨트롤의 노출 된 인터페이스를 정의 하는:

[!code-cpp[NVC_MFC_AxCont#2](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_2.h)]
[!code-cpp[NVC_MFC_AxCont#3](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_3.h)]

이러한 함수 호출할 수 있습니다 사용 하 여 응용 프로그램의 프로시저의 다른 일반적인 C++ 구문입니다. 컨트롤의 메서드 및 속성 액세스로이 멤버 함수를 사용 하 여에 대 한 자세한 내용은 섹션을 참조 하세요 [ActiveX 컨트롤 프로그래밍](#_core_programming_the_activex_control)합니다.

##  <a name="_core_member_variable_modifications_to_the_project"></a> 프로젝트에 멤버 변수를 수정

ActiveX 컨트롤 프로젝트에 추가 되었으며 대화 상자 컨테이너에 포함 되 면 프로젝트의 다른 부분에서 액세스할 수 있습니다. 가장 쉬운 액세스를 제어 하는 것 [멤버 변수를 만듭니다](../mfc/activex-control-containers-connecting-an-activex-control-to-a-member-variable.md) 대화 상자 클래스의 `CContainerDlg` (2 단계), 즉 Visual 하 여 프로젝트에 추가 하는 래퍼 클래스와 동일한 형식의 C++. 그런 다음 언제 든 지 포함 된 컨트롤에 액세스 하려면 멤버 변수를 사용할 수 있습니다.

경우는 **멤버 변수 추가** 대화 상자를 추가 합니다 *m_circctl* 멤버 프로젝트에 변수를 다음 줄에 추가 헤더 파일 (합니다. H)는 `CContainerDlg` 클래스:

[!code-cpp[NVC_MFC_AxCont#4](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_4.h)]
[!code-cpp[NVC_MFC_AxCont#5](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_5.h)]

또한 호출 **DDX_Control** 이 자동으로 추가 합니다 `CContainerDlg`의 구현의 `DoDataExchange`:

[!code-cpp[NVC_MFC_AxCont#6](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_6.cpp)]

##  <a name="_core_programming_the_activex_control"></a> ActiveX 컨트롤 프로그래밍

이 시점에서 ActiveX 컨트롤을 대화 상자 템플릿에 삽입할 수 있고에 멤버 변수를 생성 합니다. 이제 사용할 수 있습니다 일반 C++ 포함된 된 컨트롤의 메서드 및 속성에 액세스 하는 구문입니다.

설명 했 듯이 (에서 [의 래퍼 클래스 헤더 (합니다. H)](#_core_the_wrapper_class_header_28h29_file)), 헤더 파일 (합니다. H)에 `CCirc` 가변이 사례 원형에서 래퍼 클래스 H, get 및 set 노출 된 속성 값을 사용할 수 있는 멤버 함수의 목록을 포함 합니다. 멤버 함수를 노출 된 메서드를 사용할 수 있습니다.

컨트롤의 속성을 수정 하는 일반적인 위치에는 `OnInitDialog` 주 대화 상자 클래스의 멤버 함수입니다. 이 함수는 대화 상자가 표시 되 고 해당 컨트롤을 포함 하 여 해당 콘텐츠를 초기화 하는 데 사용 됩니다 직전 호출 됩니다.

다음 코드 예제에서는 합니다 *m_circctl* embedded Circ 컨트롤의 캡션 및 CircleShape 속성을 수정 하는 멤버 변수:

[!code-cpp[NVC_MFC_AxCont#7](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_7.cpp)]

## <a name="see-also"></a>참고자료

[ActiveX 컨트롤 컨테이너](../mfc/activex-control-containers.md)
