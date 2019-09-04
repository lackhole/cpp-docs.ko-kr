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

Windows 메시지가 처리되지 않고 있는 경우 프레임워크는 [CWinApp](../mfc/reference/cwinapp-class.md)의 멤버 함수 [OnIdle](../mfc/reference/cwinapp-class.md#onidle)을 호출합니다(MFC 라이브러리 참조에서 설명).

백그라운드 작업을 수행하려면 `OnIdle`을 재정의합니다. 기본 버전은 도구 모음 버튼과 같은 사용자 인터페이스 개체의 상태를 업데이트하고 작업 과정에서 프레임워크가 생성한 임시 개체를 정리합니다. 다음 그림은 큐에 메시지가 없는 경우 메시지 루프가 `OnIdle`을  호출하는 방식을 보여줍니다.

![메시지 루프 프로세스](../mfc/media/vc387c1.gif "메시지 루프 프로세스") <br/>
메시지 루프

유휴 루프에서 수행할 수 있는 작업에 대한 자세한 내용은 [유휴 루프 처리](../mfc/idle-loop-processing.md)를 참조합니다.

## <a name="see-also"></a>참고자료

[CWinApp: 애플리케이션 클래스](../mfc/cwinapp-the-application-class.md)
