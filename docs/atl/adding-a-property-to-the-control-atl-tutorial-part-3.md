---
title: 컨트롤에 속성 추가(ATL 자습서, 3부)
ms.custom: get-started-article
ms.date: 09/26/2018
ms.assetid: f775fe34-103b-4f07-9999-400e987ee030
ms.openlocfilehash: b5f9f9c8fde44dd67a9a05aeae0f91fb7b5f2f4d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62252608"
---
# <a name="adding-a-property-to-the-control-atl-tutorial-part-3"></a>컨트롤에 속성 추가(ATL 자습서, 3부)

`IPolyCtl` 컨트롤의 사용자 지정 메서드 및 속성을 포함 하는 인터페이스 이며 속성을 추가 합니다.

### <a name="to-add-the-property-definitions-to-your-project"></a>속성 정의 프로젝트에 추가 하려면

1. **클래스 뷰**를 확장 하 고는 `Polygon` 분기 합니다.

1. 마우스 오른쪽 단추로 클릭 `IPolyCtl`합니다.

1. 바로 가기 메뉴에서 클릭 **추가**를 클릭 하 고 **; 속성 추가**합니다. 합니다 **속성 추가** 마법사가 나타납니다.

1. 형식 `Sides` 으로 **속성 이름**합니다.

1. 드롭다운 목록의 **속성 형식**선택, `short`합니다.

1. 클릭 **확인** 속성 추가 완료 합니다.

1. **솔루션 탐색기**끝에 다음 줄을 마우스 오른쪽 단추로 Polygon.idl을 열고는 `IPolyCtl : IDispatch` 인터페이스:

    ```cpp
    short get_Sides();
    void set_Sides(short value);
    ```

    다음 문자열로 바꾸세요.

    ```cpp
    [propget, id(1), helpstring("property Sides")] HRESULT Sides([out, retval] short *pVal);
    [propput, id(1), helpstring("property Sides")] HRESULT Sides([in] short newVal);
    ```

1. **솔루션 탐색기**PolyCtl.h 열고 정의 뒤에 다음 줄을 추가 `m_clrFillColor`:

    [!code-cpp[NVC_ATL_Windowing#44](../atl/codesnippet/cpp/adding-a-property-to-the-control-atl-tutorial-part-3_1.h)]

이제 기본 함수를 설정 하 고 속성 및 속성을 저장 하는 변수를 검색 하지만 그에 따라 함수를 구현 해야 합니다.

### <a name="to-update-the-get-and-put-methods"></a>업데이트 get 및 put 메서드

1. 기본값을 설정 `m_nSides`합니다. 기본 삼각형 PolyCtl.h의 생성자에 대 한 줄을 추가 하 여 모양을 확인 합니다.

    [!code-cpp[NVC_ATL_Windowing#45](../atl/codesnippet/cpp/adding-a-property-to-the-control-atl-tutorial-part-3_2.h)]

1. 구현 된 `Get` 고 `Put` 메서드. 합니다 `get_Sides` 및 `put_Sides` 함수 선언 PolyCtl.h에 추가 되었습니다. 이제는 코드를 추가할 `get_Sides` 고 `put_Sides` 다음 PolyCtl.cpp에:

    [!code-cpp[NVC_ATL_Windowing#46](../atl/codesnippet/cpp/adding-a-property-to-the-control-atl-tutorial-part-3_3.cpp)]

합니다 `get_Sides` 의 현재 값을 반환 하는 메서드를 `Sides` 속성을 통해는 `pVal` 포인터입니다. 에 `put_Sides` 메서드는 코드를 사용 하면 사용자 설정는 `Sides` 속성 허용 되는 값을 합니다. 최소 3, 및 지점의 배열로, 각 면에 대해 사용 되므로 100 제한은 적절 한 최 댓 값.

이제 라는 속성이 `Sides`합니다. 다음 단계에서 사용 하는 그리기 코드를 변경 됩니다.

[2 단계를 다시](../atl/adding-a-control-atl-tutorial-part-2.md) &#124; [4 단계로 이동 합니다.](../atl/changing-the-drawing-code-atl-tutorial-part-4.md)

## <a name="see-also"></a>참고자료

[자습서](../atl/active-template-library-atl-tutorial.md)
