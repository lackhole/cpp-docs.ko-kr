---
title: ATL 연결 지점 예제
ms.date: 11/04/2016
helpviewer_keywords:
- connection points [C++], examples
- examples [ATL]
ms.assetid: a49721b7-f308-43de-8868-f662a94bc81a
ms.openlocfilehash: f33364cee65031c358fb546312f3fe2b7ae854d3
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69491789"
---
# <a name="atl-connection-point-example"></a>ATL 연결 지점 예제

이 예제에서는 [IPropertyNotifySink](/windows/win32/api/ocidl/nn-ocidl-ipropertynotifysink) 를 나가는 인터페이스로 지 원하는 개체를 보여 줍니다.

[!code-cpp[NVC_ATL_Windowing#84](../atl/codesnippet/cpp/atl-connection-point-example_1.h)]

를 나가는 `IPropertyNotifySink` 인터페이스로 지정 하는 경우 대신 `IConnectionPointImpl` [IPropertyNotifySinkCP](../atl/reference/ipropertynotifysinkcp-class.md) 클래스를 사용할 수 있습니다. 예:

[!code-cpp[NVC_ATL_Windowing#85](../atl/codesnippet/cpp/atl-connection-point-example_2.h)]

## <a name="see-also"></a>참고자료

[연결점](../atl/atl-connection-points.md)
