---
title: Windows FORMS-MFC 프로그래밍의 차이점
ms.date: 11/04/2016
helpviewer_keywords:
- MFC [C++], Windows Forms support
- Windows Forms [C++], compared to MFC
ms.assetid: f3bfcf45-cfd4-45a4-8cde-5f4dbb18ee51
ms.openlocfilehash: 998485a3384512f57cf35fc264e2321fa0996728
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57742524"
---
# <a name="windows-formsmfc-programming-differences"></a>Windows Forms/MFC 프로그래밍의 차이점

항목에서는 [MFC에서 Windows Form 사용자 정의 컨트롤을 사용 하 여](../dotnet/using-a-windows-form-user-control-in-mfc.md) Windows Forms에 대 한 MFC 지원을 설명 합니다. .NET Framework 또는 MFC 프로그래밍에 익숙한 경우이 항목에서는 두 간의 프로그래밍 차이점에 대 한 배경 정보를 제공 합니다.

Windows Forms는.NET Framework에서 Microsoft Windows 응용 프로그램을 만드는입니다. 이 프레임 워크에는 최신 개체 지향, 확장할 수 있는 다양 한 Windows 기반 응용 프로그램을 개발할 수 있도록 하는 클래스 집합을 제공 합니다. Windows Forms 데이터 표시 및 Windows Forms 컨트롤을 사용 하 여 데이터 편집 기능을 제공 하 고 다양 한 데이터 원본에 액세스할 수 있는 풍부한 클라이언트 응용 프로그램을 만들 수 됩니다.

그러나 MFC에 익숙한 개발자 라면 특정 유형의 Windows Forms에서 아직 명시적으로 지원 되지 않는 응용 프로그램 만들기 수를 사용할 수 있습니다. Windows Forms 응용 프로그램은 MFC 대화 상자 응용 프로그램 동일 합니다. 그러나 제공 하지 않습니다 직접 단일 문서 인터페이스 (SDI) 다중 문서 인터페이스 (MDI)에 대 한 OLE 문서 서버/컨테이너, ActiveX 문서, 문서/뷰 지원 같은 기타 MFC 응용 프로그램 종류를 지원 하도록 인프라 및 여러 최상위 인터페이스 (MTI)입니다. 이러한 응용 프로그램을 만드는 사용자 고유의 논리를 작성할 수 있습니다.

Windows Forms 응용 프로그램에 대 한 자세한 내용은 참조 하세요. [Windows Forms 소개](/dotnet/framework/winforms/windows-forms-overview)합니다.

MFC를 사용 하는 Windows Forms을 보여 주는 샘플 응용 프로그램을 참조 하세요 [MFC 및 Windows Forms 통합](http://www.microsoft.com/downloads/details.aspx?FamilyID=987021bc-e575-4fe3-baa9-15aa50b0f599&displaylang=en)합니다.

다음 MFC 뷰로 또는 문서 및 명령 라우팅 기능 Windows Forms의 상응 없습니다.

- 셸 통합

   MFC에 동적 데이터 교환 (DDE) 명령 및 문서를 마우스 오른쪽 단추로 클릭 하 고 열기와 같은 동사를 선택, 편집 또는 인쇄 하는 경우 셸을 사용 하는 명령줄 인수를 처리 합니다. Windows Forms 없습니다 셸 통합에 및 셸 동사에 응답 하지 않습니다.

- 문서 템플릿

   MFC에서 문서 템플릿 열린 문서 프레임 창 (MDI, SDI 또는 MTI 모드에서)에 포함 된 뷰를 연결 합니다. Windows Forms에 문서 템플릿에 해당 항목이 없습니다.

- 문서

   MFC 문서 파일 형식을 등록 하 고 셸에서 문서를 열 때 문서 종류를 처리 합니다. Windows Forms은 문서 지원 하지 않습니다.

- 문서 상태

   MFC는 문서에 대 한 변경 상태를 유지 관리합니다. 따라서 응용 프로그램을 닫습니다, 응용 프로그램을 포함 하는 마지막 보기를 닫거나 Windows에서 종료, MFC 문서를 저장할 것인지 묻습니다. Windows Forms에 해당 하는 지원 되지 않습니다.

- 명령

   MFC에 명령의 개념이 있습니다. 메뉴 모음, 도구 모음과 상황에 맞는 메뉴 모두 동일한 명령 잘라내기, 복사 등을 호출할 수 있습니다. Windows Forms, 명령에 특정 UI 요소 (예:; 메뉴 항목)에서 완전히 바인딩된 이벤트 따라서 모든 명령 이벤트를 명시적으로 연결 해야 합니다. Windows Forms에서 단일 처리기를 사용 하 여 여러 이벤트를 처리할 수도 있습니다. 자세한 내용은 [Windows Forms에서 단일 이벤트 처리기에 여러 이벤트 연결](/dotnet/framework/winforms/how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms)합니다.

- 명령 라우팅

   MFC 명령 라우팅 활성 뷰 또는 문서 명령 처리할 수 있습니다. 동일한 명령 같으며 다른 보기에 대 한 다양 한 의미 때문에 (예를 들어 복사에서에서 다르게 작동 하는 그래픽 편집기에서 텍스트 편집 보기 보다), 명령이 현재 보기에서 처리 해야 합니다. 에 대 한 각 보기 유형에 대 한 다양 한 처리기를 사용할 수 없습니다 Windows Forms 메뉴와 도구 모음에 내재 된 활성 뷰가 이해 하지 못합니다 있으므로 하 **MenuItem.Click** 추가 내부 코드를 작성 하지 않고 이벤트입니다.

- 명령 업데이트 메커니즘

   MFC에 메커니즘을 업데이트 하는 명령입니다. 따라서 활성 뷰 또는 문서는 UI 요소 (예: 하거나 사용 하 고, 메뉴 항목이 나 도구 단추를 사용 하지 않도록 설정 하 고, 상태를 확인)의 상태를 담당 합니다. Windows Forms에 명령 업데이트 메커니즘의 해당 요소가 있습니다.

## <a name="see-also"></a>참고자료

[MFC에서 Windows Form 사용자 정의 컨트롤 사용](../dotnet/using-a-windows-form-user-control-in-mfc.md)
