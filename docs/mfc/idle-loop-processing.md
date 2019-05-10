---
title: 유휴 루프 처리
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, background processing
- PeekMessage method [MFC], elsewhere than message loop
- PeekMessage method [MFC]
- MFC, messages
- messages [MFC], loops
- OnIdle method [MFC]
- processing [MFC], background
- idle loop processing [MFC]
- idle processing [MFC]
- threading [MFC], alternatives to multithreading
- processing, during idle loop
- processing [MFC]
- background processing [MFC]
ms.assetid: 5c7c46c1-6107-4304-895f-480983bb1e44
ms.openlocfilehash: 0d0e3fcba9ce447ec359958fc5ed59c6d596dd7a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62219492"
---
# <a name="idle-loop-processing"></a>유휴 루프 처리

대부분의 응용 프로그램 "에서"배경입니다. 시간이 오래 걸리는 처리를 수행합니다. 경우에 따라 성능 고려 사항 이러한 작업에 대 한 다중 스레드를 사용 하 여 지정 합니다. MFC에서 수행 하는 유휴 시간 작업 등의 간단한 작업에 대 한 권장 되지 않습니다 있도록 스레드 추가 개발 오버 헤드를 포함 합니다 [OnIdle](../mfc/reference/cwinthread-class.md#onidle) 함수입니다. 이 문서는 유휴 처리에 중점을 둡니다. 다중 스레딩, 참조에 대 한 자세한 내용은 [다중 스레딩 항목](../parallel/multithreading-support-for-older-code-visual-cpp.md)합니다.

일부 종류의 백그라운드 처리는 사용자가 그렇지 않은 경우 응용 프로그램 상호 작용 하지는 간격 동안 적절 하 게 수행 됩니다. Microsoft Windows 운영 체제에 대 한 개발 된 응용 프로그램에서 응용 프로그램 시간이 오래 걸리는 프로세스가 많은 작은 조각으로 분할 하 여 유휴 시간 처리를 수행할 수 있습니다. 각 조각은 처리 한 후 응용 프로그램 생성을 사용 하 여 Windows 실행 제어를 [PeekMessage](/windows/desktop/api/winuser/nf-winuser-peekmessagea) 루프입니다.

이 문서에서는 유휴 응용 프로그램에서 처리를 수행 하는 두 가지를 설명 합니다.

- 사용 하 여 **PeekMessage** MFC의 기본 메시지 루프에 있습니다.

- 다른 포함 **PeekMessage** 응용 프로그램의 다른 곳을 반복 합니다.

##  <a name="_core_peekmessage_in_the_mfc_message_loop"></a> MFC 메시지 루프의 PeekMessage

MFC를 사용 하 여 개발한 응용 프로그램에서 주 메시지 루프를 `CWinThread` 를 호출 하는 메시지 루프를 포함 하는 클래스를 [PeekMessage](/windows/desktop/api/winuser/nf-winuser-peekmessagea) Win32 API입니다. 이 루프도 호출 합니다 `OnIdle` 멤버 함수 `CWinThread` 메시지 사이입니다. 응용 프로그램 재정의 하 여 유휴 시간에 메시지를 처리할 수는 `OnIdle` 함수입니다.

> [!NOTE]
>  `Run`를 `OnIdle`, 한 다른 멤버 함수는 특정 클래스의 멤버는 이제 `CWinThread` 아닌 클래스의 `CWinApp`합니다. `CWinApp`는 `CWinThread`에서 파생됩니다.

유휴 처리를 수행 하는 방법에 대 한 자세한 내용은 참조 하세요. [OnIdle](../mfc/reference/cwinthread-class.md#onidle) 에 *MFC 참조*합니다.

##  <a name="_core_peekmessage_elsewhere_in_your_application"></a> 응용 프로그램에서 다른 곳에서 PeekMessage

유휴 응용 프로그램에서 처리를 수행 하는 다른 방법은 함수 중 하나에 메시지 루프를 포함 하는 하는 것입니다. 이 메시지 루프는 MFC의 기본 메시지 루프에 있는 매우 비슷합니다 [CWinThread::Run](../mfc/reference/cwinthread-class.md#run)합니다. 즉, MFC를 사용 하 여 개발한 응용 프로그램에서 이러한 루프는 다양 한 기본 메시지 루프와 동일한 기능을 수행 해야 합니다. 다음 코드 조각은 MFC와 호환 되는 메시지 루프를 작성 하는 방법을 보여 줍니다.

[!code-cpp[NVC_MFCDocView#8](../mfc/codesnippet/cpp/idle-loop-processing_1.cpp)]

이 코드는 함수에 포함 된 작업을 수행 하는 유휴 상태 처리가으로 루프입니다. 해당 루프 내에서 중첩 된 루프를 반복적으로 호출 `PeekMessage`합니다. 루프를 호출 하는 호출 하는 0이 아닌 값을 반환 하기만 `CWinThread::PumpMessage` 일반 메시지 변환 및 디스패치를 수행 하 합니다. 하지만 `PumpMessage` 문서화 되 없는 시각적 개체의 \atlmfc\src\mfc 디렉터리 ThrdCore.Cpp 파일에서 소스 코드를 검사할 수 있습니다 C++ 설치 합니다.

한 번 내부 루프가 종료 외부 루프 유휴 처리를 수행 하려면 하나 이상의 호출을 사용 하 여 `OnIdle`입니다. 첫 번째 호출은 MFC의 목적입니다. 추가 호출을 할 수 있습니다 `OnIdle` 고유한 백그라운드 작업을 수행 합니다.

유휴 처리를 수행 하는 방법에 대 한 자세한 내용은 참조 하세요. [OnIdle](../mfc/reference/cwinthread-class.md#onidle) MFC 라이브러리 참조에서 합니다.

## <a name="see-also"></a>참고자료

[일반 MFC 항목](../mfc/general-mfc-topics.md)
