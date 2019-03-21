---
title: ATL 프로젝트에 새 인터페이스 추가
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.ATL.interface
helpviewer_keywords:
- interfaces, adding to ATL objects
- Implement Interface ATL wizard
- controls [ATL], interfaces
- ATL projects, adding interfaces
ms.assetid: 7d34b023-2c6b-4155-aca3-d47a40968063
ms.openlocfilehash: 99f262d420cd503c6ca385ed29bcaa2647c5f556
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57810057"
---
# <a name="adding-a-new-interface-in-an-atl-project"></a>ATL 프로젝트에 새 인터페이스 추가

개체 또는 컨트롤 인터페이스를 추가 하면 해당 인터페이스의 각 메서드에 대 한 스텁 아웃 함수를 만듭니다. 개체 또는 컨트롤에서 현재 기존 형식 라이브러리에서 찾을 인터페이스만 추가할 수 있습니다. 또한 인터페이스를 추가할 클래스를 구현 해야 합니다는 [BEGIN_COM_MAP](com-map-macros.md#begin_com_map) 매크로 프로젝트 특성을 사용 하는 경우에 있어야 또는 `coclass` 특성입니다.

두 가지 방법 중 하나에서 컨트롤에는 새 인터페이스를 추가할 수 있습니다: 수동으로 또는 클래스 뷰에서 코드 마법사를 사용 하 여 합니다.

## <a name="to-use-code-wizards-in-class-view-to-add-an-interface-to-an-existing-object-or-control"></a>클래스 뷰에서 코드 마법사를 사용 하 여 기존 개체 또는 컨트롤에 인터페이스를 추가 하려면

1. [클래스 뷰](/visualstudio/ide/viewing-the-structure-of-code), 컨트롤의 클래스 이름을 마우스 오른쪽 단추로 클릭 합니다. 예를 들어, 전체 컨트롤을 복합 컨트롤 또는 BEGIN_COM_MAP 매크로 헤더 파일에 구현 하는 다른 컨트롤 클래스입니다.

1. 바로 가기 메뉴에서 클릭 **추가**를 클릭 하 고 **인터페이스 구현**합니다.

1. 구현에 대 한 인터페이스를 선택 합니다 [인터페이스 구현 마법사](../../ide/implement-interface-wizard.md)합니다. 모든 사용 가능한 typelib에 들어 있는 인터페이스 없으면 다음 추가 해야 수동으로.idl 파일입니다.

## <a name="to-add-a-new-interface-manually"></a>새 인터페이스를 수동으로 추가 하려면

1. .Idl 파일에 새 인터페이스의 정의 추가 합니다.

1. 개체 또는 인터페이스에서 컨트롤 파생 됩니다.

1. 새 [COM_INTERFACE_ENTRY](com-interface-entry-macros.md#com_interface_entry) 인터페이스에 대 한 프로젝트 특성을 사용 하는 경우 추가 또는 `coclass` 특성입니다.

1. 인터페이스에서 메서드를 구현 합니다.

## <a name="see-also"></a>참고자료

[ATL 프로젝트 마법사](../../atl/reference/atl-project-wizard.md)<br/>
[Visual C++ 프로젝트 형식](../../build/reference/visual-cpp-project-types.md)<br/>
[ATL 및 C 런타임 코드를 사용한 프로그래밍](../../atl/programming-with-atl-and-c-run-time-code.md)<br/>
[ATL COM 개체 기본 사항](../../atl/fundamentals-of-atl-com-objects.md)<br/>
[기본 ATL 프로젝트 구성](../../atl/reference/default-atl-project-configurations.md)
