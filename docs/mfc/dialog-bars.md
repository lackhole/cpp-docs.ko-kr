---
title: 대화 상자 모음
ms.date: 11/19/2018
helpviewer_keywords:
- MFC, control bars
- CDialogBar class [MFC], dialog bars
- control bars [MFC], dialog bars
- dialog bars
- dialog bars [MFC], about dialog bars
ms.assetid: 485c8055-6bb0-4051-8417-dd2971499321
ms.openlocfilehash: e4e843327daba6f0aa468cb07394165bc70fa7f0
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "58779510"
---
# <a name="dialog-bars"></a>대화 상자 모음

대화 상자 막대는 도구 모음에서 일종의 [컨트롤 막대](../mfc/control-bars.md) 하는 모든 종류의 컨트롤을 포함할 수 있습니다. 모덜리스 대화 상자에서의 특징을 있기 때문에 [CDialogBar](../mfc/reference/cdialogbar-class.md) 개체는 더 강력한 도구 모음을 제공 합니다.

여러 키 간에 차이가 도구 모음 및 `CDialogBar` 개체입니다. `CDialogBar` Visual c + + 대화 상자 편집기를 사용 하 여 만들 수 있는 및 모든 종류의 Windows 컨트롤을 포함할 수 있는 대화 상자 템플릿 리소스에서 개체가 만들어집니다. 사용자는 컨트롤을 컨트롤에서 탭 수입니다. 및 부모 조정 된 경우이를 그대로 둘 수도 또는 부모 프레임 창의 일부를 사용 하 여 대화 상자 막대에 맞게 맞춤 스타일을 지정할 수 있습니다. 다음 그림에는 다양 한 컨트롤을 사용 하 여 대화 상자 막대를 보여 줍니다.

![VC 대화 상자 막대](../mfc/media/vc378t1.gif "VC 대화 상자 모음") <br/>
대화 상자 모음

작업 측면에서는 `CDialogBar` 개체가 같은 모덜리스 대화 상자를 사용 합니다. 대화 상자 편집기를 사용 하 여 디자인 하 고 대화 상자 리소스를 만들어야 합니다.

대화 상자 막대의 장점 중 하나입니다 단추 이외의 컨트롤을 포함할 수 있습니다.

고유한 대화 상자 클래스에서 파생 시키는 것 `CDialog`, 대화 상자 막대에 대 한 사용자 고유의 클래스를 일반적으로 파생 되지 않은 합니다. 같은 대화 상자 막대는 주 창 하는 모든 대화 상자 막대 컨트롤 알림 메시지를 확장 **BN_CLICKED** 하거나 **에서 EN_CHANGE**, 가로 막대형, 주 창 대화의 부모로 전송 됩니다.

## <a name="see-also"></a>참고자료

[사용자 인터페이스 요소](../mfc/user-interface-elements-mfc.md)<br/>
[샘플](../overview/visual-cpp-samples.md)
