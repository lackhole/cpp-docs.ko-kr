---
title: C++ 창 개체와 HWND 간 관계
ms.date: 11/19/2018
f1_keywords:
- HWND
helpviewer_keywords:
- Windows window [MFC]
- window objects [MFC], HWND and
- HWND [MFC]
- CWnd class [MFC], HWND
- HWND, window objects [MFC]
ms.assetid: f2e76340-6691-4ee6-9424-0345634a9469
ms.openlocfilehash: 8cf8856be7166768c507932184e257cf69b0eb35
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62309335"
---
# <a name="relationship-between-a-c-window-object-and-an-hwnd"></a>C++ 창 개체와 HWND 간 관계

창을 *개체* 는 개체입니다는 C++ `CWnd` 클래스 (또는 파생된 클래스) 프로그램에서 직접 만든 합니다. 제공 하 고 프로그램의 생성자 및 소멸자 호출에 대 한 응답으로 이동 합니다. Windows *창*, 다른 한편으로 창에 해당 하 고 있는 경우 시스템 리소스를 소모 되는 내부 Windows 데이터 구조에 대해 불투명 핸들 됩니다. Windows 창 "창 핸들"으로 식별 됩니다 (`HWND`) 후 생성 되 고는 `CWnd` 개체를 호출 하 여 만들어집니다 합니다 `Create` 클래스의 멤버 함수 `CWnd`합니다. 프로그램 호출 하거나 사용자의 동작에 의해 창이 소멸 됩니다. 창 핸들 창 개체에 저장 됩니다 *m_hWnd* 멤버 변수입니다. 다음 그림은 간의 관계는 C++ Windows 창과 창 개체입니다. 창을 만드는 부분은 [만드는 Windows](../mfc/creating-windows.md)합니다. 에 설명 되어 제거 창 [창 개체 제거](../mfc/destroying-window-objects.md)합니다.

![CWnd 창 개체 및 결과 창](../mfc/media/vc37fj1.gif "CWnd 창 개체 및 결과 창") <br/>
창 개체 및 Windows 창

## <a name="see-also"></a>참고자료

[창 개체](../mfc/window-objects.md)
