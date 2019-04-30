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
ms.openlocfilehash: 87b3405f1441e730cf5c9ce7fc03d2c7372e55db
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62297101"
---
# <a name="initializing-the-dialog-box"></a>대화 상자 초기화

후 대화 상자와 모든 해당 컨트롤에 작성 됩니다만 표시 되기 전에 대화 상자 (두 가지 형식의) 화면에서 대화 상자 개체의 [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) 멤버 함수를 호출 합니다. 모달 대화 상자에 대해이 중에 발생 합니다 `DoModal` 호출 합니다. 모덜리스 대화 상자에 대해 `OnInitDialog` 될 때 호출 됩니다 `Create` 라고 합니다. 일반적으로 재정의 `OnInitDialog` 입력란의 초기 텍스트를 설정 하는 등 대화 상자의 컨트롤을 초기화 합니다. 호출 해야 합니다는 `OnInitDialog` 기본 클래스의 멤버 함수 `CDialog`에서 프로그램 `OnInitDialog` 재정의 합니다.

대화 상자의 배경 색과 응용 프로그램의 다른 모든 대화 상자는 설정 하려는 경우 참조 [대화 상자의 배경색 설정](../mfc/setting-the-dialog-boxs-background-color.md)합니다.

## <a name="see-also"></a>참고자료

[대화 상자의 수명 주기](../mfc/life-cycle-of-a-dialog-box.md)
