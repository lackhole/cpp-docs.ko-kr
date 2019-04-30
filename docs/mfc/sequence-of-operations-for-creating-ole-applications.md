---
title: OLE 응용 프로그램을 만드는 작업 시퀀스
ms.date: 11/04/2016
helpviewer_keywords:
- OLE applications [MFC], creating
- OLE applications [MFC]
- applications [OLE], creating
- applications [OLE]
ms.assetid: 84b0f606-36c1-4253-9cea-44427f0074b9
ms.openlocfilehash: b7fa989d1a3b799cf6b427e27142d4479be900bf
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62308188"
---
# <a name="sequence-of-operations-for-creating-ole-applications"></a>OLE 응용 프로그램을 만드는 작업 시퀀스

다음 표에서 OLE 연결과 응용 프로그램을 만드는 사용자의 역할 및 프레임 워크의 역할을 보여 줍니다. 이러한 하는 데 단계의 순서를 대신 사용할 수 있는 옵션을 나타냅니다.

### <a name="creating-ole-applications"></a>OLE 응용 프로그램 만들기

|작업|너 해|프레임 워크|
|----------|------------|------------------------|
|COM 구성 요소를 만듭니다.|MFC 응용 프로그램 마법사를 실행 합니다. 선택 **전체 서버** 하거나 **미니 서버** 에 **복합 문서 지원** 탭 합니다.|프레임 워크를 사용 하도록 설정 하는 COM 구성 요소 기능을 사용 하 여 기본 응용 프로그램을 생성 합니다. 모든 COM 기능을 약간만 수정 하면 기존 응용 프로그램에 전송할 수 있습니다.|
|컨테이너 응용 프로그램을 처음부터 새로 만듭니다.|MFC 응용 프로그램 마법사를 실행 합니다. 선택할 **컨테이너** 에 **복합 문서 지원** 탭 합니다. 클래스 뷰를 사용 하는 소스 코드 편집기로 이동 합니다. COM 처리기 함수에 대 한 코드를 입력 합니다.|프레임 워크에는 COM 구성 요소 (서버) 응용 프로그램에서 생성 된 COM 개체를 삽입할 수 있는 기본 응용 프로그램을 생성 합니다.|
|부터 자동화를 지 원하는 응용 프로그램을 만듭니다.|MFC 응용 프로그램 마법사를 실행 합니다. 선택할 **Automation** 에서 합니다 **고급 기능** 탭 합니다. 클래스 뷰를 사용 하 여 자동화에 대 한 응용 프로그램의 메서드와 속성을 표시 합니다.|프레임 워크를 활성화 하 고 다른 응용 프로그램에서 자동화할 수 있는 기본 응용 프로그램을 생성 합니다.|

## <a name="see-also"></a>참고자료

[프레임워크를 기반으로 구축](../mfc/building-on-the-framework.md)<br/>
[MFC 애플리케이션을 빌드하는 작업 시퀀스](../mfc/sequence-of-operations-for-building-mfc-applications.md)<br/>
[ActiveX 컨트롤을 만드는 작업 시퀀스](../mfc/sequence-of-operations-for-creating-activex-controls.md)<br/>
[데이터베이스 애플리케이션을 만드는 작업 시퀀스](../mfc/sequence-of-operations-for-creating-database-applications.md)
