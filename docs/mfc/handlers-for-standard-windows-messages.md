---
title: 표준 Windows 메시지에 대한 처리기
ms.date: 11/04/2016
f1_keywords:
- afx_msg
helpviewer_keywords:
- Windows messages [MFC], handlers
- message handling [MFC], Windows message handlers
- handler functions, standard Windows messages
- functions [MFC], handler
- messages [MFC], Windows
ms.assetid: 19412a8b-2c38-4502-81da-13c823c7e36c
ms.openlocfilehash: d60ae52225ddd993c1768d0b5ce1989ab0192e45
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62358242"
---
# <a name="handlers-for-standard-windows-messages"></a>표준 Windows 메시지에 대한 처리기

표준 Windows 메시지에 대 한 처리기를 기본값 (**WM_**) 클래스에 미리 정의 된 `CWnd`합니다. 이 클래스 라이브러리는 메시지 이름을 기반으로 이러한 처리기의 이름을 지정합니다. 예를 들어 처리기를 **WM_PAINT** 메시지에서 선언 된 `CWnd` 으로:

`afx_msg void OnPaint();`

**afx_msg** 키워드의 효과 제안 합니다 C++ **가상** 처리기는 서로 구분 하 여 `CWnd` 멤버 함수입니다. 하지만 이러한 함수는 실제로 가상이 아니며, 대신 메시지 맵을 통해 구현됩니다. 메시지 맵은 C++ 언어의 확장이 아닌 표준 전처리기 매크로에만 의존합니다. 합니다 **afx_msg** 키워드 전처리 후 공백으로 확인 합니다.

기본 클래스에 정의된 처리기를 재정의하려면 단순히 파생된 클래스의 동일 프로토타입으로 함수를 정의하고 처리기에 대한 메시지-맵 항목을 만듭니다. 처리기는 클래스의 기본 클래스에서 동일한 이름의 모든 처리기를 "재정의"합니다.

이부 경우에는 기본 클래스 및 Windows가 해당 메시지에 대해 작업을 수행할 수 있도록 처리기가 기본 클래스에서 재정의된 처리기를 호출해야 합니다. 재정의에서 기본 클래스 처리기를 호출 하는 위치는 상황에 따라 달라집니다. 경우에 따라 기본 클래스 처리기를 먼저 호출하거나, 마지막으로 호출해야 합니다. 메시지를 직접 처리하지 않도록 선택한 일부 경우에는 기본 클래스 처리기를 조건에 따라 호출합니다. 또한 기본 클래스 처리기를 호출한 후, 기본 클래스 처리기에서 반환된 값 또는 상태에 따라 고유 처리기 코드를 조건에 따라 실행해야 할 수도 있습니다.

> [!CAUTION]
>  인수를 기본 클래스 처리기에 전달하려는 경우에는 처리기에 전달된 인수를 수정하는 것이 안전하지 않습니다. 예를 들어 수정 하려고 시도할 수 있습니다는 *nChar* 인수는 `OnChar` 처리기 (대문자로 변환 예를 들어). 이 동작은 상당히 불분명 하지만이 효과 달성 해야 할 경우 사용 합니다 `CWnd` 멤버 함수 `SendMessage` 대신 합니다.

속성 창의 지정된 된 메시지에 대 한 처리기 함수의 기초를 작성 하는 경우 지정된 된 메시지를 재정의 하는 적절 한 방법은 어떻게 확인 합니까-는 `OnCreate` 에 대 한 처리기 **WM_CREATE**예를 들어-의 형식으로 스케치 권장 되는 재정의 된 멤버 함수입니다. 다음 예제는 처리기를 먼저 기본 클래스 처리기를 호출 하 작업을 계속만 조건-1을 반환 하지 않는 것이 좋습니다.

[!code-cpp[NVC_MFCMessageHandling#3](../mfc/codesnippet/cpp/handlers-for-standard-windows-messages_1.cpp)]

일반적으로 이러한 처리기의 이름은 접두사 "On"으로 시작합니다. 이러한 처리기 중 일부는 인수를 사용하지 않으며, 다른 일부는 인수를 사용합니다. 일부도 반환 형식이 아닌 다른 **void**합니다. 모든 기본 처리기 **WM_** 메시지에 설명 된 합니다 *MFC 참조* 클래스의 멤버 함수로 `CWnd` 이름이 "On."로 시작 멤버 함수 선언에 `CWnd` 붙습니다 **afx_msg**합니다.

## <a name="see-also"></a>참고자료

[메시지 처리기 함수 선언](../mfc/declaring-message-handler-functions.md)
