---
title: 일반적으로 재정의되는 멤버 함수
ms.date: 11/04/2016
helpviewer_keywords:
- CDialog class [MFC], members
- OnInitDialog function
- dialog classes [MFC], commonly overridden member functions
- OnCancel function
- overriding, dialog class members
- OnOK function
- MFC dialog boxes [MFC], overriding member functions
ms.assetid: 78eb566c-e361-4c86-8db5-c7e2791b249a
ms.openlocfilehash: 26a1527dbdac4b2a9deb57fb13481f8d2f9cb5b7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62152034"
---
# <a name="commonly-overridden-member-functions"></a>일반적으로 재정의되는 멤버 함수

다음 표에서 가능성이에서 재정의 하는 멤버 함수에 `CDialog`-클래스를 파생 합니다.

### <a name="commonly-overridden-member-functions-of-class-cdialog"></a>일반적으로 재정의 되는 CDialog 클래스의 멤버 함수

|멤버 함수|응답 메시지|재정의의 용도|
|---------------------|----------------------------|-----------------------------|
|`OnInitDialog`|**WM_INITDIALOG**|대화 상자의 컨트롤을 초기화 합니다.|
|`OnOK`|**BN_CLICKED** 단추에 대 한 **IDOK**|확인 단추를 클릭할 때 응답 합니다.|
|`OnCancel`|**BN_CLICKED** 단추에 대 한 **IDCANCEL**|취소 단추를 클릭할 때 응답 합니다.|

`OnInitDialog`를 `OnOK`, 및 `OnCancel` 는 가상 함수입니다. 을 재정의 하려면 사용 하 여 파생 된 대화 상자 클래스에서 재정의 함수를 선언 합니다 [속성 창](/visualstudio/ide/reference/properties-window)합니다.

`OnInitDialog` 대화 상자가 표시 됩니다 직전에 호출 됩니다. 기본값을 호출 해야 `OnInitDialog` 재정의에서 처리기-첫 번째 작업 처리기에서 일반적으로 합니다. 기본적으로 `OnInitDialog` 반환 **TRUE** 대화 상자에서 첫 번째 컨트롤에 포커스가 설정 되어야 함을 나타냅니다.

`OnOK` 일반적으로 모덜리스 하지만 하지 모달 대화 상자에 대 한 재정의 됩니다. 모달 대화 상자에 대 한이 처리기를 재정의 하는 경우 재정의에서 기본 클래스 버전을 호출-되도록 `EndDialog` 라고-호출 또는 `EndDialog` 직접.

`OnCancel` 모덜리스 대화 상자에 대 한 일반적으로 재정의 됩니다.

이러한 멤버 함수에 대 한 자세한 내용은 클래스를 참조 하세요. [CDialog](../mfc/reference/cdialog-class.md) 에 *MFC 참조* 에 대해 토론 [대화 상자의 수명 주기](../mfc/life-cycle-of-a-dialog-box.md)합니다.

## <a name="see-also"></a>참고자료

[대화 상자](../mfc/dialog-boxes.md)<br/>
[일반적으로 추가되는 멤버 함수](../mfc/commonly-added-member-functions.md)
