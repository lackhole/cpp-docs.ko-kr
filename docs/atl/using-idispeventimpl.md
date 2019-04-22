---
title: IDispEventImpl (ATL)를 사용 하 여
ms.date: 11/04/2016
helpviewer_keywords:
- IDispEventImpl class, using
ms.assetid: 82d53b61-9d0d-45c5-aff9-2fafa468a9ca
ms.openlocfilehash: c532164788d359c7834759de01407d49c19463ca
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58769331"
---
# <a name="using-idispeventimpl"></a>IDispEventImpl 사용

사용 하는 경우 `IDispEventImpl` 이벤트를 처리 하려면 해야 합니다.

- 클래스를 파생 [IDispEventImpl](../atl/reference/idispeventimpl-class.md)합니다.

- 이벤트 싱크 맵과 클래스에 추가 합니다.

- 사용 하 여 이벤트 싱크 맵 항목을 추가 합니다 [SINK_ENTRY](reference/composite-control-macros.md#sink_entry) 하거나 [SINK_ENTRY_EX](reference/composite-control-macros.md#sink_entry_ex) 매크로입니다.

- 처리에 관심이 메서드를 구현 합니다.

- 어드바이스를 unadvise 이벤트 소스입니다.

## <a name="example"></a>예제

아래 예제에서는 처리 하는 방법을 보여 줍니다 합니다 `DocumentChange` 단어의 이벤트가 **응용 프로그램** 개체입니다. 이 이벤트에서 메서드로 정의 됩니다는 `ApplicationEvents` dispinterface 합니다.

예로 [ATLEventHandling 샘플](../overview/visual-cpp-samples.md)합니다.

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

이 예제에서는 사용 `#import` Word의 형식 라이브러리에서 필요한 헤더 파일을 생성 합니다. 이 예제에서는 다른 버전의 Word 사용 하 여 사용 하려는 경우 올바른 mso dll 파일을 지정 해야 합니다. 예를 들어, Office 2000 mso9.dll를 제공 하 고 OfficeXP mso.dll을 제공 합니다. Stdafx.h에서이 코드가 간소화 됩니다.

[!code-cpp[NVC_ATL_EventHandlingSample#1](../atl/codesnippet/cpp/using-idispeventimpl_1.h)]

다음 코드는 NotSoSimple.h에 나타납니다. 관련 코드를 주석으로 표시 됩니다.

[!code-cpp[NVC_ATL_EventHandlingSample#2](../atl/codesnippet/cpp/using-idispeventimpl_2.h)]

## <a name="see-also"></a>참고자료

[이벤트 처리](../atl/event-handling-and-atl.md)<br/>
[ATLEventHandling 샘플](../overview/visual-cpp-samples.md)
