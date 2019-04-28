---
title: 그리기 코드 변경(ATL 자습서, 4부)
ms.custom: get-started-article
ms.date: 09/26/2018
helpviewer_keywords:
- _ATL_MIN_CRT macro
ms.assetid: 08ff14e8-aa49-4139-a110-5d071939cf1e
ms.openlocfilehash: 6ea7a0ae0c0a9be87fe507e6b934bd046c9ffe4e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62250829"
---
# <a name="changing-the-drawing-code-atl-tutorial-part-4"></a>그리기 코드 변경(ATL 자습서, 4부)

기본적으로 컨트롤의 그리기 코드 표시 텍스트와 사각형 **PolyCtl**합니다. 이 단계에서는 좀 더 흥미로운 표시 하는 코드를 변경 됩니다. 다음 작업은 다음과 같습니다.

- 헤더 파일을 수정

- 수정 된 `OnDraw` 함수

- 다각형 요소를 계산 하는 메서드를 추가 합니다.

- 채우기 색을 초기화

## <a name="modifying-the-header-file"></a>헤더 파일을 수정

수학 함수에 대 한 지원을 추가 하 여 시작 `sin` 및 `cos`에 사용 되는 다각형 점 계산 및 저장할 배열을 만들어 배치 합니다.

### <a name="to-modify-the-header-file"></a>헤더 파일을 수정 하려면

1. 줄 추가 `#include <math.h>` PolyCtl.h의 맨 위로 이동 합니다. 파일의 맨 위에 다음과 같이 표시 됩니다.

    [!code-cpp[NVC_ATL_Windowing#47](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_1.cpp)]

1. 구현 된 `IProvideClassInfo` PolyCtl.h에 다음 코드를 추가 하 여 컨트롤에 대 한 메서드 정보를 제공 하는 인터페이스입니다. 에 `CPolyCtl` 클래스에서 줄을으로 바꿉니다.

    ```cpp
    public CComControl<CPolyCtl>
    ```

    다음 문자열로 바꾸세요.

    ```cpp
    public CComControl<CPolyCtl>,
    public IProvideClassInfo2Impl<&CLSID_PolyCtl, &DIID__IPolyCtlEvents, &LIBID_PolygonLib>
    ```

    및 `BEGIN_COM_MAP(CPolyCtl)`, 줄을 추가 합니다.

    ```cpp
    COM_INTERFACE_ENTRY(IProvideClassInfo)
    COM_INTERFACE_ENTRY(IProvideClassInfo2)
    ```

1. 저장 형식 배열이 됩니다 다각형 점 계산 되 면 `POINT`, 따라서 배열 정의 문 뒤에 추가 `short m_nSides;` PolyCtl.h에:

    [!code-cpp[NVC_ATL_Windowing#48](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_2.h)]

## <a name="modifying-the-ondraw-method"></a>OnDraw 메서드를 수정합니다.

수정 해야 하는 이제는 `OnDraw` PolyCtl.h의 메서드. 추가 코드는 새 펜 및 브러시에 다각형을 그릴 만들고 호출을 `Ellipse` 및 `Polygon` 실제 그리기를 수행 하기 위해 Win32 API 함수입니다.

### <a name="to-modify-the-ondraw-function"></a>OnDraw 함수를 수정 하려면

1. 기존 대체 `OnDraw` PolyCtl.h의 메서드를 다음 코드로:

    [!code-cpp[NVC_ATL_Windowing#49](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_3.cpp)]

## <a name="adding-a-method-to-calculate-the-polygon-points"></a>다각형 요소를 계산 하는 메서드를 추가 합니다.

라는 메서드를 추가 `CalcPoints`, 다각형의 경계를 구성 하는 지점의 좌표를 계산할입니다. 이러한 계산 함수에 전달 되는 RECT 변수에 따라 달라 집니다.

### <a name="to-add-the-calcpoints-method"></a>CalcPoints 메서드를 추가 하려면

1. 선언의 추가 `CalcPoints` 에 `IPolyCtl` 의 public 섹션을 `CPolyCtl` PolyCtl.h의 클래스:

    [!code-cpp[NVC_ATL_Windowing#50](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_4.h)]

    public 섹션의 마지막 부분을 `CPolyCtl` 클래스는 다음과 같이 표시 됩니다.

    [!code-cpp[NVC_ATL_Windowing#51](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_5.h)]

1. 이 구현을 추가 합니다 `CalcPoints` PolyCtl.cpp 끝 함수:

    [!code-cpp[NVC_ATL_Windowing#52](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_6.cpp)]

## <a name="initializing-the-fill-color"></a>채우기 색을 초기화

초기화 `m_clrFillColor` 기본 색을 사용 하 여 합니다.

### <a name="to-initialize-the-fill-color"></a>채우기 색을 초기화 하려면

1. 기본 색으로 녹색을 사용 하 여이 줄을 추가 하 여는 `CPolyCtl` PolyCtl.h의 생성자:

    [!code-cpp[NVC_ATL_Windowing#53](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_7.h)]

생성자는 이제 다음과 같이 표시 됩니다.

[!code-cpp[NVC_ATL_Windowing#54](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_8.h)]

## <a name="building-and-testing-the-control"></a>빌드 및 컨트롤 테스트

컨트롤을 다시 빌드하십시오. 여전히 열려 있으면 PolyCtl.htm 파일 닫혀 있는지 확인 하 고 클릭 **다각형 빌드** 에 **빌드** 메뉴. PolyCtl.htm 페이지에서 다시 한 번 컨트롤을 볼 수 있지만이 이번 ActiveX Control Test Container를 사용 합니다.

### <a name="to-use-the-activex-control-test-container"></a>ActiveX Control Test Container를 사용 하려면

1. 빌드 및 ActiveX Control Test Container를 시작 합니다. [TSTCON 샘플: ActiveX Control Test Container](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/MFC/ole/TstCon) GitHub에서 확인할 수 있습니다.

    > [!NOTE]
    > 관련 된 오류에 대 한 `ATL::CW2AEX`, Script.Cpp, 줄 바꿉니다 `TRACE( "XActiveScriptSite::GetItemInfo( %s )\n", pszNameT );` 사용 하 여 `TRACE( "XActiveScriptSite::GetItemInfo( %s )\n", pszNameT.m_psz );`, 및 줄 `TRACE( "Source Text: %s\n", COLE2CT( bstrSourceLineText ) );` 사용 하 여 `TRACE( "Source Text: %s\n", bstrSourceLineText );`입니다.<br/>
    > 관련 된 오류에 대 한 `HMONITOR`, 열에서 StdAfx.h는 `TCProps` 바꾸고 프로젝트:
    > ```
    > #ifndef WINVER
    > #define WINVER 0x0400
    > #endif
    > ```
    > 다음 문자열로 바꾸세요.
    > ```
    > #ifndef WINVER
    > #define WINVER 0x0500
    > #define _WIN32_WINNT 0x0500
    > #endif
    > ```

1. **테스트 컨테이너**에 **편집** 메뉴에서 클릭 **새 컨트롤 삽입**합니다.

1. 호출할 수 있는 컨트롤을 찾습니다 `PolyCtl class`, 클릭 **확인**합니다. 원 안에 녹색 삼각형이 표시 됩니다.

다음 절차에 따라 면의 수를 변경해 보세요. 이중 인터페이스 내에서 속성을 수정할 **테스트 컨테이너**를 사용 하 여 **메서드 호출**합니다.

### <a name="to-modify-a-controls-property-from-within-the-test-container"></a>테스트 컨테이너 내에서 컨트롤의 속성을 수정 하려면

1. **테스트 컨테이너**, 클릭 **메서드 호출** 에 **컨트롤** 메뉴.

    합니다 **메서드 호출** 대화 상자가 표시 됩니다.

1. 선택는 **PropPut** 버전의는 **양쪽** 속성을 **메서드 이름** 드롭다운 목록 상자.

1. 형식 `5` 에 **매개 변수 값** 상자를 클릭 합니다 **값 설정**를 클릭 하 고 **Invoke**합니다.

컨트롤을 변경 하지 않는 참고 합니다. 설정 하 여 내부적으로 면의 수를 변경 하 여 `m_nSides` 변수에이 시 키 지 않는 그릴 컨트롤입니다. 다른 응용 프로그램으로 전환 하 고로 다시 전환 하는 경우 **테스트 컨테이너**, 컨트롤 그려져 있고 양쪽의 정확한 수는 있습니다.

이 문제를 해결 하려면 호출을 추가 합니다 `FireViewChange` 에 정의 된 함수 `IViewObjectExImpl`하면 변 수가 설정한 후, 합니다. 컨트롤은 자체 창에서 실행 중인 경우 `FireViewChange` 호출을 `InvalidateRect` 메서드를 직접. 컨트롤이 창 없는 실행 하는 경우는 `InvalidateRect` 컨테이너의 사이트 인터페이스 메서드를 호출 합니다. 이렇게 하면 컨트롤이 다시 그려집니다.

### <a name="to-add-a-call-to-fireviewchange"></a>FireViewChange에 대 한 호출을 추가 하려면

1. 에 대 한 호출을 추가 하 여 PolyCtl.cpp를 업데이트할 `FireViewChange` 에 `put_Sides` 메서드. 완료 한 후에 `put_Sides` 메서드는 다음과 같습니다.

    [!code-cpp[NVC_ATL_Windowing#55](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_9.cpp)]

추가한 후 `FireViewChange`, 다시 작성 및 ActiveX Control Test Container 컨트롤을 다시 시도 하세요. 이 시간 면의 수를 변경 하 고 클릭 `Invoke`를 즉시 변경 하는 컨트롤을 표시 합니다.

다음 단계에서는 이벤트를 추가 합니다.

[3 단계로](../atl/adding-a-property-to-the-control-atl-tutorial-part-3.md) &#124; [5 단계로 이동 합니다.](../atl/adding-an-event-atl-tutorial-part-5.md)

## <a name="see-also"></a>참고자료

[자습서](../atl/active-template-library-atl-tutorial.md)<br/>
[테스트 컨테이너로 속성 및 이벤트 테스트](../mfc/testing-properties-and-events-with-test-container.md)
