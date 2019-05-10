---
title: OLE 자동화 클래스
ms.date: 11/04/2016
f1_keywords:
- vc.classes.ole
helpviewer_keywords:
- Automation, classes
- Automation classes [MFC], OLE classes
- OLE Automation [MFC], classes
- Automation classes [MFC]
- OLE Automation [MFC]
ms.assetid: 96e5372b-ff8a-4da1-933b-4d9bbf4dceb3
ms.openlocfilehash: 08e33e1fce3f792e76e2eec4ecb59601c99d9822
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62348720"
---
# <a name="ole-automation-classes"></a>OLE 자동화 클래스

이러한 클래스에는 자동화 클라이언트 (응용 프로그램이 다른 응용 프로그램을 제어 하는) 지원 합니다. 자동화 서버 (응용 프로그램이 다른 응용 프로그램에서 제어할 수 있는)를 통해 지원 됩니다 [디스패치 맵](../mfc/reference/dispatch-maps.md)합니다.

[COleDispatchDriver](../mfc/reference/coledispatchdriver-class.md)<br/>
자동화 클라이언트에서 자동화 서버를 호출 하는 데 사용 합니다. 클래스에 추가할 때이 클래스는 형식 라이브러리를 제공 하는 자동화 서버에 대 한 형식이 안전한 클래스를 만들기 위해 사용 됩니다.

[COleDispatchException](../mfc/reference/coledispatchexception-class.md)<br/>
OLE 자동화 하는 동안 오류에서 발생 하는 예외입니다. 자동화 예외는 자동화 서버에 의해 throw되고 자동화 클라이언트에 의해 catch됩니다.

## <a name="see-also"></a>참고자료

[클래스 개요](../mfc/class-library-overview.md)
