---
title: 포함 된 Windows를 사용 하 여
ms.date: 11/04/2016
helpviewer_keywords:
- ATL, windows
- windows [C++], ATL
- contained windows in ATL
ms.assetid: 7b3d79e5-b569-413f-9b98-df4f14efbe2b
ms.openlocfilehash: 2b9a36c6aac80a7c77cde102d6da93c51788e4e1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62198605"
---
# <a name="using-contained-windows"></a>포함 된 Windows를 사용 하 여

포함 된 windows를 구현 하는 ATL [CContainedWindowT](../atl/reference/ccontainedwindowt-class.md)합니다. 포함된 된 창을 해당 메시지는 자체 클래스에서 처리 하는 대신 컨테이너 개체를 위임 하는 창을 나타냅니다.

> [!NOTE]
>  클래스를 파생 해야 `CContainedWindowT` 포함 된 windows를 사용 하려면.

포함 된 windows를 사용 하 여 기존 Windows 클래스 또는 기존 창 하위 클래스입니다. 슈퍼 있습니다. 슈퍼를 기존 Windows 창을 만들려면 클래스, 먼저 이름을 기존 클래스의 생성자에 지정 된 `CContainedWindowT` 개체. 그런 다음 호출 `CContainedWindowT::Create`합니다. 기존 창 하위 클래스에 Windows 클래스 이름 (생성자에 NULL 전달)를 지정할 필요가 없습니다. 호출 된 `CContainedWindowT::SubclassWindow` 서브클래싱 되는 창에 대 한 핸들을 사용 하 여 메서드.

일반적으로 포함 된 windows 컨테이너 클래스의 데이터 멤버로 사용 합니다. 컨테이너는 창이; 될 필요가 없습니다. 그러나 파생 되어야 합니다 [CMessageMap](../atl/reference/cmessagemap-class.md)합니다.

포함된 된 창을 대체 메시지 맵을 사용 하 여 해당 메시지를 처리할 수 있습니다. 둘 이상의 포함 된 창에 있는 경우 포함 된 별도 창에 해당 하는 메시지 맵, 여러 개의 대체를 선언 해야 합니다.

## <a name="example"></a>예제

다음은 두 개의 포함 된 windows 컨테이너 클래스의 예입니다.

[!code-cpp[NVC_ATL_Windowing#67](../atl/codesnippet/cpp/using-contained-windows_1.h)]

포함 된 창에 대 한 자세한 내용은 참조는 [SUBEDIT](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/Controls/SubEdit) 샘플입니다.

## <a name="see-also"></a>참고자료

[창 클래스](../atl/atl-window-classes.md)
