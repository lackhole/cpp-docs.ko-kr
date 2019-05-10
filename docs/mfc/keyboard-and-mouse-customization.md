---
title: 키보드 및 마우스 사용자 지정
ms.date: 11/19/2018
helpviewer_keywords:
- customizations [MFC], keyboard and mouse (MFC Extensions)
- keyboard and mouse customizations (MFC Extensions)
ms.assetid: 1f789f1b-5f2e-4b11-b974-e3e2a2e49d82
ms.openlocfilehash: 55eaac9d800730f3a01dcdb2eef943eb48d147b1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62311158"
---
# <a name="keyboard-and-mouse-customization"></a>키보드 및 마우스 사용자 지정

MFC 응용 프로그램 키보드 및 마우스 입력을 처리 하는 방법을 사용자 지정할 수 있습니다. 사용자 명령에 바로 가기 키를 할당 하 여 키보드 입력을 사용자 지정할 수 있습니다. 사용자가 응용 프로그램의 특정 창 내에서 실행 되어야 하는 명령을 선택 하 여 사용자 마우스 입력 사용자 지정할 수도 있습니다. 이 항목에서는 응용 프로그램에 대 한 입력을 사용자 지정 하는 방법에 설명 합니다.

에 **사용자 지정** 대화 상자에서 마우스 및 키보드에 대 한 사용자 지정 컨트롤을 변경할 수 있습니다. 이 대화 상자를 표시 하려면 사용자를 가리키는 **사용자 지정** 에 **보기** 메뉴를 선택한 다음 클릭 **도구 모음 및 도킹**합니다. 대화 상자에서 사용자가 합니다 **키보드** 탭 또는 **마우스** 탭 합니다.

## <a name="keyboard-customization"></a>키보드 사용자 지정

다음 그림에 표시 합니다 **키보드** 탭의 **사용자 지정** 대화 상자.

![사용자 지정 대화 상자의 키보드 탭](../mfc/media/mfcnextkeyboardtab.png "사용자 지정 대화 상자의 키보드 탭") <br/>
키보드 사용자 지정 탭

명령에 하나 이상의 바로 가기 키를 할당할 키보드 탭을 사용 하 여 사용자 상호 작용 합니다. 사용 가능한 명령 탭의 왼쪽에 나열 됩니다. 사용자 메뉴에서 사용할 수 있는 명령을 선택할 수 있습니다. 바로 가기 키를 사용 하 여 메뉴 명령에만 연결할 수 있습니다. 사용자가 새 바로 가기를 입력 합니다 **할당** 단추가 활성화 됩니다. 사용자가이 단추를 클릭 하면 응용 프로그램 바로 가기 선택한 명령을 연결 합니다.

현재 할당 된 바로 가기 키의 모든 목록 상자 오른쪽 열에 나열 됩니다. 사용자 수 또한 바로 가기 키를 선택 및 하거나 응용 프로그램에 대 한 모든 매핑을 다시 설정 합니다.

응용 프로그램에서 사용자이 지정을 지원 하려는 경우 만들어야 합니다는 [CKeyboardManager](../mfc/reference/ckeyboardmanager-class.md) 개체입니다. 만들려는 `CKeyboardManager` 개체를 함수 호출 [CWinAppEx::InitKeyboardManager](../mfc/reference/cwinappex-class.md#initkeyboardmanager)합니다. 이 메서드를 만들고 키보드 관리자를 초기화 합니다. 키보드 manager를 수동으로 만드는 경우에 호출 해야 `CWinAppEx::InitKeyboardManager` 초기화 합니다.

마법사를 사용 하 여 응용 프로그램을 만드는 마법사에는 키보드 관리자를 초기화 합니다. 키보드 관리자를 초기화 하는 응용 프로그램, 프레임 워크 추가 **키보드** 탭의 **사용자 지정** 대화 상자.

## <a name="mouse-customization"></a>마우스 사용자 지정

다음 그림에 표시 합니다 **마우스** 탭의 **사용자 지정** 대화 상자.

![사용자 지정 대화 상자의 마우스 탭](../mfc/media/mfcnextmousetab.png "사용자 지정 대화 상자의 마우스 탭") <br/>
마우스 사용자 지정 탭

메뉴를 할당 하려면이 탭을 사용 하 여 사용자 상호 작용 명령을 마우스 작업을 두 번 클릭 합니다. 사용자 창의 왼쪽에서 뷰를 선택 하 고 오른쪽의 컨트롤을 사용 하 여 명령을 두 번 클릭 동작을 사용 하 여 연결 합니다. 사용자가 클릭할 **닫기**, 응용 프로그램은 사용자가 보기에서 아무 곳 이나 두 번 클릭할 때마다 연결된 명령을 실행 합니다.

기본적으로 마우스 사용자 지정 마법사를 사용 하 여 응용 프로그램을 만들 때 사용 되지 않습니다.

#### <a name="to-enable-mouse-customization"></a>마우스 사용자 지정을 사용 하도록 설정 하려면

1. 초기화 된 [CMouseManager](../mfc/reference/cmousemanager-class.md) 개체를 호출 하 여 [CWinAppEx::InitMouseManager](../mfc/reference/cwinappex-class.md#initmousemanager)합니다.

1. 사용 하 여 마우스 관리자에 대 한 포인터를 가져올 [CWinAppEx::GetMouseManager](../mfc/reference/cwinappex-class.md#getmousemanager)합니다.

1. 뷰를 사용 하 여 마우스 관리자를 추가 합니다 [CMouseManager::AddView](../mfc/reference/cmousemanager-class.md#addview) 메서드. 마우스 관리자에 추가 하려는 모든 보기에 대 한이 작업을 수행 합니다.

마우스 관리자를 초기화 하는 응용 프로그램, 프레임 워크를 추가 합니다 **마우스** 탭의 **사용자 지정** 대화 상자. 모든 뷰를 추가 하면 탭에 액세스 하면 처리 되지 않은 예외가 발생 합니다. 보기의 목록을 만든 후 합니다 **마우스** 탭은 사용자에 게 제공 합니다.

마우스 관리자에 게 새 보기를 추가 하면 지정 된 고유 id입니다. 창에 대해 지원 되는 마우스 사용자 지정 하려는 경우 WM_LBUTTONDBLCLICK 메시지 및 호출 처리 해야 합니다 [CWinAppEx::OnViewDoubleClick](../mfc/reference/cwinappex-class.md#onviewdoubleclick) 함수입니다. 이 함수를 호출 하면 해당 창에 대 한 ID 매개 변수 중 하나입니다. 것은 ID 번호와 연결 된 개체를 추적 하는 프로그래머의 책임입니다.

## <a name="security-concerns"></a>보안 고려 사항

에 설명 된 대로 [사용자 정의 도구](../mfc/user-defined-tools.md)를 두 번 클릭 이벤트를 사용 하 여 사용자 ID를 사용자 정의 도구를 연결할 수 있습니다. 응용 프로그램에서는 연결 된 ID와 일치 하는 사용자 도구에 대 한 보기를 클릭할 때 응용 프로그램 일치 하는 도구를 발견 하는 경우 도구를 실행 합니다. 응용 프로그램 일치 하는 도구를 찾을 수 없으면, 두 번 클릭 한 보기로 ID 사용 하 여 WM_COMMAND 메시지를 보냅니다.

사용자 지정된 설정은 레지스트리에 저장 됩니다. 레지스트리를 편집 하 여 공격자는 임의 명령을 사용 하 여 올바른 사용자 도구 ID를 바꾸면 됩니다. 뷰를 클릭할 때 뷰를 공격자가 흩어 명령을 처리 합니다. 이 잠재적으로 위험한 예기치 않은 동작이 발생할 수 있습니다.

또한 이러한 종류의 공격에는 사용자 인터페이스 보호 무시할 수 있습니다. 예를 들어, 응용 프로그램에 인쇄를 사용 하지 않도록 설정 합니다. 즉, 해당 사용자 인터페이스에는 **인쇄** 메뉴 및 단추를 사용할 수 없습니다. 일반적으로 이렇게 하면 응용 프로그램의 인쇄 됩니다. 하지만 공격자는 레지스트리를 편집을 하는 경우 사용자 수 이제 수 보낼 인쇄 명령 뷰를 두 번 클릭 하 여 직접 제공 되지 않는 사용자 인터페이스 요소를 무시 하 고.

이러한 종류의 공격 으로부터 보호를 실행 하기 전에 명령을 유효한 지 확인 하려면 응용 프로그램 명령 처리기에 코드를 추가 합니다. 응용 프로그램에 전송 되지 명령을 방지 하기 위해 사용자 인터페이스에 종속 되지 않습니다.

## <a name="see-also"></a>참고자료

[MFC에 대한 사용자 지정](../mfc/customization-for-mfc.md)<br/>
[CKeyboardManager 클래스](../mfc/reference/ckeyboardmanager-class.md)<br/>
[CMouseManager 클래스](../mfc/reference/cmousemanager-class.md)<br/>
[사용자 지정의 보안 의미](../mfc/security-implications-of-customization.md)
