---
title: '방법: 기존 MFC 리본을 리본 리소스로 변환'
ms.date: 11/04/2016
helpviewer_keywords:
- ribbon resource, converting from an MFC ribbon
- MFC ribbon, converting to a ribbon resource
ms.assetid: 324b7ff6-58f9-4691-96a9-9836a79d0fb6
ms.openlocfilehash: b4265a7bf3ebe2c4926f21572d802b75bd525990
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62389491"
---
# <a name="how-to-convert-an-existing-mfc-ribbon-to-a-ribbon-resource"></a>방법: 기존 MFC 리본을 리본 리소스로 변환

리본 리소스는 시각화, 수정 및 수동으로 코딩 된 리본 보다 유지 관리 하기 쉽습니다. 이 항목에서는 MFC 프로젝트에 수동으로 코딩 된 리본을 리본 리소스로 변환 하는 방법을 설명 합니다.

예를 들어, MFC 리본 클래스를 사용 하는 코드가 있는 기존 MFC 프로젝트 있어야 [CMFCRibbonBar 클래스](../mfc/reference/cmfcribbonbar-class.md)합니다.

### <a name="to-convert-an-mfc-ribbon-to-a-ribbon-resource"></a>MFC 리본을 리본 리소스로 변환

1. Visual Studio에서 기존 MFC 프로젝트를 엽니다 소스 파일 위치는 `CMFCRibbonBar` 개체 초기화 됩니다. 일반적으로 mainfrm.cpp 파일이 있습니다. 리본 메뉴에 대 한 초기화 코드 뒤에 다음 코드를 추가 합니다.

```
    m_wndRibbonBar.SaveToXMLFile("RibbonOutput.xml");
```

   파일을 저장한 후 닫습니다.

1. 빌드 및 MFC 응용 프로그램을 실행 한 다음 메모장에서 RibbonOutput.txt 열고 해당 내용을 복사 합니다.

1. Visual Studio에서에 **프로젝트** 메뉴에서 클릭 **리소스 추가**합니다. 에 **리소스 추가** 대화 상자에서 **리본** 클릭 하 고 **새**합니다.

   Visual Studio는 리본 리소스를 만들고 디자인 뷰에서 열립니다. 리본 리소스 ID는에 표시 되는 idr_ribbon1입니다 **리소스 뷰**합니다. 리본 메뉴 ribbon1.mfcribbon ms XML 파일에서 정의 됩니다.

1. Visual Studio에서 ribbon1.mfcribbon ms, 열고 해당 내용을 삭제 후 RibbonOutput.txt 앞에서 복사한 내용을 붙여 넣습니다. 저장 하 고 ribbon1.mfcribbon ms를 닫습니다.

1. 다시 CMFCRibbonBar 개체를 초기화 하는 소스 파일을 열고 (일반적으로 mainfrm.cpp) 주석 기존 코드를 리본. 다음 코드를 주석으로 처리 하는 코드 뒤에 추가 합니다.

```
    m_wndRibbonBar.LoadFromResource(IDR_RIBBON1);
```

1. 프로젝트를 빌드하고 프로그램을 실행 합니다.

## <a name="see-also"></a>참고자료

[리본 디자이너(MFC)](../mfc/ribbon-designer-mfc.md)
