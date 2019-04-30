---
title: CWindowImpl 사용 하 여 창 구현
ms.date: 11/04/2016
helpviewer_keywords:
- ATL, windows
- windows [C++], subclassing
- windows [C++], superclassing
- windows [C++], ATL
- subclassing ATL window classes
- superclassing, ATL
ms.assetid: 3fc40550-f1d6-4702-8b7c-4cf682b6a855
ms.openlocfilehash: 265c3145d8ceacae540286f72939dc046e7c8b35
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62197847"
---
# <a name="implementing-a-window-with-cwindowimpl"></a>CWindowImpl 사용 하 여 창 구현

를 구현 하기 위해 창에서 클래스를 파생 `CWindowImpl`합니다. 파생된 클래스에서 메시지 맵 및 메시지 처리기 함수를 선언 합니다. 이제 세 가지 방법으로 클래스를 사용할 수 있습니다.

- [새 Windows 클래스를 기반으로 창을 만들기](#_atl_creating_a_window_based_on_a_new_windows_class)

- [기존 Windows 클래스 슈퍼 클래스](#_atl_superclassing_an_existing_windows_class)

- [기존 창 하위 클래스.](#_atl_subclassing_an_existing_window)

##  <a name="_atl_creating_a_window_based_on_a_new_windows_class"></a> 새 Windows 클래스에 따라 창 만들기

`CWindowImpl` 포함 된 [DECLARE_WND_CLASS](reference/window-class-macros.md#declare_wnd_class) Windows 클래스 정보를 선언 하는 매크로입니다. 이 매크로 구현 하는 `GetWndClassInfo` 함수를 사용 하는 [CWndClassInfo](../atl/reference/cwndclassinfo-class.md) 새 Windows 클래스의 정보를 정의할 수 있습니다. 때 `CWindowImpl::Create` 라고,이 Windows 클래스 등록 되 고 새 창이 만들어집니다.

> [!NOTE]
>  `CWindowImpl` NULL을 전달 합니다 `DECLARE_WND_CLASS` 매크로 ATL은 Windows 클래스 이름을 생성 합니다. DECLARE_WND_CLASS에 고유한 이름을 지정 하려면 문자열을 전달 하면 `CWindowImpl`-클래스를 파생 합니다.

## <a name="example"></a>예제

다음은 새 Windows 클래스를 기반으로 창을 구현 하는 클래스의 예입니다.

[!code-cpp[NVC_ATL_Windowing#64](../atl/codesnippet/cpp/implementing-a-window-with-cwindowimpl_1.h)]

창을 만들려면의 인스턴스를 만듭니다 `CMyWindow` 호출을 `Create` 메서드.

> [!NOTE]
>  기본 Windows 클래스 정보를 재정의 하려면 구현 합니다 `GetWndClassInfo` 설정 하 여 파생된 클래스에서 메서드를 `CWndClassInfo` 적절 한 값 멤버입니다.

##  <a name="_atl_superclassing_an_existing_windows_class"></a> 기존 Windows 클래스를 슈퍼 클 래 싱

합니다 [DECLARE_WND_SUPERCLASS](reference/window-class-macros.md#declare_wnd_superclass) 매크로 사용 하면 해당 슈퍼 클래스는 기존 Windows 창을 만들려면 클래스입니다. 이 매크로 지정 하면 `CWindowImpl`-클래스를 파생 합니다. 다른 ATL 창과 마찬가지로 메시지는 메시지 맵을 통해 처리 됩니다.

DECLARE_WND_SUPERCLASS를 사용 하는 경우 새 Windows 클래스 등록 됩니다. 이 새 클래스를 지정 해도 사용 하 여 창 프로시저를 대체할 기존 클래스와 동일 하 게 됩니다 `CWindowImpl::WindowProc` (또는이 메서드를 재정의 하는 함수를 사용 하 여).

## <a name="example"></a>예제

다음은 클래스의 예제를 슈퍼 표준 편집 클래스:

[!code-cpp[NVC_ATL_Windowing#65](../atl/codesnippet/cpp/implementing-a-window-with-cwindowimpl_2.h)]

슈퍼 클래스로 지정 된 편집 창을 만들기의 인스턴스를 만듭니다 `CMyEdit` 호출을 `Create` 메서드.

##  <a name="_atl_subclassing_an_existing_window"></a> 기존 창을 서브클래싱

기존 창 서브 클래스에서 클래스 파생 `CWindowImpl` 메시지 맵을 두 이전 경우와 같이 선언 합니다. 단, 하는 것 이므로 하위 클래스는 기존 창에 모든 Windows 클래스 정보를 지정 하지 않으면.

호출 하는 대신 `Create`, 호출 `SubclassWindow` 서브 클래스를 기존 창에 핸들을 전달 합니다. 창을 서브클래싱 되 면 사용할 `CWindowImpl::WindowProc` (또는이 메서드를 재정의 하는 함수)을 메시지 맵에 메시지를 보내기 위해. 개체에서 서브클래싱된 창을 분리 하려면 호출 `UnsubclassWindow`합니다. 창의 원본 창 프로시저는 다음 복원 됩니다.

## <a name="see-also"></a>참고자료

[창 구현](../atl/implementing-a-window.md)
