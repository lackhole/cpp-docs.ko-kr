---
title: 대화 상자 초기화
ms.date: 11/04/2016
helpviewer_keywords:
- initializing dialog boxes [MFC]
- OnInitDialog method [MFC]
- modal dialog boxes [MFC], initializing
- modeless dialog boxes [MFC], initializing
- MFC dialog boxes [MFC], initializing
ms.assetid: 968142f5-19f9-4b34-a1d4-8e6412d4379b
ms.openlocfilehash: 14cdf94bef79f254b4aaa2c1c0dfba6c88b7498b
ms.sourcegitcommit: 1e6386be9084f70def7b3b8b4bab319a117102b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/30/2019
ms.locfileid: "71685618"
---
# <a name="initializing-the-dialog-box"></a>대화 상자 초기화

대화 상자와 모든 컨트롤이 만들어졌지만 화면에 대화 상자를 표시 하기 바로 전에 대화 상자 개체의 [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) 멤버 함수가 호출 됩니다. 모달 대화 상자의 경우 `DoModal` 호출 중에 발생 합니다. 모덜리스 대화 상자의 경우 `Create`이 호출 될 때 `OnInitDialog`이 호출 됩니다. 일반적으로 `OnInitDialog`을 재정의 하 여 편집 상자의 초기 텍스트를 설정 하는 것과 같은 대화 상자의 컨트롤을 초기화 합니다. @No__t-2 재정의에서 기본 클래스 `CDialog`의 `OnInitDialog` 멤버 함수를 호출 해야 합니다.

대화 상자의 배경색 및 응용 프로그램의 다른 모든 대화 상자를 설정 하려면 [대화 상자의 배경색 설정](../mfc/setting-the-dialog-boxs-background-color.md)을 참조 하세요.

## <a name="see-also"></a>참조

[MFC에서 대화 상자 작업](../mfc/life-cycle-of-a-dialog-box.md)
