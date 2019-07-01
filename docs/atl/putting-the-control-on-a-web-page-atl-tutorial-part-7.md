---
title: 웹 페이지에 컨트롤 배치(ATL 자습서, 7부)
ms.custom: get-started-article
ms.date: 05/06/2019
ms.assetid: 50dc4c95-c95b-4006-b88a-9826f7bdb222
ms.openlocfilehash: db6dcc57ff9f3748d802e76617ef18dea8f9506c
ms.sourcegitcommit: 6cf0c67acce633b07ff31b56cebd5de3218fd733
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/24/2019
ms.locfileid: "67344353"
---
# <a name="putting-the-control-on-a-web-page-atl-tutorial-part-7"></a>웹 페이지에 컨트롤 배치(ATL 자습서, 7부)

컨트롤이 이제 완료 되었습니다. 실제 상황에서 컨트롤 작업을 보려면 웹 페이지에 배치 합니다. 컨트롤이 포함 된 HTML 파일에는 컨트롤을 정의할 때 생성 되었습니다. PolyCtl.htm 파일을 엽니다 **솔루션 탐색기**, 웹 페이지에 컨트롤을 볼 수 있습니다.

이 단계에서는 기능 컨트롤을 추가 하 고 이벤트에 응답 하도록 웹 페이지를 스크립팅 합니다. 안전 컨트롤 것 Internet Explorer가 컨트롤을 수정할 수 있습니다.

## <a name="adding-new-functionality"></a>새 기능 추가

### <a name="to-add-control-features"></a>제어 기능을 추가 하려면

1. PolyCtl.cpp를 열고 다음 코드를 바꿉니다.

    ```cpp
    if (PtInRegion(hRgn, xPos, yPos))
        Fire_ClickIn(xPos, yPos);
    else
        Fire_ClickOut(xPos, yPos);
    ```

    다음 문자열로 바꾸세요.

    ```cpp
    short temp = m_nSides;
    if (PtInRegion(hRgn, xPos, yPos))
    {
        Fire_ClickIn(xPos, yPos);
        put_Sides(++temp);
    }
    else
    {
        Fire_ClickOut(xPos, yPos);
        put_Sides(--temp);
    }
    ```

이제 셰이프 추가 하거나 클릭 하는 위치에 따라 양쪽 제거 됩니다.

## <a name="scripting-the-web-page"></a>웹 페이지 스크립팅

컨트롤 하지 수행할 아직 따라서 전송 되는 이벤트에 응답 하도록 웹 페이지를 변경 합니다.

### <a name="to-script-the-web-page"></a>웹 페이지 스크립팅

1. PolyCtl.htm을 열고 HTML 뷰를 선택 합니다. HTML 코드에 다음 줄을 추가 합니다. 다음 추가 합니다 `</OBJECT>` 하기 전에 `</BODY>`입니다.

    ```html
    <SCRIPT LANGUAGE="VBScript">
    <!--
        Sub PolyCtl_ClickIn(x, y)
            MsgBox("Clicked (" & x & ", " & y & ") - adding side")
        End Sub
        Sub PolyCtl_ClickOut(x, y)
            MsgBox("Clicked (" & x & ", " & y & ") - removing side")
        End Sub
    -->
    </SCRIPT>
    ```

1. HTM 파일을 저장 합니다.

컨트롤에서 면 속성을 가져오고는 VBScript 코드를 추가 했습니다. 컨트롤 내부를 클릭 하면 변 수가 1 씩 증가 합니다. 컨트롤의 바깥쪽을 클릭 하면 변 수가 하나씩 줄어듭니다.

## <a name="indicating-that-the-control-is-safe-for-scripting"></a>스크립트에 안전한 컨트롤 임을 나타내는

Internet Explorer에만 컨트롤을 사용 하 여 웹 페이지를 볼 수 있습니다. 다른 브라우저는 더 이상 보안 약점 인해 ActiveX 컨트롤을 지원합니다.

> [!NOTE]
> 컨트롤이 표시되지 않는 경우 일부 브라우저에 ActiveX 컨트롤을 실행할 설정을 조정해야 합니다. ActiveX 컨트롤을 사용 하는 방법에 대 한 브라우저 설명서를 참조 하십시오.

현재 Internet Explorer 보안 설정에 따라 보안 경고 대화 상자가 나타날 수 있습니다. 이 제안에 따르면 컨트롤 스크립트에 안전 하지 않을 하 수 손상 됩니다. 예를 들어, 파일을 표시 하지만 또한 컨트롤을 설치한 경우는 `Delete` 파일을 삭제 하는 메서드를 안전 하 게 되 면 될 수만 페이지에서 볼 수 있습니다. 것은 스크립트에 안전 하므로 사용자가 호출할 수는 `Delete` 메서드.

> [!IMPORTANT]
> 이 자습서에서는 안전으로 표시 된 ActiveX 컨트롤을 실행 하려면 Internet Explorer에서 보안 설정을 변경할 수 있습니다. 제어판에서 클릭 **인터넷 속성** 클릭 **보안** 적절 한 설정을 변경할 수 있습니다. 이 자습서를 완료 하는 경우 원래 상태로 다시 보안 설정을 변경 합니다.

프로그래밍 방식으로이 특정 컨트롤에 대 한 보안 경고 대화 상자를 표시할 필요가 없다는 것 Internet Explorer을 알릴 수 있습니다. 사용 하 여 수행할 수 있습니다는 `IObjectSafety` 인터페이스입니다. 클래스에서이 인터페이스의 구현을 제공 하는 ATL [IObjectSafetyImpl](../atl/reference/iobjectsafetyimpl-class.md)합니다. 컨트롤에 인터페이스를 추가 하려면 추가 `IObjectSafetyImpl` 상속 된 클래스의 목록에 고 COM 맵에에 대 한 항목을 추가 합니다.

### <a name="to-add-iobjectsafetyimpl-to-the-control"></a>컨트롤에 IObjectSafetyImpl을 추가 하려면

1. PolyCtl.h의 상속 된 클래스 목록 끝에 다음 줄을 추가 하 고 이전 줄에 쉼표를 추가 합니다.

    [!code-cpp[NVC_ATL_Windowing#62](../atl/codesnippet/cpp/putting-the-control-on-a-web-page-atl-tutorial-part-7_1.h)]

1. 다음 줄을 PolyCtl.h의 COM 맵에 추가:

    [!code-cpp[NVC_ATL_Windowing#63](../atl/codesnippet/cpp/putting-the-control-on-a-web-page-atl-tutorial-part-7_2.h)]

## <a name="building-and-testing-the-control"></a>컨트롤 빌드 및 테스트

컨트롤을 빌드하십시오. 빌드가 완료 되 면 PolyCtl.htm를 다시 브라우저 보기에서 엽니다. 이 이번에는 웹 페이지가 표시 되도록 하지 않고 직접 합니다 **보안 경고** 대화 상자. 다각형 내부를 클릭 하면 변 수가 하나 증가 합니다. 면의 수를 줄이기 위해 다각형 외부를 클릭 합니다.

[6 단계로 돌아가기](../atl/adding-a-property-page-atl-tutorial-part-6.md)

## <a name="next-steps"></a>다음 단계

이 단계도 ATL 자습서를 마칩니다. ATL에 대 한 자세한 정보 링크에 대 한 참조를 [ATL 시작 페이지](../atl/active-template-library-atl-concepts.md)합니다.

## <a name="see-also"></a>참고자료

[자습서](../atl/active-template-library-atl-tutorial.md)
