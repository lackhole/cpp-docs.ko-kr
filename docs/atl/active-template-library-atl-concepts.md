---
title: ATL(액티브 템플릿 라이브러리) 개념
ms.date: 11/04/2016
helpviewer_keywords:
- ATL, about ATL
ms.assetid: a3960991-4d76-4da5-9568-3fa7fde53ff4
ms.openlocfilehash: 7eb7eb1c369f825fbb689cd476d43be538ae8d9a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62223456"
---
# <a name="active-template-library-atl-concepts"></a>ATL(액티브 템플릿 라이브러리) 개념

액티브 템플릿 라이브러리 (ATL)는 작고 빠른 구성 요소 개체 모델(COM, Component Object Model)을 만들 수 있도록 해 주는 템플릿 기반의 C++ 클래스의 집합입니다. 스토크 구현, 이중 인터페이스, 표준 COM 열거자 인터페이스, 연결 지점, 분리 인터페이스 및 ActiveX 컨트롤을 포함한 핵심 COM 기능에 대한 특별한 지원을 해 줍니다.

다수의 ATL 프로그래밍을 수행하기 위해 특성이나 COM 프로그래밍 간소화를 위해 설계된 Visual C++.NET의 새로운 기능에 대한 학습이 필요할 수도 있습니다. 자세한 내용은 [특성 사용 프로그래밍](../windows/attributed-programming-concepts.md)을 참조합니다.

## <a name="in-this-section"></a>섹션 내용

[ATL 자습서](../atl/active-template-library-atl-tutorial.md)<br/>
컨트롤 생성을 안내하고 프로세스에서 일부 ATL 기초를 보여줍니다.

[COM 및 ATL 소개](../atl/introduction-to-com-and-atl.md)<br/>
구성 요소 개체 모델(COM) 이면의 주요 개념을 소개합니다. 이 문서에서 ATL 정의 및 사용 시기에 대해서도 간략하게 설명합니다.

[ATL COM 개체 기본 사항](../atl/fundamentals-of-atl-com-objects.md)<br/>
이러한 클래스를 구현 하는 방법 및 다양 한 ATL 클래스 간의 관계를 설명 합니다.

[이중 인터페이스 및 ATL](../atl/dual-interfaces-and-atl.md)<br/>
ATL의 관점에서 이중 인터페이스를 설명합니다.

[ATL 컬렉션 및 열거자](../atl/atl-collections-and-enumerators.md)<br/>
ATL에서 컬렉션, 열거자 작성 및 구현을 설명합니다.

[복합 컨트롤 기본 사항](../atl/atl-composite-control-fundamentals.md)<br/>
복합 컨트롤을 만들기 위한 단계별 지침을 제공 합니다. 복합 컨트롤에는 다른 ActiveX 컨트롤 또는 Windows 컨트롤을 포함할 수 있는 ActiveX 컨트롤의 형식입니다.

[ATL 컨트롤 포함 FAQ](../atl/atl-control-containment-faq.md)<br/>
ATL 컨트롤을 호스팅할 때의 기본적인 문제를 설명합니다.

[ATL COM 속성 페이지](../atl/atl-com-property-pages.md)<br/>
COM 속성 페이지를 지정하고 구현하는 방법을 보여줍니다.

[DHTML 컨트롤에 대한 ATL 지원](../atl/atl-support-for-dhtml-controls.md)<br/>
DHTML 컨트롤 만들기에 대 한 단계별 지침을 제공 합니다.

[ATL 연결 지점](../atl/atl-connection-points.md)<br/>
연결점 이란 무엇 이며 ATL을 구현 하는 방법을 설명 합니다.

[이벤트 처리 및 ATL](../atl/event-handling-and-atl.md)<br/>
ATL의 [IDispEventImpl](../atl/reference/idispeventimpl-class.md) 및 [IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md) 클래스를 사용하여 COM 이벤트를 처리하는데 필요한 단계를 설명합니다.

[ATL 및 자유 스레드된 마샬러](../atl/atl-and-the-free-threaded-marshaler.md)<br/>
클래스가 자유 스레드 된 마샬러(FTM) 집합을 허용하는 ATL 단순 개체 마법사의 옵션을 자세히 설명합니다.

[프로젝트의 스레딩 모델 지정](../atl/specifying-the-threading-model-for-a-project-atl.md)<br/>
프로젝트의 스레딩 관련 된 런타임 성능 제어에 사용할 수 있는 매크로 설명 합니다.

[ATL 모듈 클래스](../atl/atl-module-classes.md)<br/>
ATL 7.0에 대한 새 모듈 클래스를 설명합니다. ATL에 필요한 기본 기능을 구현하는 모듈 클래스

[ATL 서비스](../atl/atl-services.md)<br/>
일련의 서비스가 구현될 때 발생하는 이벤트에 대해 설명합니다. 또한 서비스 개발에 관련된 개념 중 일부에 대해서도 다룹니다.

[ATL 창 클래스](../atl/atl-window-classes.md)<br/>
ATL에서 슈퍼 클래스 및 하위 클래스 윈도우를 만드는 방법에 대해 설명합니다. ATL 창 클래스는 COM 클래스가 아닙니다. 

[ATL 컬렉션 클래스](../atl/atl-collection-classes.md)<br/>
ATL에서 배열과 맵을 사용하는 방법에 대해 설명합니다.

[ATL 레지스트리 구성 요소 (등록자)](../atl/atl-registry-component-registrar.md)<br/>
구문과 대체 가능 매개 변수를 스크립팅 하는 ATL을 설명합니다. 또한 등록자에 정적 링크를 설정하는 방법을 설명합니다. 

[ATL 및 C 런타임 코드를 사용한 프로그래밍](../atl/programming-with-atl-and-c-run-time-code.md)<br/>
C 런타임 라이브러리(CRT)의 정적 또는 동적으로 연결의 이점을 설명합니다.

[CComBSTR을 사용한 프로그래밍](../atl/programming-with-ccombstr-atl.md)<br/>
`CComBSTR` 을 이용하여 프로그래밍할 때 주의해야 하는 여러 가지 상황에 대해 설명합니다.

[인코딩 참조](../atl/atl-encoding-reference.md)<br/>
atlenc.h에 있는 uuencode, 16진수, 그리고 UTF8과 같은 일반적인 인터넷 표준 범위의 인코딩 지원을 위한 함수와 매크로를 제공합니다.

[유틸리티 참조](../atl/atl-utilities-reference.md)<br/>
[CPathT](../atl/reference/cpatht-class.md) 및 [CUrl](../atl/reference/curl-class.md) 형식의 경로 URL을 조작하기 위한 코드를 제공합니다.  스레드 풀인 [CThreadPool](../atl/reference/cthreadpool-class.md)을 응용 프로그램에서 사용할 수 있습니다. 이 코드는 atlpath.h 및 atlutil.h에서 찾을 수 있습니다. 

## <a name="related-sections"></a>관련 단원

[ATL 샘플](../overview/visual-cpp-samples.md)<br/>
설명 및 ATL 샘플 프로그램에 대 한 링크를 제공합니다.

[ATL 프로젝트 만들기](../atl/reference/creating-an-atl-project.md)<br/>
ATL 프로젝트 마법사에 대 한 정보를 포함합니다.

[ATL 컨트롤 마법사](../atl/reference/atl-control-wizard.md)<br/>
클래스를 추가 하는 방법에 설명 합니다.

[특성 사용된 프로그래밍](../windows/attributed-programming-concepts.md)<br/>
특성을 사용하여 COM 프로그래밍을 단순화하는 방법에 대한 개요와 자세한 내용에 대한 목록을 제공합니다.

[ATL 클래스 개요](../atl/atl-class-overview.md)<br/>
ATL 클래스에 대한 참조 정보와 링크를 제공합니다.
