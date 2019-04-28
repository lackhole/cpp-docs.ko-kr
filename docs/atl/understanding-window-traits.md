---
title: ATL 창 특성
ms.date: 11/04/2016
helpviewer_keywords:
- window traits
ms.assetid: c90cf850-9e91-49da-9cf3-ad4efb30347d
ms.openlocfilehash: 29549e54051405fc3dd4d5d7ae70a382ad7a62ea
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62196185"
---
# <a name="understanding-window-traits"></a>창 특성 이해

창 특성 클래스에는 ATL 창 개체 만들기에 사용 되는 스타일을 표준화 하는 간단한 방법을 제공 합니다. 창 특성에서 템플릿 매개 변수로 수락 됩니다 [CWindowImpl](../atl/reference/cwindowimpl-class.md) 및 기본 창 스타일 클래스 수준에서 제공 하는 방법으로 다른 ATL 창 클래스입니다.

창 인스턴스를 생성자에 대 한 호출에서 명시적으로 스타일을 제공 하지 않는 경우 [만들기](../atl/reference/cwindowimpl-class.md#create), 올바른 스타일을 사용 하 여 여전히 창이 만들어졌는지 확인 하는 특성 클래스를 사용할 수 있습니다. 특정 스타일 설정 되어 있는지 해당 창 클래스의 모든 인스턴스에 대 한 다른 스타일을 허용 하는 동안에 인스턴스 단위로 설정할도 확인할 수 있습니다.

## <a name="atl-window-traits-templates"></a>ATL 창 특성 템플릿

ATL에는 해당 템플릿 매개 변수를 사용 하 여 컴파일 타임에 기본 스타일을 설정 하는 데 허용 하는 두 창 traits 템플릿을 제공 합니다.

|클래스|설명|
|-----------|-----------------|
|[CWinTraits](../atl/reference/cwintraits-class.md)|기본 창 스타일 없음 다른 스타일에 대 한 호출에 지정 된 경우에 사용할 수 있도록 하려는 경우이 템플릿을 사용 하 여 `Create`입니다. 에 설정 된 스타일을 통해 런타임 우선에서 제공 되는 스타일 컴파일 시간입니다.|
|[CWinTraitsOR](../atl/reference/cwintraitsor-class.md)|창 클래스에 대해 항상 설정 해야 하는 스타일을 지정 하려는 경우이 클래스를 사용 합니다. 런타임 시 제공 되는 스타일은 비트 OR 연산자를 사용 하 여 컴파일 타임에 설정 된 스타일을 사용 하 여 결합 됩니다.|

ATL 이러한 템플릿 외에도 다양 한 미리 정의 된 특수화를 제공 합니다 `CWinTraits` 창 스타일의 자주 사용 되는 조합에 대 한 템플릿. 참조 된 [CWinTraits](../atl/reference/cwintraits-class.md) 전체 세부 정보에 대 한 설명서를 참조 합니다.

## <a name="custom-window-traits"></a>사용자 지정 창 특성

ATL에서 제공 하는 템플릿 중 하나는 특수화 드문 경우에서 충분 하지 사용자 지정 특성 클래스를 생성 해야 하 고 두 정적 함수를 구현 하는 클래스를 생성 해야 합니다. `GetWndStyle` 고 `GetWndStyleEx`:

[!code-cpp[NVC_ATL_Windowing#68](../atl/codesnippet/cpp/understanding-window-traits_1.h)]

새 스타일 값을 생성 하는 데 사용할 수 있는 런타임 시 일부 스타일 값 전달 됩니다 이러한 각 함수. 이 정적 함수에 전달 된 스타일 값을 스타일 인수로 전달 되는 항목 수 창 특성 클래스는 ATL 창 클래스의 템플릿 인수로 사용 중인 경우 [만들기](../atl/reference/cwindowimpl-class.md#create)합니다.

## <a name="see-also"></a>참고자료

[창 클래스](../atl/atl-window-classes.md)
