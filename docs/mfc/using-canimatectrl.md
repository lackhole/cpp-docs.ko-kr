---
title: CAnimateCtrl 사용
ms.date: 11/04/2016
f1_keywords:
- CAnimateCtrl
helpviewer_keywords:
- animation controls [MFC], CAnimateCtrl class
- controls [MFC], animation
- CAnimateCtrl class [MFC], about CAnimateCtrl class [MFC]
ms.assetid: 696c0805-bef0-4e2e-a9e7-b37b9215b7f0
ms.openlocfilehash: b967cc6dde6b4f639ef081b3821f6a7e5a2fe295
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62351643"
---
# <a name="using-canimatectrl"></a>CAnimateCtrl 사용

Animation 컨트롤 클래스로 [CAnimateCtrl](../mfc/reference/canimatectrl-class.md), 클립 오디오 비디오 인터리빙 (AVI) 형식으로 표시 되는 창-표준 Windows 비디오/오디오 형식입니다. AVI 클립은 일련의 동영상 같은 비트맵 프레임입니다.

스레드가 계속 AVI 클립 표시 되는 동안 실행을 애니메이션 컨트롤의 일반적 용도 중 하나 이므로 시간이 오래 걸리는 작업 중 시스템 작업을 나타냅니다. 예를 들어 Windows 찾기 대화 상자는 파일 시스템 검색으로 이동 돋보기 효과 표시합니다.

애니메이션 컨트롤 간단한 AVI 클립을 재생할 수만 있습니다 및 소리를 지원 하지 않습니다. (제한의 전체 목록은 참조 하세요 [CAnimateCtrl](../mfc/reference/canimatectrl-class.md).) 애니메이션 컨트롤의 기능 심각 하 게 제한 되므로 및 변경 될 수 있습니다, 멀티미디어 재생 및/또는 기록 기능을 제공 하는 컨트롤이 필요한 경우 MCIWnd 컨트롤과 같은 대안을 사용 해야 합니다. MCIWnd 컨트롤에 대 한 자세한 내용은 멀티미디어 설명서를 참조 하세요.

## <a name="what-do-you-want-to-know-more-about"></a>자세히 알아볼 항목

- [애니메이션 컨트롤 사용](../mfc/using-an-animation-control.md)

- [애니메이션 컨트롤이 보내는 알림](../mfc/notifications-sent-by-animation-controls.md)

## <a name="see-also"></a>참고자료

[컨트롤](../mfc/controls-mfc.md)
