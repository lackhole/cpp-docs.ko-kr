---
title: MFC 애플리케이션 만들기
ms.date: 11/04/2016
helpviewer_keywords:
- applications [MFC]
- MFC, creating applications
- MFC applications
ms.assetid: b8b8aa08-9c49-404c-8078-b42079ac18f0
ms.openlocfilehash: 0f16fe577f1dc02dc9a2fc0cffb5899b16ad8cca
ms.sourcegitcommit: fc1de63a39f7fcbfe2234e3f372b5e1c6a286087
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65708241"
---
# <a name="creating-an-mfc-application"></a>MFC 애플리케이션 만들기

MFC 응용 프로그램은 MFC(Microsoft Foundation Class) 라이브러리를 기반으로 하는 실행 가능한 Windows용 응용 프로그램입니다. MFC 응용 프로그램을 만드는 가장 쉬운 방법은 MFC 응용 프로그램 마법사를 사용하는 것입니다.

> [!IMPORTANT]
>  Visual Studio Express 버전에서는 MFC 프로젝트가 지원되지 않습니다.

다섯 가지 유형으로 대개 MFC 실행 파일: 표준 Windows 응용 프로그램, 대화 상자, 폼 기반 응용 프로그램, Explorer 스타일 응용 프로그램 및 웹 브라우저 스타일 응용 프로그램입니다. 자세한 내용은 다음을 참조하세요.

- [클래스를 사용 하 여 Windows 응용 프로그램 작성](../../mfc/using-the-classes-to-write-applications-for-windows.md)

- [대화 상자 만들기 및 표시](../../mfc/creating-and-displaying-dialog-boxes.md)

- [폼 기반 MFC 응용 프로그램 만들기](../../mfc/reference/creating-a-forms-based-mfc-application.md)

- [파일 탐색기 스타일 MFC 응용 프로그램 만들기](../../mfc/reference/creating-a-file-explorer-style-mfc-application.md)

- [웹 브라우저 스타일 MFC 응용 프로그램 만들기](../../mfc/reference/creating-a-web-browser-style-mfc-application.md)

MFC 응용 프로그램 마법사에서는 선택하는 옵션에 따라 위의 다섯 가지 응용 프로그램 형식 모두에 적합한 클래스와 파일을 생성합니다.

### <a name="to-create-an-mfc-application-using-the-mfc-application-wizard"></a>MFC 응용 프로그램 마법사를 사용하여 MFC 응용 프로그램을 만들려면

1. 도움말 항목의 지침을 따릅니다 [만들기를 C++ 콘솔 앱 프로젝트](../../get-started/tutorial-console-cpp.md)합니다.

1. 에 **새 프로젝트** 대화 상자에서 **MFC 응용 프로그램** 마법사를 열려면 템플릿 창에서.

1. 사용 하 여 응용 프로그램 설정을 정의 합니다 [MFC 응용 프로그램 마법사](../../mfc/reference/mfc-application-wizard.md)합니다.

    > [!NOTE]
    >  마법사의 기본 설정을 그대로 유지하려면 이 단계를 건너 뜁니다.

1. 클릭 **완료** 마법사를 닫고 개발 환경에서 새 프로젝트를 엽니다.

프로젝트가 만들어진 후에 만들어진 파일을 볼 수 있습니다 **솔루션 탐색기**합니다. 마법사에서 프로젝트용으로 만드는 파일에 대한 자세한 내용은 프로젝트 생성 파일인 ReadMe.txt를 참조하세요. 파일 형식에 대 한 자세한 내용은 참조 하세요. [Visual Studio 용으로 만들어지는 파일 형식 C++ 프로젝트](../../build/reference/file-types-created-for-visual-cpp-projects.md)합니다.

## <a name="see-also"></a>참고자료

[코드 마법사로 기능 추가](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[속성 페이지(Visual C++)](../../build/reference/property-pages-visual-cpp.md)

