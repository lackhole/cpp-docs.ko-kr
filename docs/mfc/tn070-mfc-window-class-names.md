---
title: 'TN070: MFC 창 클래스 이름'
ms.date: 11/04/2016
helpviewer_keywords:
- window class names [MFC]
- TN070 [MFC]
ms.assetid: 90617912-dd58-4a7c-9082-ced71736d7cd
ms.openlocfilehash: e2818104c59a94b0e1239abc614a83dea8c3de08
ms.sourcegitcommit: 934cb53fa4cb59fea611bfeb9db110d8d6f7d165
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2019
ms.locfileid: "65611205"
---
# <a name="tn070-mfc-window-class-names"></a>TN070: MFC 창 클래스 이름

> [!NOTE]
>  다음 기술 노트는 온라인 설명서에 먼저 포함되어 있었으므로 업데이트되지 않았습니다. 따라서 일부 절차 및 항목은 만료되거나 올바르지 않을 수 있습니다. 최신 정보를 보려면 온라인 설명서 색인에서 관심 있는 항목을 검색하는 것이 좋습니다.

MFC windows 창의 기능을 반영 하는 동적으로 생성된 된 클래스 이름을 사용 합니다. MFC는 프레임 창, 뷰 및 응용 프로그램에서 생성 하는 팝업 창에 동적으로 클래스 이름을 생성 합니다. 대화 상자 및 MFC 응용 프로그램에서 생성 된 컨트롤 창의 해당 클래스에 대 한 Windows에서 제공한 이름을 갖습니다.

고유한 창 클래스를 등록 하 고 재정의 사용 하 여 동적으로 제공 된 클래스 이름을 바꿀 수 있습니다 [PreCreateWindow](../mfc/reference/cwnd-class.md#precreatewindow)합니다. MFC에서 제공한 클래스 이름에 맞게 다음과 같은 두 가지 중 하나:

```
Afx:%x:%x
Afx:%x:%x:%x:%x:%x
```

대체 하는 16 진수는 `%x` 문자 데이터에서 입력 되는 [WNDCLASS](/windows/desktop/api/winuser/ns-winuser-tagwndclassa) 구조입니다. MFC는이 기법을 사용 하므로 여러 C++ 클래스와 동일한 요구 **WNDCLASS** 구조에 동일한 등록 된 창 클래스를 공유할 수 있습니다. 대부분의 간단한 Win32 응용 프로그램과 달리 MFC 응용 프로그램 하나만 **WNDPROC**이므로 쉽게 공유할 수 있습니다 **WNDCLASS** 시간과 메모리를 저장 하는 구조입니다. 대체 가능한 값은 `%x` 위에 표시 된 문자는 다음과 같습니다.

- **WNDCLASS.hInstance**

- **WNDCLASS.style**

- **WNDCLASS.hCursor**

- **WNDCLASS.hbrBackground**

- **WNDCLASS.hIcon**

첫 번째 형태 (`Afx:%x:%x`) 될 때 사용 됩니다 **hCursor**를 **hbrBackground**, 및 **hIcon** 는 모두 **NULL**합니다.

## <a name="see-also"></a>참고자료

[번호별 기술 참고 사항](../mfc/technical-notes-by-number.md)<br/>
[범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)<br/>
[TN020: ID 명명 및 번호 매기기 규칙](../mfc/tn020-id-naming-and-numbering-conventions.md)
