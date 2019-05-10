---
title: 자동화 클라이언트
ms.date: 11/04/2016
helpviewer_keywords:
- clients, Automation
- Automation clients
- type libraries, Automation clients
- clients
ms.assetid: 84e34a79-06f6-4752-a33b-ae0ede1d8ecf
ms.openlocfilehash: 098c41ea981d9d0069130d5439632aa7b0d6cbbd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62254364"
---
# <a name="automation-clients"></a>자동화 클라이언트

Automation을 사용 하면 다른 응용 프로그램에서 구현 하는 개체를 조작 하거나 조작할 수 있도록 개체를 노출 시키는 응용 프로그램에 대 한 수 있습니다. 자동화 클라이언트는 다른 응용 프로그램에 속하는 노출 된 개체를 조작할 수 있는 응용 프로그램. 개체를 표시 하는 응용 프로그램에는 자동화 서버를 라고 합니다. 클라이언트는 해당 개체의 속성 및 함수에 액세스 하 여 서버 응용 프로그램의 개체를 조작 합니다.

### <a name="types-of-automation-clients"></a>유형의 자동화 클라이언트

자동화 클라이언트는 다음과 같은 두 종류가 있습니다.

- 동적으로 (런타임에) 속성 및 서버 작업에 대 한 정보를 획득 하는 클라이언트입니다.

- 서버의 작업을 확인 하 고 속성을 지정 하는 정적 정보 (컴파일 시 제공)를 소유 하는 클라이언트입니다.

첫 번째 종류의 클라이언트는 OLE 시스템의 쿼리를 통해 서버의 메서드 및 속성에 대 한 정보를 획득 `IDispatch` 메커니즘입니다. 동적 클라이언트에 대해 사용할 적합 하지만 `IDispatch` 여기서 구동에 알 수 있어야 합니다 개체 컴파일 시간 정적 클라이언트에 사용 하기 어렵습니다. Microsoft Foundation 클래스를 제공 하는 정적 바인딩된 클라이언트를 합니다 [COleDispatchDriver](../mfc/reference/coledispatchdriver-class.md) 클래스입니다.

정적 바인딩된 클라이언트는 클라이언트 응용 프로그램을 사용 하 여 정적으로 링크 하는 프록시 클래스를 사용 합니다. 이 클래스는 형식 안전성이 제공 C++ 서버 응용 프로그램의 속성 및 작업을 캡슐화 합니다.

클래스 `COleDispatchDriver` 자동화의 클라이언트 쪽에 대 한 기본 지원을 제공 합니다. 사용 하는 **새 항목 추가** 에서 파생 된 클래스를 만들면 대화 상자에서 `COleDispatchDriver`합니다.

그런 다음 속성 및 서버 응용 프로그램의 개체는 함수를 설명 하는 형식 라이브러리 파일을 지정 합니다. 항목 추가 대화 상자의이 파일을 읽고 만듭니다는 `COleDispatchDriver`-응용 프로그램 서버 응용 프로그램의 개체에 액세스 하기 위해 호출할 멤버 함수를 사용 하 여 클래스를 파생 된 C++ 형식이 안전한 방식입니다. 추가 기능에서 상속 `COleDispatchDriver` 적절 한 자동화 서버를 호출 하는 프로세스를 간소화 합니다.

### <a name="handling-events-in-automation-clients"></a>자동화 클라이언트의 이벤트 처리

자동화 클라이언트에서 이벤트를 처리 하려는 경우 싱크 인터페이스를 추가 해야 합니다. MFC는 ActiveX 컨트롤에 대 한 싱크 인터페이스를 추가 하지만 다른 COM 서버에 없습니다. 마법사 지원을 제공 합니다.

## <a name="see-also"></a>참고자료

[자동화 클라이언트: 형식 라이브러리 사용](../mfc/automation-clients-using-type-libraries.md)<br/>
[자동화](../mfc/automation.md)<br/>
[MFC 응용 프로그램 마법사](../mfc/reference/mfc-application-wizard.md)
