---
title: 웹 브라우저 스타일 MFC 애플리케이션 만들기
ms.date: 06/25/2018
f1_keywords:
- vc.appwiz.mfcweb.project
helpviewer_keywords:
- MFC, Web applications
- Web browsers, creating from MFC architecture
- Web browsers
- Web applications [MFC], creating
ms.assetid: 257f8c03-33c3-428c-832e-0b70aff6168d
ms.openlocfilehash: 9d249c7effc2c78e319207d82c9a963d7a61a67c
ms.sourcegitcommit: ecf274bcfe3a977c48745aaa243e5e731f1fdc5f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2019
ms.locfileid: "66504775"
---
# <a name="creating-a-web-browser-style-mfc-application"></a>웹 브라우저 스타일 MFC 애플리케이션 만들기

네트워크 및 로컬 파일 시스템에서 웹 브라우저 스타일 응용 프로그램 폴더 뿐 아니라 (예: HTML 또는 액티브 문서)는 인터넷 또는 인트라넷에서 정보에 액세스할 수 있습니다. 응용 프로그램의 뷰 클래스를 파생 시켜 [CHtmlView](../../mfc/reference/chtmlview-class.md), 효과적으로 WebBrowser 컨트롤을 사용 하 여 뷰를 제공 하 여 응용 프로그램 웹 브라우저를 확인 합니다.

### <a name="to-create-a-web-browser-application-based-on-the-mfc-documentview-architecture"></a>MFC 문서/뷰 아키텍처를 기반으로 웹 브라우저 응용 프로그램을 만들려면

1. 지침을 따르고 [MFC 응용 프로그램을 만드는](../../mfc/reference/creating-an-mfc-application.md)합니다.

1. MFC 응용 프로그램 마법사에서 [응용 프로그램 종류](../../mfc/reference/application-type-mfc-application-wizard.md) 페이지에 있는지 확인 합니다는 **문서/뷰 아키텍처** 확인란을 선택 합니다. (중 하나를 선택할 수 있습니다 **단일 문서로** 또는 **여러 문서**, 있지만 **대화 상자 기반**.)

1. 에 [클래스를 생성 하는 검토](../../mfc/reference/generated-classes-mfc-application-wizard.md) 페이지에서 사용 하 여는 **기본 클래스** 드롭 다운 메뉴를 `CHtmlView`합니다.

1. 다른 옵션을 선택 하려는 기본 응용 프로그램에 기본 제공 합니다.

1. **마침**을 클릭합니다.

WebBrowser 컨트롤 로케이터 URL (Uniform Resource) 탐색 및 하이퍼링크를 통해 웹 검색을 지원 합니다. 컨트롤에는 앞으로 이동할 수 있는 기록 목록을 유지 관리를 통해 이전 버전과 이전에 검색 사이트, 폴더 및 문서 탐색, 하이퍼링크, 기록 목록, 즐겨찾기 및 보안을 직접 처리 하는 컨트롤입니다. 응용 프로그램 호스트 활성 문서도 액티브 문서 컨테이너도 WebBrowser 컨트롤을 사용 수 있습니다. 따라서 Microsoft Excel 스프레드시트와 같은 서식된 문서 또는 Word 문서를 열고 WebBrowser 컨트롤 내에서 현재 위치에서 편집 합니다. WebBrowser 컨트롤을 ActiveX 컨트롤을 호스트할 수 있는 ActiveX 컨트롤 컨테이너 이기도 합니다.

> [!NOTE]
>  WebBrowser ActiveX 컨트롤 (및 따라서 `CHtmlView`) Internet Explorer 4.0에서 Windows 버전에서 실행 하는 응용 프로그램에만 사용할 수 없거나 이상이 설치 된.

때문에 `CHtmlView` 같은 다른 인쇄 되지 Microsoft 웹 브라우저 컨트롤을 지 원하는 간단히 구현 [CView](../../mfc/reference/cview-class.md)-클래스를 파생 합니다. 대신 WebBrowser 컨트롤 인쇄 고 프린터 사용자 인터페이스를 구현합니다. 결과적으로, `CHtmlView` 는 인쇄 미리 보기, 지원 하지 않습니다 하 고 기타 인쇄 지원 기능에 대 한 프레임 워크를 제공 하지 않습니다: 예를 들어 [CView::OnPreparePrinting](../../mfc/reference/cview-class.md#onprepareprinting), [CView::OnBeginPrinting](../../mfc/reference/cview-class.md#onbeginprinting), 및 [CView::OnEndPrinting](../../mfc/reference/cview-class.md#onendprinting), 다른 MFC 응용 프로그램에서 사용할 수 있는 합니다.

`CHtmlView` 응용 프로그램에 웹 페이지나 HTML 페이지 보기를 제공 하는 웹 브라우저 컨트롤에 대 한 래퍼로 작동 합니다. 마법사에서는 재정의 만듭니다.는 [OnInitialUpdate](../../mfc/reference/cview-class.md#oninitialupdate) Microsoft 시각적 개체를 탐색 링크를 제공 하는 뷰 클래스의 함수 C++ 웹 사이트:

```cpp
void CWebView::OnInitialUpdate()
{
    CHtmlView::OnInitialUpdate();

    // TODO: This code navigates to a popular spot on the web.
    // Change the code to go where you'd like.
    Navigate2(_T("http://www.docs.microsoft.com/"),
        NULL,
        NULL);
}
```

사용자 중 하나를 사용 하 여이 사이트를 바꿀 수 있습니다 하거나 사용할 수 있습니다 합니다 [LoadFromResource](../../mfc/reference/chtmlview-class.md#loadfromresource) 멤버 함수를 뷰에 대 한 기본 콘텐츠로 프로젝트의 리소스 스크립트에 있는 HTML 페이지를 엽니다. 예를 들어:

```cpp
void CWebView::OnInitialUpdate()
{
    CHtmlView::OnInitialUpdate();

    // TODO: This code navigates to a popular spot on the web.
    // Change the code to go where you'd like.
    LoadFromResource(IDR_HTML1);
}
```

## <a name="see-also"></a>참고자료

[MFC 샘플 MFCIE](https://github.com/Microsoft/VCSamples)<br/>
[MFC 응용 프로그램 마법사](../../mfc/reference/mfc-application-wizard.md)<br/>
[컴파일러 설정 및 빌드 속성](../../build/working-with-project-properties.md)<br/>
[속성 페이지(Visual C++)](../../build/reference/property-pages-visual-cpp.md)<br/>
[컴파일러 설정 및 빌드 속성](../../build/working-with-project-properties.md)

