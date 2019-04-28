---
title: 이벤트 추가(ATL 자습서, 5부)
ms.custom: get-started-article
ms.date: 09/27/2018
ms.assetid: 2de12022-3148-4ce3-8606-8a9d4274f0e9
ms.openlocfilehash: 57fc2adaadcca52cfc25736b5f9010fcb65a2ff0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62252565"
---
# <a name="adding-an-event-atl-tutorial-part-5"></a>이벤트 추가(ATL 자습서, 5부)

이 단계에서는 추가 된 `ClickIn` 및 `ClickOut` ATL 컨트롤에 이벤트입니다. 발생 하는 합니다 `ClickIn` 다각형 및 화재 내부를 클릭할 경우 이벤트 `ClickOut` 외부를 클릭할 경우. 이벤트를 추가 하는 작업은 다음과 같습니다.

- 추가 된 `ClickIn` 고 `ClickOut` 메서드

- 형식 라이브러리를 생성합니다.

- 연결 지점 인터페이스를 구현합니다.

## <a name="adding-the-clickin-and-clickout-methods"></a>ClickIn 및 ClickOut 메서드를 추가합니다.

2 단계에서 ATL 컨트롤을 만들 때 선택 된 **연결점** 확인란 합니다. 만든이 `_IPolyCtlEvents` 마우스 오른쪽 단추로 Polygon.idl 파일에 대 한 인터페이스입니다. 인터페이스 이름이 밑줄로 시작 하는 참고 합니다. 이것이 인터페이스에 내부 인터페이스를 표시 하려면 규칙입니다. 따라서 COM 개체를 탐색할 수 있도록 하는 프로그램 하지 않도록 선택할 수는 사용자 인터페이스를 표시 합니다. 선택 하면 참고 **연결점** 나타내기 위해 마우스 오른쪽 단추로 Polygon.idl 파일에 다음 줄을 추가 `_IPolyCtlEvents` 기본 소스 인터페이스는:

`[default, source] dispinterface _IPolyCtlEvents;`

원본 특성 컨트롤 임을 나타냅니다는 알림의 원본 컨테이너에서이 인터페이스를 호출 하도록 합니다.

이제 추가 합니다 `ClickIn` 및 `ClickOut` 방법의 `_IPolyCtlEvents` 인터페이스입니다.

### <a name="to-add-the-clickin-and-clickout-methods"></a>ClickIn 및 ClickOut 메서드를 추가 하려면

1. **솔루션 탐색기**를 마우스 오른쪽 단추로 Polygon.idl을 열고 아래에 다음 코드를 추가 `methods:` 에 `dispInterface_IPolyCtlEvents` PolygonLib 라이브러리의 선언:

    ```cpp
   [id(1), helpstring("method ClickIn")] void ClickIn([in] LONG x,[in] LONG y);
   [id(2), helpstring("method ClickOut")] void ClickOut([in] LONG x,[in] LONG y);
    ```

합니다 `ClickIn` 고 `ClickOut` 메서드 x 클릭 한 요소의 y 좌표를 매개 변수로 합니다.

## <a name="generating-the-type-library"></a>형식 라이브러리를 생성합니다.

프로젝트에서이 파일 연결 지점 인터페이스 및 컨트롤에 대 한 연결 지점 컨테이너 인터페이스를 구성 하는 데 필요한 정보를 얻으려면 사용 되므로 시점에서 형식 라이브러리를 생성 합니다.

### <a name="to-generate-the-type-library"></a>형식 라이브러리를 생성 하려면

1. 프로젝트를 다시 빌드하십시오.

     또는

1. 마우스 오른쪽 단추로 Polygon.idl 파일을 마우스 오른쪽 단추로 클릭 **솔루션 탐색기** 누릅니다 **컴파일** 바로 가기 메뉴.

이렇게 하면 형식 라이브러리는 Polygon.tlb 파일을 만들어집니다. Polygon.tlb 파일에서 표시 되지 않습니다 **솔루션 탐색기**가 이진 파일 및 없습니다 수 표시 되거나 직접 편집할 때문입니다.

## <a name="implementing-the-connection-point-interfaces"></a>연결 지점 인터페이스를 구현합니다.

연결 지점 인터페이스 및 컨트롤에 대 한 연결 지점 컨테이너 인터페이스를 구현 합니다. Com에서 이벤트의 연결 지점 메커니즘을 통해 구현 됩니다. COM 개체에서 이벤트를 수신 하는 컨테이너 COM 개체를 구현 하는 연결 지점에 권장 된 연결을 설정 합니다. COM 개체는 연결 지점이 여러 개를 가질 수 있으므로 COM 개체는 또한 연결 지점 컨테이너 인터페이스를 구현 합니다. 이 인터페이스를 통해 컨테이너는 연결 지점을 지 확인할 수 있습니다.

연결 지점을 구현 하는 인터페이스 라고 `IConnectionPoint`, 라고 연결 지점 컨테이너를 구현 하는 인터페이스 및 `IConnectionPointContainer`합니다.

구현할 수 있도록 `IConnectionPoint`, 연결 지점 구현 마법사를 사용 합니다. 이 마법사는 생성 된 `IConnectionPoint` 형식 라이브러리를 읽고 실행 될 수 있는 각 이벤트에 대 한 함수를 구현 하 여 인터페이스입니다.

### <a name="to-implement-the-connection-points"></a>연결 지점 구현

1. **솔루션 탐색기**_IPolyCtlEvents_CP.h 열고 아래에 다음 코드를 추가 합니다 `public:` 문에서 `CProxy_IPolyCtlEvents` 클래스:

    ```cpp
    VOID Fire_ClickIn(LONG x, LONG y)
    {
        T* pT = static_cast<T*>(this);
        int nConnectionIndex;
        CComVariant* pvars = new CComVariant[2];
        int nConnections = m_vec.GetSize();

        for (nConnectionIndex = 0; nConnectionIndex < nConnections; nConnectionIndex++)
        {
            pT->Lock();
            CComPtr<IUnknown> sp = m_vec.GetAt(nConnectionIndex);
            pT->Unlock();
            IDispatch* pDispatch = reinterpret_cast<IDispatch*>(sp.p);
            if (pDispatch != NULL)
            {
                pvars[1].vt = VT_I4;
                pvars[1].lVal = x;
                pvars[0].vt = VT_I4;
                pvars[0].lVal = y;
                DISPPARAMS disp = { pvars, NULL, 2, 0 };
                pDispatch->Invoke(0x1, IID_NULL, LOCALE_USER_DEFAULT, DISPATCH_METHOD, &disp, NULL, NULL, NULL);
            }
        }
        delete[] pvars;

    }
    VOID Fire_ClickOut(LONG x, LONG y)
    {
        T* pT = static_cast<T*>(this);
        int nConnectionIndex;
        CComVariant* pvars = new CComVariant[2];
        int nConnections = m_vec.GetSize();

        for (nConnectionIndex = 0; nConnectionIndex < nConnections; nConnectionIndex++)
        {
            pT->Lock();
            CComPtr<IUnknown> sp = m_vec.GetAt(nConnectionIndex);
            pT->Unlock();
            IDispatch* pDispatch = reinterpret_cast<IDispatch*>(sp.p);
            if (pDispatch != NULL)
            {
                pvars[1].vt = VT_I4;
                pvars[1].lVal = x;
                pvars[0].vt = VT_I4;
                pvars[0].lVal = y;
                DISPPARAMS disp = { pvars, NULL, 2, 0 };
                pDispatch->Invoke(0x2, IID_NULL, LOCALE_USER_DEFAULT, DISPATCH_METHOD, &disp, NULL, NULL, NULL);
            }
        }
        delete[] pvars;

    }
    ```

이 파일 이라고 하는 클래스에 표시 됩니다 `CProxy_IPolyCtlEvents` 에서 파생 되는 `IConnectionPointImpl`합니다. _IPolyCtlEvents_CP.h 이제 두 개의 메서드를 정의 `Fire_ClickIn` 및 `Fire_ClickOut`, 하는 두 개의 좌표 매개 변수입니다. 컨트롤에서 이벤트를 발생 시킬 때 이러한 메서드를 호출 합니다.

컨트롤을 만들어 **연결점** 옵션을 선택 하 여 _IPolyCtlEvents_CP.h 파일 생성 되었습니다. 도 추가 하는 it `CProxy_PolyEvents` 하 고 `IConnectionPointContainerImpl` 컨트롤의 여러 상속 목록에 노출 `IConnectionPointContainer` COM 맵에 적절 한 항목을 추가 하 여 수입니다.

이벤트를 지 원하는 코드를 구현 완료 됩니다. 이제 적절 한 시점 이벤트를 발생 시키려면 일부 코드를 추가 합니다. 발생 하는 것을 기억 하십시오를 `ClickIn` 또는 `ClickOut` 컨트롤에서 마우스 왼쪽된 단추를 클릭할 때 이벤트입니다. 추가 대 한 처리기를 확인 하려면 사용자가 단추를 클릭 합니다 `WM_LBUTTONDOWN` 메시지입니다.

### <a name="to-add-a-handler-for-the-wmlbuttondown-message"></a>WM_LBUTTONDOWN 메시지에 대 한 처리기를 추가 하려면

1. **클래스 뷰**를 마우스 오른쪽 단추로 클릭 합니다 `CPolyCtl` 클래스 및 클릭 **속성** 바로 가기 메뉴.

1. 에 **속성** 창 클릭 합니다 **메시지** 아이콘을 클릭 한 다음 `WM_LBUTTONDOWN` 왼쪽 목록에서.

1. 표시 되는 드롭다운 목록에서 클릭  **\<추가 > OnLButtonDown**합니다. `OnLButtonDown` 처리기 선언 PolyCtl.h에 추가 되 고 처리기 구현 PolyCtl.cpp에 추가 됩니다.

그런 다음 처리기를 수정 합니다.

### <a name="to-modify-the-onlbuttondown-method"></a>OnLButtonDown 메서드를 수정 하려면

1. 구성 된 코드를 변경 합니다 `OnLButtonDown` 메서드 PolyCtl.cpp (마법사에서 배치 된 모든 코드가 삭제)에 다음과 같이 표시 되도록:

    [!code-cpp[NVC_ATL_Windowing#57](../atl/codesnippet/cpp/adding-an-event-atl-tutorial-part-5_2.cpp)]

이 코드는 점 사용 하 여 계산 합니다 `OnDraw` 함수에 대 한 호출을 사용 하 여 사용자의 마우스 클릭을 검색 하는 영역을 만드는 `PtInRegion`.

합니다 *uMsg* 매개 변수 처리 Windows 메시지의 ID입니다. 이 옵션을 사용 하면 다양 한 메시지를 처리 하는 하나의 함수만 가질 수 있습니다. 합니다 *wParam* 하며 *lParam* 매개 변수는 처리 중인 메시지에 대 한 표준 값입니다. 매개 변수 *bHandled* 여부 함수에서 메시지를 처리 하는지 여부를 지정할 수 있습니다. 기본적으로 값에서 메시지를 처리 하는 함수는 FALSE로 설정할 수 있습니다을 나타내려면 TRUE로 설정 됩니다. 이렇게 하면 ATL 계속 메시지를 보낼 다른 메시지 처리기 함수를 찾습니다.

## <a name="building-and-testing-the-control"></a>빌드 및 컨트롤 테스트

이제 이벤트를 사용해 보세요. 컨트롤을 빌드하고 ActiveX Control Test Container를 다시 시작 합니다. 이 이번에는 이벤트 로그 창을 봅니다. 출력 창에 이벤트를 라우팅, 클릭 **로깅** 에서 합니다 **옵션** 메뉴를 선택 **출력 창에는 로그**합니다. 컨트롤을 삽입 하 고 창에서 클릭 해 보십시오. 사실은 `ClickIn` 채워진된 다각형 내부를 클릭할 경우 발생 하 고 `ClickOut` 외부를 클릭할 때 발생 합니다.

다음으로, 속성 페이지를 추가 합니다.

[4 단계를 다시](../atl/changing-the-drawing-code-atl-tutorial-part-4.md) &#124; [6 단계로 이동 합니다.](../atl/adding-a-property-page-atl-tutorial-part-6.md)

## <a name="see-also"></a>참고자료

[자습서](../atl/active-template-library-atl-tutorial.md)
