---
title: 테스트 컨테이너로 속성 및 이벤트 테스트
ms.date: 11/04/2016
helpviewer_keywords:
- testing, test containers
- tstcon32.exe
- debugging ActiveX controls
- test container
- ActiveX Control Test Container
- ActiveX controls [MFC], testing
- properties [MFC], testing
ms.assetid: 626867cf-fe53-4c30-8973-55bb93ef3917
ms.openlocfilehash: 977ef29095e652ab40028a2e8ba7feffabf56418
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58781070"
---
# <a name="testing-properties-and-events-with-test-container"></a>테스트 컨테이너로 속성 및 이벤트 테스트

테스트 컨테이너 응용 프로그램을 Visual c + +에서 제공 되는 ActiveX 컨트롤 컨테이너를 사용 하 여 테스트 및 ActiveX 컨트롤 디버깅입니다. 테스트 컨테이너는 컨트롤 개발자를 해당 속성을 변경 하 고 해당 메서드를 호출 해당 이벤트를 발생 하 여 컨트롤의 기능을 테스트할 수 있습니다. 테스트 컨테이너 데이터 바인딩 알림의 로그를 표시할 수 있습니다 및 ActiveX 컨트롤의 지 속성 기능을 테스트 하는 기능 제공: 스트림 또는 하위 속성을 저장, 다시 로드 하면 하는 저장 된 스트림 데이터를 검토할 수 있습니다. 이 섹션에서는 테스트 컨테이너의 기본 기능을 사용 하는 방법을 설명 합니다. 자세한 내용은 다음을 선택 합니다 **도움말** 테스트 컨테이너를 실행 하는 동안 메뉴.

### <a name="to-access-the-activex-control-test-container"></a>ActiveX 컨트롤 테스트 컨테이너에 액세스 하려면

1. 빌드는 [TSTCON 샘플: ActiveX Control Test Container](../overview/visual-cpp-samples.md)합니다.

### <a name="to-test-your-activex-control"></a>ActiveX 컨트롤을 테스트 하려면

1. 에 **편집할** 테스트 컨테이너의 메뉴 클릭 **새 컨트롤 삽입**합니다.

1. 에 **컨트롤 삽입** 상자에서 원하는 컨트롤을 선택 및 클릭 **확인**합니다. 컨트롤은 컨트롤 컨테이너에 표시 됩니다.

    > [!NOTE]
    >  컨트롤에 없는 경우는 **컨트롤 삽입** 대화 상자를 사용 하 여 등록 되었는지 확인 합니다 **컨트롤 등록** 명령을 합니다 **파일** 테스트의 메뉴 컨테이너입니다.

이 시점에서 컨트롤의 속성 또는 이벤트를 테스트할 수 있습니다.

#### <a name="to-test-properties"></a>속성을 테스트 하려면

1. 에 **제어** 메뉴에서 클릭 **메서드 호출**합니다.

1. 에 **메서드 이름** 드롭 다운 목록에서 테스트 하려는 속성의 PropPut 메서드를 선택 합니다.

1. 수정 합니다 **매개 변수 값** 또는 **매개 변수 형식** 클릭 합니다 **값 설정** 단추.

1. 클릭 **Invoke** 개체에 새 값을 적용 합니다.

   속성에는 이제 새 값을 포함 합니다.

#### <a name="to-test-events-and-specify-the-destination-of-event-information"></a>테스트 이벤트 및 이벤트 정보의 대상을 지정 합니다.

1. 에 **옵션** 메뉴에서 클릭 **로깅**합니다.

1. 대상 이벤트 정보를 지정 합니다.

## <a name="see-also"></a>참고자료

[MFC ActiveX 컨트롤](../mfc/mfc-activex-controls.md)<br/>
[방법: ActiveX 컨트롤 디버그](/visualstudio/debugger/how-to-debug-an-activex-control)
