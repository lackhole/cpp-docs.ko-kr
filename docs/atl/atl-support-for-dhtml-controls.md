---
title: DHTML 컨트롤에 대한 ATL 지원
ms.date: 11/04/2016
helpviewer_keywords:
- HTML controls, ATL support
- DHTML controls, ATL support
- DHTML controls
ms.assetid: 4ba98098-da5d-4362-96ad-8372f816c307
ms.openlocfilehash: dd8ac616d127c3307c1c432c0b3c9bc2ef1d6181
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62223294"
---
# <a name="atl-support-for-dhtml-controls"></a>DHTML 컨트롤에 대한 ATL 지원

ATL을 사용 하 여, DHTML (동적 HTML) 기능을 사용 하 여 컨트롤을 만들 수 있습니다. ATL DHTML 컨트롤:

- WebBrowser 컨트롤을 호스팅합니다.

- HTML과 DHTML 컨트롤의 사용자 인터페이스 (UI)를 사용 하 여 여부를 지정 합니다.

- 해당 인터페이스를 통해 해당 메서드와 WebBrowser 개체에 액세스 [IWebBrowser2](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752127\(v=vs.85\))합니다.

- 간의 통신을 관리 C++ 코드 및 HTML입니다.

DHTML 컨트롤 DHTML 컨트롤에 추가 디스패치 인터페이스가 포함 됩니다 점을 제외 하 고 다른 ATL 컨트롤와 비슷합니다. 그림을 참조 하세요 [DHTML 컨트롤 프로젝트의 요소 식별](../atl/identifying-the-elements-of-the-dhtml-control-project.md) 기본 DHTML 프로젝트에서 제공 하는 인터페이스에 대 한 예제입니다.

웹 브라우저 또는 ActiveX Control Test Container와 같은 다른 컨테이너에서 ATL DHTML 컨트롤을 볼 수 있습니다.

## <a name="in-this-section"></a>섹션 내용

[DHTML 컨트롤 프로젝트의 요소 식별](../atl/identifying-the-elements-of-the-dhtml-control-project.md)<br/>
DHTML 컨트롤 프로젝트의 요소를 설명합니다.

[DHTML에서 C++ 코드 호출](../atl/calling-cpp-code-from-dhtml.md)<br/>
호출의 예를 제공 C++ DHTML 컨트롤에서 코드입니다.

[ATL DHTML 컨트롤 만들기](../atl/creating-an-atl-dhtml-control.md)<br/>
DHTML 컨트롤을 만드는 단계를 나열 합니다.

[ATL DHTML 컨트롤 테스트](../atl/testing-the-atl-dhtml-control.md)<br/>
초기 DHTML 컨트롤 프로젝트 빌드 및 테스트 하는 방법을 보여 줍니다.

[ATL DHTML 컨트롤 수정](../atl/modifying-the-atl-dhtml-control.md)<br/>
컨트롤에 일부 기능을 추가 하는 방법을 보여 줍니다.

[변경 된 ATL DHTML 컨트롤 테스트](../atl/testing-the-modified-atl-dhtml-control.md)<br/>
컨트롤의 추가 기능을 테스트 하는 방법을 보여 줍니다.

## <a name="related-sections"></a>관련 단원

[ATL](../atl/active-template-library-atl-concepts.md)<br/>
액티브 템플릿 라이브러리를 사용하여 프로그래밍하는 방법에 대한 개념 항목의 링크를 제공합니다.
