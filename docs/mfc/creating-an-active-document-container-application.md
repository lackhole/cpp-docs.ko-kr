---
title: 액티브 문서 컨테이너 애플리케이션 만들기
ms.date: 11/04/2016
helpviewer_keywords:
- active documents [MFC], containers
- containers [MFC], active document
- active document containers [MFC], creating
- MFC COM, active document containment
- applications [MFC], active document container
ms.assetid: 14e2d022-a6c5-4249-8712-706b0f4433f7
ms.openlocfilehash: 965778fd5d17aa416b198c101edc3a445a39580b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62152945"
---
# <a name="creating-an-active-document-container-application"></a>액티브 문서 컨테이너 애플리케이션 만들기

액티브 문서 컨테이너 애플리케이션을 만드는 가장 간단하고 가장 권장되는 방법은 MFC 애플리케이션 마법사를 사용해서 MFC EXE 컨테이너 애플리케이션을 만들고 액티브 문서 포함을 지원하도록 애플리케이션을 수정하는 방법입니다.

#### <a name="to-create-an-active-document-container-application"></a>액티브 문서 컨테이너 애플리케이션을 만들려면

1. **파일** 메뉴에서 클릭 **프로젝트**에서 **새** 하위 메뉴.

1. 왼쪽된 창에서 클릭 **시각적 C++**  형식 프로젝션 합니다.

1. 선택 **MFC 응용 프로그램** 오른쪽 창에서.

1. 프로젝트 이름을 *MyProj*, 클릭 **확인**합니다.

1. 선택 된 **복합 문서 지원** 페이지입니다.

1. 선택 된 **컨테이너** 하거나 **컨테이너/풀 서버** 옵션입니다.

1. 선택 된 **액티브 문서 컨테이너** 확인란 합니다.

1. **마침**을 클릭합니다.

1. MFC 애플리케이션 마법사에서 애플리케이션 생성이 완료되면 솔루션 탐색기를 사용해서 다음 파일을 엽니다.

   - *MyProjview.cpp*

1. *MyProjview.cpp*를 다음과 같이 변경 합니다.

   - `CMyProjView::OnPreparePrinting`에서 함수 내용을 다음 코드로 바꿉니다.

     [!code-cpp[NVC_MFCDocView#56](../mfc/codesnippet/cpp/creating-an-active-document-container-application_1.cpp)]

   `OnPreparePrinting`은 인쇄 지원을 제공합니다. 이 코드는 기본 인쇄 준비인 `DoPreparePrinting` 대신 사용됩니다.

   액티브 문서 포함은 향상된 인쇄 체계를 제공합니다.

   - 현재 문서를 먼저 호출 해당 `IPrint` 인터페이스 및 자체를 인쇄 하도록 지시 합니다. 이 컨테이너를 프린터에 포함된 된 항목의 이미지를 렌더링 해야 하는 이전의 OLE 포함 다릅니다 `CDC` 개체입니다.

   - 실패할 경우 포함 된 항목이 통해 자동으로 인쇄 하도록 해당 `IOleCommandTarget` 인터페이스

   - 실패하면 항목을 직접 렌더링합니다.

   정적 멤버 함수 `COleDocObjectItem::OnPrint` 및 `COleDocObjectItem::OnPreparePrinting`은 이전 코드에 구현된 대로 향상된 이 인쇄 체계를 처리합니다.

1. 사용자의 고유 구현을 추가하고 애플리케이션을 빌드합니다.

## <a name="see-also"></a>참고자료

[활성 문서 포함](../mfc/active-document-containment.md)
