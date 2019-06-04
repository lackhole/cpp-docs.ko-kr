---
title: ATL DHTML 컨트롤 수정
ms.date: 11/04/2016
helpviewer_keywords:
- HTML controls, modifying
- DHTML controls
- DHTML controls, modifying
ms.assetid: c053f35f-8629-4600-9595-721f5956777a
ms.openlocfilehash: e594360cc6752a60bf2e07a1fb1d02041604d959
ms.sourcegitcommit: ecf274bcfe3a977c48745aaa243e5e731f1fdc5f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2019
ms.locfileid: "66503001"
---
# <a name="modifying-the-atl-dhtml-control"></a>ATL DHTML 컨트롤 수정

ATL 컨트롤 마법사 줄어들고 시작 코드 빌드를 컨트롤에 실행 메서드를 프로젝트 파일에 작성 되는 방법 및 DHTML 컨트롤의를 호출 하는 방법을 볼 수 있도록 C++ 디스패치 메서드를 사용 하는 코드입니다. 인터페이스에 디스패치 메서드를 추가할 수 있습니다. 그런 다음 HTML 리소스에서 메서드를 호출할 수 있습니다.

## <a name="to-modify-the-atl-dhtml-control"></a>ATL DHTML 컨트롤 수정

1. **클래스 뷰**을 컨트롤 프로젝트를 확장 합니다.

   "UI"로 끝나는 인터페이스에 한 가지 방법은 `OnClick`합니다. "UI"로 끝나지 않는 인터페이스는 메서드는 없습니다.

1. 라는 메서드를 추가 `MethodInvoked` "UI입니다."로 끝나지 않는 인터페이스

   이 메서드는 컨트롤과 상호 작용에 DHTML에서 사용 하는 인터페이스 필요가 컨테이너 상호 작용에 대 한 컨트롤 컨테이너에 사용 되는 인터페이스에 추가 됩니다. 컨테이너만이 메서드를 호출할 수 있습니다.

1. .Cpp 파일에서 인 메서드를 찾아 예를 들어 메시지 상자를 표시 하는 코드를 추가 합니다.

   [!code-cpp[NVC_ATL_COM#5](../atl/codesnippet/cpp/modifying-the-atl-dhtml-control_1.cpp)]

1. 다른 메서드 호출 추가 `HelloHTML`,이 시간에만 "U"를 선택 합니다. 종료 하는 인터페이스에 추가 스텁 하는지 알 `HelloHTML` 메서드는.cpp에서 파일과 예를 들어 메시지 상자를 표시 하는 코드를 추가 합니다.

   [!code-cpp[NVC_ATL_COM#6](../atl/codesnippet/cpp/modifying-the-atl-dhtml-control_2.cpp)]

1. 세 번째 메서드를 추가 `GoToURL`를 인터페이스에 끝나지 "U"를 선택 합니다. 이 메서드를 호출 하 여 구현 [IWebBrowser2::Navigate](/previous-versions//aa752133\(v=vs.85\))다음과 같이 합니다.

   [!code-cpp[NVC_ATL_COM#7](../atl/codesnippet/cpp/modifying-the-atl-dhtml-control_3.cpp)]

   사용할 수는 `IWebBrowser2` 메서드 ATL.h 파일에서 해당 인터페이스에 대 한 포인터를 제공 하기 때문입니다.

그런 다음 만든 메서드를 호출 하는 HTML 리소스를 수정 합니다. 이러한 메서드를 호출 하는 것에 대 한 세 개의 단추를 추가 합니다.

## <a name="to-modify-the-html-resource"></a>HTML 리소스를 수정 하려면

1. **솔루션 탐색기**, HTML 리소스를 표시할.htm 파일을 두 번 클릭 합니다.

   HTML, 특히에 대 한 호출 외부 Windows 디스패치 메서드를 검사 합니다. 프로젝트를 호출 하는 HTML `OnClick` 메서드 및 매개 변수를 나타내는 컨트롤의 본문 (`theBody`) 및 할당할 색 ("`red`"). 다음 메서드 호출의 텍스트는 단추에 표시 되는 레이블입니다.

1. 다른 추가 `OnClick` 메서드를 색을 변경만 합니다. 예를 들어:

    ```html
    <br>
    <br>
    <BUTTON onclick='window.external.OnClick(theBody, "white");'>Refresh</BUTTON>
    ```

   이 메서드는 레이블이 붙은 단추를 만듭니다 **새로 고침**, 원래, 흰색 배경에 컨트롤을 반환 하는 사용자가 클릭할 수 있습니다.

1. 에 대 한 호출을 추가 합니다 `HelloHTML` 만든 메서드. 예를 들어:

    ```html
    <br>
    <br>
    <BUTTON onclick='window.external.HelloHTML();'>HelloHTML</BUTTON>
    ```

   이 메서드는 레이블이 붙은 단추를 만듭니다 **HelloHTML**, 사용자가 클릭 하 여 표시할 수 있는 `HelloHTML` 메시지 상자입니다.

이제 빌드할 수 있습니다 하 고 [수정 된 DHTML 컨트롤 테스트](../atl/testing-the-modified-atl-dhtml-control.md)합니다.

## <a name="see-also"></a>참고자료

[DHTML 컨트롤에 대 한 지원](../atl/atl-support-for-dhtml-controls.md)
