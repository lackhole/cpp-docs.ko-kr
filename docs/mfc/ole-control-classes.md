---
title: OLE 컨트롤 클래스
ms.date: 11/04/2016
f1_keywords:
- vc.classes.ole
helpviewer_keywords:
- ActiveX classes [MFC]
- custom controls [MFC], classes
- ActiveX controls [MFC], OLE control classes
- ActiveX control classes [MFC]
- OLE controls [MFC], classes
- OLE control classes [MFC]
- reusable component classes [MFC]
ms.assetid: 96495ec3-319e-4163-b839-1af0428ed9dd
ms.openlocfilehash: 86470c3e3e66d6aee2ce532570cea096641d2c1d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62186090"
---
# <a name="ole-control-classes"></a>OLE 컨트롤 클래스

이들은 OLE 컨트롤을 작성할 때 사용 되는 기본 클래스입니다. `COleControlModule` 와 같은 OLE 컨트롤 모듈에는 클래스는를 [CWinApp](../mfc/reference/cwinapp-class.md) 응용 프로그램의 클래스입니다. 각 모듈에는 하나 이상의 OLE 컨트롤; 구현 이러한 컨트롤은 `COleControl` 개체입니다. 이러한 제어를 사용 하 여 해당 컨테이너를 사용 하 여 통신 `CConnectionPoint` 개체입니다.

`CPictureHolder` 및 `CFontHolder` 클래스 사진 및 글꼴에 대 한 COM 인터페이스를 캡슐화 하는 동안 합니다 `COlePropertyPage` 및 `CPropExchange` 클래스 속성 페이지 및 컨트롤에 대 한 지 속성 속성을 구현 하는 데 도움이 합니다.

[COleControlModule](../mfc/reference/colecontrolmodule-class.md)<br/>
대체는 `CWinApp` OLE 컨트롤 모듈에 대 한 클래스입니다. 파생 된 `COleControlModule` OLE 컨트롤 모듈 개체를 개발 하는 클래스입니다. OLE 컨트롤의 모듈을 초기화 하는 것에 대 한 멤버 함수를 제공 합니다.

[COleControl](../mfc/reference/colecontrol-class.md)<br/>
파생 된 `COleControl` OLE 컨트롤을 개발 하는 클래스입니다. 파생 된 `CWnd`,이 클래스는 이벤트 발생 메서드와 속성을 지 원하는 기능 등의 추가 OLE 관련 기능을 포함 하 고 Windows 창 개체의 모든 기능을 상속 합니다.

[CConnectionPoint](../mfc/reference/cconnectionpoint-class.md)<br/>
`CConnectionPoint` 클래스는 특수 한 유형의 연결 지점 이라고 하는 다른 OLE 개체와 통신 하는 데 사용 되는 인터페이스를 정의 합니다. 연결 지점 이벤트를 발생 시키고 같은 다른 개체에 대 한 작업을 시작 하 고 변경 알림을 수 있는 송신 인터페이스를 구현 합니다.

[CPictureHolder](../mfc/reference/cpictureholder-class.md)<br/>
Windows 그림 개체의 기능을 캡슐화 하며 `IPicture` COM 인터페이스에 OLE 컨트롤의 사용자 지정 그림 속성을 구현 하는 데 사용 합니다.

[CFontHolder](../mfc/reference/cfontholder-class.md)<br/>
Windows 글꼴 개체의 기능을 캡슐화 하며 `IFont` COM 인터페이스에 OLE 컨트롤의 스톡 글꼴 속성을 구현 하는 데 사용 합니다.

[COlePropertyPage](../mfc/reference/colepropertypage-class.md)<br/>
대화 상자에 유사한 그래픽 인터페이스에서 제어 OLE의 속성을 표시 합니다.

[CPropExchange](../mfc/reference/cpropexchange-class.md)<br/>
OLE 컨트롤 속성 지 속성 구현을 지원합니다. 비슷합니다 [CDataExchange](../mfc/reference/cdataexchange-class.md) 대화 상자에 대 한 합니다.

[CMonikerFile](../mfc/reference/cmonikerfile-class.md)<br/>
모니커를 만들 수 있는 문자열 표현이 나 모니커를 사용 하 고는 모니커는 이름이 있는 스트림에 동기적으로 바인딩합니다.

[CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md)<br/>
유사 하 게 작동 `CMonikerFile`하지만 모니커 이름의 스트림의을 비동기적으로 모니커에 바인딩합니다.

[CDataPathProperty](../mfc/reference/cdatapathproperty-class.md)<br/>
비동기적으로 로드할 수 있는 OLE 컨트롤 속성을 구현합니다.

[CCachedDataPathProperty](../mfc/reference/ccacheddatapathproperty-class.md)<br/>
비동기적으로 전송되고 메모리 파일에 캐싱되는 OLE 컨트롤 속성을 구현합니다.

[COleCmdUI](../mfc/reference/colecmdui-class.md)<br/>
액티브 문서 컨테이너의 사용자 인터페이스 (예: FileNew, 열기, 인쇄 및 등)에서 발생 하는 명령을 수신 하도록 허용 하 고 활성 문서의 사용자 인터페이스에서 발생 하는 명령을 수신 하는 컨테이너를 허용 합니다.

[COleSafeArray](../mfc/reference/colesafearray-class.md)<br/>
임의의 형식 및 차원 배열 사용 하 여 작동 합니다.

## <a name="see-also"></a>참고자료

[클래스 개요](../mfc/class-library-overview.md)
