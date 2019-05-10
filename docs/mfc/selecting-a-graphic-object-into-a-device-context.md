---
title: 그래픽 개체를 선택하여 장치 컨텍스트로 넣기
ms.date: 11/04/2016
helpviewer_keywords:
- graphic objects [MFC], selecting into device context
- SelectObject method [MFC]
- GDI objects [MFC], device contexts
- lifetime, graphic objects [MFC]
- device contexts, selecting graphic objects into
- device contexts, graphic objects [MFC]
ms.assetid: cf54a330-63ef-421f-83eb-90ec7bd82eef
ms.openlocfilehash: 7fb1507c1200da4cdf44627557ff6993e927d51e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62308533"
---
# <a name="selecting-a-graphic-object-into-a-device-context"></a>그래픽 개체를 선택하여 장치 컨텍스트로 넣기

이 항목에서는 창 디바이스 컨텍스트에서 그래픽 개체를 사용 하 여에 적용 됩니다. 한 후 [그리기 개체를 만들](../mfc/one-stage-and-two-stage-construction-of-objects.md), 여기에 저장 된 기본 개체 대신 장치 컨텍스트로 선택 해야 합니다.

[!code-cpp[NVC_MFCDocViewSDI#7](../mfc/codesnippet/cpp/selecting-a-graphic-object-into-a-device-context_1.cpp)]

## <a name="lifetime-of-graphic-objects"></a>그래픽 개체의 수명

그래픽 개체를 반환한 [SelectObject](../mfc/reference/cdc-class.md#selectobject) 됩니다 "." 까지 삭제 될 예정 이므로 합니다 [OnIdle](../mfc/reference/cwinapp-class.md#onidle) 클래스의 멤버 함수 `CWinApp` 다음에 프로그램이 가져옵니다 유휴 시간입니다. 반환 된 개체를 사용으로 `SelectObject` 아무런 문제가 주 메시지 루프에 컨트롤을 반환 하지 않고 단일 함수에서 해야 합니다.

### <a name="what-do-you-want-to-know-more-about"></a>자세히 알아볼 항목

- [그래픽 개체](../mfc/graphic-objects.md)

- [1 단계 및 2 단계 그래픽 개체 생성](../mfc/one-stage-and-two-stage-construction-of-objects.md)

- [장치 컨텍스트](../mfc/device-contexts.md)

- [뷰에 그리기](../mfc/drawing-in-a-view.md)

## <a name="see-also"></a>참고자료

[그래픽 개체](../mfc/graphic-objects.md)
