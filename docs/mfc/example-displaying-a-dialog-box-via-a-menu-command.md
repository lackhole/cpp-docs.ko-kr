---
title: '예제: 메뉴 명령을 통해 대화 상자를 표시합니다.'
ms.date: 11/04/2016
helpviewer_keywords:
- MFC dialog boxes [MFC], examples
- MFC dialog boxes [MFC], displaying
- modeless dialog boxes [MFC], displaying
- dialog boxes [MFC], MFC
- modal dialog boxes [MFC], displaying
- examples [MFC], dialog boxes
- menu items [MFC], examples
ms.assetid: e8692549-acd7-478f-9c5e-ba310ce8cccd
ms.openlocfilehash: 1e730125e47609f0bf87814b32962336cb752b04
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62173309"
---
# <a name="example-displaying-a-dialog-box-via-a-menu-command"></a>예제: 메뉴 명령을 통해 대화 상자를 표시합니다.

이 항목에서는 프로시저를 포함 합니다.

- 메뉴 명령을 통해 모달 대화 상자를 표시 합니다.

- 메뉴 명령을 통해 모덜리스 대화 상자를 표시 합니다.

두 샘플 프로시저는 MFC 응용 프로그램 및 사용 하 여 만든 응용 프로그램에서 작동 합니다 [MFC 응용 프로그램 마법사](../mfc/reference/mfc-application-wizard.md)합니다.

절차는 다음 이름 및 값을 사용합니다.

|항목|이름 또는 값|
|----------|-------------------|
|애플리케이션|DisplayDialog|
|메뉴 명령|보기 메뉴에서 명령을 테스트 합니다. 명령 ID ID_VIEW_TEST =|
|대화 상자|테스트 대화 상자 클래스 CTestDialog; = 헤더 파일 TestDialog.h; = 변수 testdlg, ptestdlg =|
|명령 처리기|OnViewTest|

### <a name="to-display-a-modal-dialog-box"></a>모달 대화 상자를 표시 하려면

1. 메뉴 명령 만들기 참조 [만들기 메뉴 또는 메뉴 항목](../windows/creating-a-menu.md)합니다.

1. 만들기 대화 상자. 참조 [대화 상자 편집기를 시작](../windows/creating-a-new-dialog-box.md)합니다.

1. 대화 상자에 대 한 클래스를 추가 합니다. 참조 [클래스 추가](../ide/adding-a-class-visual-cpp.md) 자세한 내용은 합니다.

1. **클래스 뷰**, 문서 클래스 (CDisplayDialogDoc)를 선택 합니다. **속성** 창에서 **이벤트** 단추를 클릭합니다. 왼쪽된 창에서 메뉴 명령 (ID_VIEW_TEST)의 ID를 두 번 클릭 합니다 **속성** 창과 선택 **명령**입니다. 오른쪽 창에서 아래쪽 화살표를 클릭 하 고 선택  **\<추가 > OnViewTest**합니다.

   MDI 응용 프로그램의 메인프레임을 메뉴 명령에 추가 하는 경우 응용 프로그램 클래스 (CDisplayDialogApp)을 대신 선택 합니다.

1. 다음 include 문을 CDisplayDialogDoc.cpp (또는 CDisplayDialogApp.cpp) 추가 include 문을 기존 후:

   ```cpp
   #include "TestDialog.h"
   ```

1. 다음 코드를 추가 `OnViewTest` 함수를 구현 합니다.

   ```cpp
   CTestDialog testdlg;
   testdlg.DoModal();  
   ```

### <a name="to-display-a-modeless-dialog-box"></a>모덜리스 대화 상자를 표시 하려면

1. 4 단계에서 뷰 클래스 (CDisplayDialogView)를 선택 하 고 제외 하 고 모달 대화 상자를 표시 하는 처음 4 개 단계를 수행 합니다.

1. DisplayDialogView.h를 편집 합니다.

   - 대화 상자 클래스 선언 앞에 첫 번째 클래스를 선언 합니다.

   ```cpp
   class CTestDialog;
   ```

   - 특성의 public 섹션 후 대화 상자에 대 한 포인터를 선언 합니다.

   ```cpp
   CTestDialog* m_pTestDlg;
   ```

1. DisplayDialogView.cpp를 편집 합니다.

   - 다음 문을 포함 후 기존 include 문을 추가 합니다.

   ```cpp
   #include "TestDialog.h"
   ```

   - 생성자에 다음 코드를 추가 합니다.

   ```cpp
   m_pTestDlg = NULL;
   ```

   - 소멸자에 다음 코드를 추가 합니다.

   ```cpp
   delete m_pTestDlg;
   ```

   - 다음 코드를 추가 `OnViewTest` 함수를 구현 합니다.

   ```cpp
   if (NULL == m_pTestDlg)
   {
      m_pTestDlg = new CTestDialog(this);
      m_pTestDlg->Create(CTestDialog::IDD, this);
   }
   m_pTestDlg->ShowWindow(SW_SHOW); 
   ```

## <a name="see-also"></a>참고자료

[대화 상자](../mfc/dialog-boxes.md)<br/>
[모달 및 모덜리스 대화 상자](../mfc/modal-and-modeless-dialog-boxes.md)
