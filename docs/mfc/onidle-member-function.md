---
title: OnIdle 멤버 함수
ms.date: 11/19/2018
f1_keywords:
- OnIdle
helpviewer_keywords:
- processing messages [MFC]
- OnIdle method [MFC]
- idle loop processing [MFC]
- CWinApp class [MFC], OnIdle method [MFC]
- message handling [MFC], OnIdle method [MFC]
ms.assetid: 51adc874-0075-4f76-be1c-79283f46c10b
ms.openlocfilehash: c7cdd5cd2327be1b90e7fdb3694353acf8adcafe
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62394564"
---
# <a name="onidle-member-function"></a>OnIdle 멤버 함수

Windows 메시지가 처리 되는 경우 프레임 워크에서 호출 된 [CWinApp](../mfc/reference/cwinapp-class.md) 멤버 함수 [OnIdle](../mfc/reference/cwinapp-class.md#onidle) (MFC 라이브러리 참조에서 설명).

재정의 `OnIdle` 백그라운드 작업을 수행할 수 있습니다. 기본 버전을 도구 모음 단추와 같은 사용자 인터페이스 개체의 상태를 업데이트 하 고 해당 작업 하는 과정에서 프레임 워크에 의해 생성 된 임시 개체의 정리를 수행 합니다. 다음 그림은 메시지 루프를 호출 하는 방법을 보여 줍니다. `OnIdle` 큐에 메시지가 없는 경우.

![메시지 루프 프로세스](../mfc/media/vc387c1.gif "메시지 루프 프로세스") <br/>
메시지 루프

유휴 루프에서 수행할 수 있는 작업에 대 한 자세한 내용은 참조 하세요. [유휴 루프 처리](../mfc/idle-loop-processing.md)합니다.

## <a name="see-also"></a>참고자료

[CWinApp: 애플리케이션 클래스](../mfc/cwinapp-the-application-class.md)
