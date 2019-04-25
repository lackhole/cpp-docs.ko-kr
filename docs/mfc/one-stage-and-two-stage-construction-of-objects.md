---
title: 1단계 및 2단계 개체 생성
ms.date: 11/04/2016
helpviewer_keywords:
- objects [MFC], creating graphic objects
- object creation [MFC], graphic objects
- objects [MFC], graphic objects
- one-stage and two-stage construction of objects [MFC]
ms.assetid: 5a1c410c-4a4b-4dd9-a2ec-ced831aa7f21
ms.openlocfilehash: 871db7abd2682d557bf2e80e9cb97624f0dc53a6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62160161"
---
# <a name="one-stage-and-two-stage-construction-of-objects"></a>1단계 및 2단계 개체 생성

펜 및 브러시와 같은 그래픽 개체를 만들기 위한 두 가지 기술 중 하나를 선택을 해야 합니다.

- *1 단계 생성*: 생성 하 고 in one stage을 생성자를 사용 하 여 모든 개체를 초기화 합니다.

- *2 단계 생성*: 생성 하 고 별도의 두 단계로 개체를 초기화 합니다. 생성자는 개체를 만들고 초기화 함수를 초기화 합니다.

2 단계 생성이 항상 안전 합니다. 1 단계 생성에서 메모리 할당이 실패 하거나 잘못 된 인수를 제공 하는 경우 생성자는 예외를 throw 수 없습니다. 오류를 확인 해야 하지만 2 단계 생성 하 여 문제를 금지 합니다. 두 경우 모두 개체를 소멸은 동일한 프로세스입니다.

> [!NOTE]
>  이러한 기술은 모든 개체 그래픽 개체 뿐 아니라 만들기에 적용 됩니다.

## <a name="example-of-both-construction-techniques"></a>두 가지 방법 모두 생성의 예

다음 간단한 예제에서는 pen 개체를 생성 하는 두 방법을 모두 보여 줍니다.

[!code-cpp[NVC_MFCDocViewSDI#6](../mfc/codesnippet/cpp/one-stage-and-two-stage-construction-of-objects_1.cpp)]

### <a name="what-do-you-want-to-know-more-about"></a>자세히 알아볼 항목

- [그래픽 개체](../mfc/graphic-objects.md)

- [그래픽 개체를 선택 하 여 장치 컨텍스트로](../mfc/selecting-a-graphic-object-into-a-device-context.md)

- [장치 컨텍스트](../mfc/device-contexts.md)

- [뷰에 그리기](../mfc/drawing-in-a-view.md)

## <a name="see-also"></a>참고자료

[그래픽 개체](../mfc/graphic-objects.md)
