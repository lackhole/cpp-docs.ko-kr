---
title: IDispEventImpl 사용 (ATL)
ms.date: 08/19/2019
helpviewer_keywords:
- IDispEventImpl class, using
ms.assetid: 82d53b61-9d0d-45c5-aff9-2fafa468a9ca
ms.openlocfilehash: 9684781ba99d96e2c58d450ee0ff892374e33aef
ms.sourcegitcommit: 9d4ffb8e6e0d70520a1e1a77805785878d445b8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2019
ms.locfileid: "69630594"
---
# <a name="using-idispeventimpl"></a>IDispEventImpl 사용

를 사용 `IDispEventImpl` 하 여 이벤트를 처리 하는 경우 다음을 수행 해야 합니다.

- [IDispEventImpl](../atl/reference/idispeventimpl-class.md)에서 클래스를 파생 시킵니다.

- 클래스에 이벤트 싱크 맵을 추가 합니다.

- [SINK_ENTRY](reference/composite-control-macros.md#sink_entry) 또는 [SINK_ENTRY_EX](reference/composite-control-macros.md#sink_entry_ex) 매크로를 사용 하 여 이벤트 싱크 맵에 항목을 추가 합니다.

- 처리할 메서드를 구현 합니다.

- 이벤트 원본을 Advise 하 고 unadvise.

## <a name="example"></a>예제

아래 예제에서는 Word의 **Application** 개체에서 `DocumentChange` 발생 하는 이벤트를 처리 하는 방법을 보여 줍니다. 이 이벤트는이에 대 `ApplicationEvents` 한 메서드로 정의 됩니다.

예는 [ATLEventHandling 샘플](../overview/visual-cpp-samples.md)에서 가져온 것입니다.

```cpp
[ uuid(000209F7-0000-0000-C000-000000000046), hidden ]
dispinterface ApplicationEvents {
properties:
methods:
    [id(0x00000001), restricted, hidden]
    void Startup();

    [id(0x00000002)]
    void Quit();

    [id(0x00000003)]
    void DocumentChange();
};
```

이 예제에서는 `#import` 를 사용 하 여 Word의 형식 라이브러리에서 필요한 헤더 파일을 생성 합니다. 다른 버전의 Word와 함께이 예를 사용 하려면 올바른 mso dll 파일을 지정 해야 합니다. 예를 들어 Office 2000은 mso9을 제공 하 고 OfficeXP는 mso.dll을 제공 합니다. 이 코드는 *.pch. h* (Visual Studio 2017 및 이전 버전의*stdafx.h* )에서 간소화 되었습니다.

[!code-cpp[NVC_ATL_EventHandlingSample#1](../atl/codesnippet/cpp/using-idispeventimpl_1.h)]

다음 코드는 NotSoSimple. h에 표시 됩니다. 관련 코드는 설명으로 표시 됩니다.

[!code-cpp[NVC_ATL_EventHandlingSample#2](../atl/codesnippet/cpp/using-idispeventimpl_2.h)]

## <a name="see-also"></a>참고자료

[이벤트 처리](../atl/event-handling-and-atl.md)<br/>
[ATLEventHandling 샘플](../overview/visual-cpp-samples.md)
