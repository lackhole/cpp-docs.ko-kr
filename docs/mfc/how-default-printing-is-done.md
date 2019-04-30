---
title: 기본 인쇄가 수행되는 방법
ms.date: 11/04/2016
helpviewer_keywords:
- default printing
- printing [MFC], default
- defaults, printing
ms.assetid: 0f698459-0fc9-4d43-97da-29cf0f65daa2
ms.openlocfilehash: 5f7971b48c9050e315b2fd57d2f3449517afa07e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62254324"
---
# <a name="how-default-printing-is-done"></a>기본 인쇄가 수행되는 방법

이 문서에서는 MFC 프레임워크의 관점에서 Windows의 기본 인쇄 프로세스에 대해 설명합니다.

MFC 응용 프로그램에서 뷰 클래스에는 모든 그리기 코드를 포함하는 `OnDraw`라는 멤버 함수가 포함되어 있습니다. `OnDraw` 에 대 한 포인터를 [CDC](../mfc/reference/cdc-class.md) 개체를 매개 변수로 합니다. 이 `CDC` 개체는 `OnDraw`에서 생성되는 이미지를 수신하기 위한 장치 컨텍스트를 나타냅니다. 문서를 표시 하는 창이 받으면를 [WM_PAINT](/windows/desktop/gdi/wm-paint) 메시지, 프레임 워크 호출 `OnDraw` 화면에 대 한 장치 컨텍스트를 전달 하 고 (을 [CPaintDC](../mfc/reference/cpaintdc-class.md) 구체적 개체). 따라서 `OnDraw`의 출력이 화면으로 이동합니다.

Windows 프로그래밍에서 프린터로 출력을 전송하는 것은 화면으로 출력을 전송하는 것과 매우 비슷합니다. 그 이유는 Windows GDI(그래픽 장치 인터페이스)가 하드웨어에 독립적이기 때문입니다. 단순히 적절한 장치 컨텍스트만 사용해도 화면 표시 또는 인쇄를 위해 동일한 GDI 함수를 사용할 수 있습니다. `CDC`가 수신하는 `OnDraw` 개체가 프린터를 나타낼 경우, `OnDraw`의 출력은 프린터로 이동합니다.

이렇게 해서 추가적인 노력 없이도 MFC 응용 프로그램에서 간단한 인쇄를 수행할 수 있습니다. 인쇄 대화 상자를 표시하고 프린터에 대한 장치 컨텍스트를 만드는 작업은 프레임워크에서 수행됩니다. 사용자가 파일 메뉴에서 인쇄 명령을 선택하면 뷰가 이 장치 컨텍스트를 `OnDraw`에 전달하고, 프린터에서 문서가 출력됩니다.

하지만 인쇄와 화면 표시 사이에는 몇 가지 중요한 차이점이 있습니다. 인쇄할 때는 창에 특정 부분을 표시하는 대신 문서를 고유 페이지로 나누고 한 번에 하나씩 표시해야 합니다. 그 결과, 용지 크기(레터 크기, 리걸 크기 또는 봉투 등)를 알고 있어야 합니다. 가로 또는 세로 모드와 같이 방향을 다르게 인쇄해야 할 수도 있습니다. Microsoft Foundation Class 라이브러리는 응용 프로그램에서 이러한 문제를 어떻게 처리할지 예측할 수 없으므로, 이러한 기능을 추가할 수 있는 프로토콜을 제공합니다.

프로토콜 문서에 설명 되어 있는지 [다중 페이지 문서](../mfc/multipage-documents.md)합니다.

## <a name="see-also"></a>참고자료

[인쇄](../mfc/printing.md)
