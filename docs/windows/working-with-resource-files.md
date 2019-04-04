---
title: Working with Resource Files (c + +)
ms.date: 02/14/2019
helpviewer_keywords:
- resources [C++], about resources
- resources [C++], about resource files
- resource files [C++], about resource files
ms.assetid: 2699a539-b369-4b78-80f0-df03eb7b6780
ms.openlocfilehash: 0a13fb05f0e6e8582d5e476eb889e307458f528d
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58767303"
---
# <a name="working-with-resource-files"></a>리소스 파일 작업

> [!WARNING]
> 이 섹션의 내용은 C++로 작성된 Windows 데스크톱 애플리케이션에 적용됩니다.
>
> C + +로 작성 된 유니버설 Windows 플랫폼 앱의 리소스에 대 한 자세한 내용은 [앱 리소스 정의](/windows/uwp/app-resources/), 또는 리소스를 추가 하려면 C + + (관리) CLI 프로젝트를 참조 하십시오 [데스크톱 앱의 리소스](/dotnet/framework/resources/index) 에서 .NET Framework 개발자 가이드입니다.

리소스와 같은 다양 한 범위의 요소를 구성할 수 있습니다.

- 비트맵, 아이콘 또는 커서와 같은 사용자에 게 정보를 제공 하는 인터페이스 요소입니다.
- 데이터 및 응용 프로그램을 포함 하는 사용자 지정 리소스 필요 합니다.
- 설치 Api에서 사용 되는 버전 리소스입니다.
- 메뉴 및 대화 상자 리소스입니다.

프로젝트에 새 리소스를 추가하고 적절한 리소스 편집기를 사용하여 리소스를 수정할 수 있습니다. 대부분의 Visual C++ 마법사에서는 프로젝트에 대해 .rc 파일을 자동으로 생성합니다.

> [!NOTE]
> 합니다 **리소스 편집기** 하 고 **리소스 뷰** Express 버전에서는 사용할 수 없습니다.

관리 되는 프로젝트에 리소스 파일을 수동으로 추가, 참조 [데스크톱 앱에 대 한 리소스 파일 만들기](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)합니다. 이 문서에서는 리소스에 액세스, 정적 리소스 표시, 속성에 리소스 문자열을 할당 하는 방법을 포함 합니다.

전역화 및 지역화 관리 되는 앱의 리소스를 참조 하세요 [Globalizing and Localizing.NET Framework Applications](/dotnet/standard/globalization-localization/index)합니다.

## <a name="in-this-section"></a>섹션 내용

[리소스 파일](../windows/resource-files-visual-studio.md)<br/>
리소스 파일 및 Windows 데스크톱 응용 프로그램에서 사용 하는 방법에 대해 설명 합니다. 또한 리소스 파일을 사용 하는 방법을 설명 하는 문서에 대 한 링크를 제공 합니다.

[리소스 식별자(기호)](../windows/symbols-resource-identifiers.md)<br/>
심볼을 설명하고, **리소스 심볼** 대화 상자를 사용하여 프로젝트의 심볼을 관리하는 방법에 대한 정보를 제공합니다.

[리소스 편집기](../windows/resource-editors.md)<br/>
각 편집기를 사용 하 여 수정할 수 있습니다 하는 리소스 유형 및 Visual Studio에서 제공 하는 리소스 편집기를 설명 합니다. 또한 각 편집기를 사용 하 여 자세한 정보 링크를 제공 합니다.

## <a name="related-sections"></a>관련 단원

[Visual C++](../overview/visual-cpp-in-visual-studio.md)<br/>
Visual C++ 설명서에 대한 링크를 제공합니다.

[의견 보내기](/visualstudio/ide/talk-to-us)<br/>
설명서 집합을 사용하고 기술 지원에 문의하고 액세스 가능성 기능을 적용하는 방법에 대한 정보를 확인할 수 있는 링크를 제공합니다.

## <a name="see-also"></a>참고 항목

[Windows 데스크톱 응용 프로그램](../windows/windows-desktop-applications-cpp.md)<br/>
[메뉴 및 기타 리소스](https://msdn.microsoft.com/library/windows/desktop/ms632583.aspx)