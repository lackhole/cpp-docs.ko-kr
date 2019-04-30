---
title: 'ActiveX 컨트롤 컨테이너: 컨트롤 컨테이너 응용 프로그램에 컨트롤 삽입'
ms.date: 11/04/2016
helpviewer_keywords:
- ActiveX control containers [MFC], inserting controls
- ActiveX controls [MFC], adding to projects
ms.assetid: bbb617ff-872f-43d8-b4d6-c49adb16b148
ms.openlocfilehash: 5f2b964d337ee882bff8acd904ad2fcf64879f88
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62338235"
---
# <a name="activex-control-containers-inserting-a-control-into-a-control-container-application"></a>ActiveX 컨트롤 컨테이너: 컨트롤 컨테이너 응용 프로그램에 컨트롤 삽입

ActiveX 컨트롤을 사용 하 여 컨테이너 응용 프로그램을 추가 해야 합니다 ActiveX 컨트롤 컨테이너 응용 프로그램에서 ActiveX 컨트롤에 액세스 하려면, 먼저 합니다 [ActiveX 컨트롤 삽입](../windows/insert-activex-control-dialog-box.md) 대화 상자.

ActiveX 컨트롤에 ActiveX 컨트롤 컨테이너 프로젝트를 추가 하려면 참조 [보기 및 대화 상자에 ActiveX 컨트롤 추가](../windows/viewing-and-adding-activex-controls-to-a-dialog-box.md)합니다.

컨트롤에 추가한 후 대화 상자 클래스 (ActiveX 컨트롤 형식)의 멤버 변수를 추가 해야 합니다. 이 절차에 대 한 자세한 내용은 참조 하세요. [멤버 변수 추가](../ide/adding-a-member-variable-visual-cpp.md)합니다.

추가한 후 래퍼 클래스 라고 멤버 변수 클래스를 자동으로 생성 되어 프로젝트에 추가 합니다. 이 클래스는 컨트롤 컨테이너와 포함 된 컨트롤 간의 인터페이스로 사용 됩니다.

## <a name="see-also"></a>참고자료

[ActiveX 컨트롤 컨테이너](../mfc/activex-control-containers.md)
