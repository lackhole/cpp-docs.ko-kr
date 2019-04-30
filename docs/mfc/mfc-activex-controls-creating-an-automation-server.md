---
title: 'MFC ActiveX 컨트롤: 자동화 서버 만들기'
ms.date: 11/04/2016
helpviewer_keywords:
- Automation servers [MFC], MFC ActiveX controls
- ActiveX controls [MFC], Automation server
- MFC ActiveX controls [MFC], Automation server
ms.assetid: e0c24ed2-d61c-49ad-a4fa-4e1098d1d39b
ms.openlocfilehash: 01f0162e124c5c49d45ce4a90f5243c88b09b5a0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62225253"
---
# <a name="mfc-activex-controls-creating-an-automation-server"></a>MFC ActiveX 컨트롤: 자동화 서버 만들기

프로그래밍 방식으로 제어 하는 다른 응용 프로그램에 포함 하 고 응용 프로그램에서 컨트롤의 메서드를 호출 하기 위해 자동화 서버로 MFC ActiveX 컨트롤을 개발할 수 있습니다. 이러한 컨트롤은 여전히 ActiveX 컨트롤 컨테이너에서 호스팅해야 수 없습니다.

### <a name="to-create-a-control-as-an-automation-server"></a>자동화 서버로 컨트롤을 만들려면

1. [만들](../mfc/reference/mfc-activex-control-wizard.md) 컨트롤입니다.

1. [메서드 추가](../mfc/mfc-activex-controls-methods.md)합니다.

1. 재정의 [IsInvokeAllowed](../mfc/reference/colecontrol-class.md#isinvokeallowed)합니다.

1. 컨트롤을 빌드하십시오.

### <a name="to-programmatically-access-the-methods-in-an-automation-server"></a>자동화 서버에 있는 메서드를 프로그래밍 방식으로 액세스 하려면

1. 예를 들어 응용 프로그램을 만들려면, [MFC exe](../mfc/reference/mfc-application-wizard.md)합니다.

1. 맨 앞에 `InitInstance` 함수를 다음 줄을 추가 합니다.

   [!code-cpp[NVC_MFC_AxCont#17](../mfc/codesnippet/cpp/mfc-activex-controls-creating-an-automation-server_1.cpp)]

1. 클래스 뷰에서 프로젝트 노드를 마우스 오른쪽 단추로 클릭 하 고 선택 **typelib의 클래스 추가** 형식 라이브러리를 가져옵니다.

   이렇게 하면 파일 확장명이.h 및.cpp 파일을 프로젝트에 추가 됩니다.

1. 헤더 파일에서 클래스의 하나 이상의 메서드를 호출 하는 ActiveX 컨트롤의는 여기서 다음 줄을 추가 합니다. `#include filename.h`, 여기서 파일 name은 형식 라이브러리를 가져올 때 생성 된 헤더 파일의 이름입니다.

1. ActiveX 컨트롤의 메서드는 전화를 걸 수 있는 함수에서 컨트롤의 래퍼 클래스의 개체를 만드는 코드를 추가 하 고 ActiveX 개체를 만듭니다. 예를 들어, 다음과 같은 MFC 코드 인스턴스화합니다를 `CCirc` 제어 캡션 속성을 가져옵니다 및 대화 상자에서 확인 단추를 클릭 하면 결과 표시 합니다.

   [!code-cpp[NVC_MFC_AxCont#18](../mfc/codesnippet/cpp/mfc-activex-controls-creating-an-automation-server_2.cpp)]

응용 프로그램에서 사용 후 ActiveX 컨트롤에 메서드 추가 하는 경우 응용 프로그램에서 컨트롤의 최신 버전을 사용 하 여 형식 라이브러리를 가져올 때 생성 된 파일을 삭제 하 여 시작할 수 있습니다. 다음 형식 라이브러리를 다시 가져오십시오.

## <a name="see-also"></a>참고자료

[MFC ActiveX 컨트롤](../mfc/mfc-activex-controls.md)
