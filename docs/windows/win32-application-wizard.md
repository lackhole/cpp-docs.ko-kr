---
title: Win32 응용 프로그램 마법사
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.win32.overview
helpviewer_keywords:
- Win32 Application Wizard
- Win32 Project Wizard
ms.assetid: 5d7b3a5e-8461-479a-969a-67b7883725b9
ms.openlocfilehash: 639834c8d723b65b894e6d216cbeb3b7f4dc37ec
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57822693"
---
# <a name="win32-application-wizard"></a>Win32 응용 프로그램 마법사

Visual C++ Win32 애플리케이션 마법사에서는 아래 표의 머리글에 나열된 네 가지 형식의 프로젝트를 만들 수 있습니다. 각각의 경우 연 프로젝트 형식에 적합한 추가 옵션을 지정할 수 있습니다. 다음 표에서는 각 애플리케이션 유형에 사용할 수 있는 옵션을 나타냅니다.

|지원 유형|콘솔 애플리케이션|실행 파일(Windows) 애플리케이션|동적 연결 라이브러리|정적 라이브러리|
|---------------------|-------------------------|----------------------------------------|---------------------------|--------------------|
|**빈 프로젝트**|예|예|예|아니요|
|**내보내기 기호**|아니요|아니요|예|아니요|
|**미리 컴파일된 헤더**|아니요|아니요|아니요|예|
|**ATL 지원**|예|아니요|아니요|아니요|
|**MFC 지원**|예|아니요|아니요|예|

## <a name="overview"></a>개요

이 마법사 페이지에서는 만들려는 Win32 애플리케이션에 대한 현재 프로젝트 설정을 설명합니다. 기본적으로 설정된 옵션은 다음과 같습니다.

- 프로젝트는 Windows 애플리케이션입니다.

- 프로젝트가 비어 있지 않습니다.

- 프로젝트에 내보내기 기호가 없습니다.

- 프로젝트에서 미리 컴파일된 헤더 파일을 사용하지 않습니다. 이 옵션은 정적 라이브러리 프로젝트에만 사용할 수 있습니다.

- 프로젝트에 MFC 또는 ATL에 대한 지원이 없습니다.

이러한 기본값을 변경하려면 마법사의 왼쪽 열에서 [애플리케이션 설정](../windows/application-settings-win-32-project-wizard.md) 탭을 클릭하고 원하는 대로 변경합니다.

Windows 데스크톱 애플리케이션을 만들었으면 [제네릭](../ide/generic-cpp-class-wizard.md) 코드 마법사를 사용하여 제네릭 C++ 클래스를 추가할 수 있습니다. HTML 파일, 헤더 파일, 리소스 또는 텍스트 파일 등의 다른 항목을 추가할 수 있습니다.

> [!NOTE]
> ATL 클래스는 추가할 수 없으며 MFC 클래스는 MFC를 지원하는 Windows 데스크톱 애플리케이션 형식(이전 표 참조)에만 추가할 수 있습니다.

마법사에서 프로젝트용으로 만든 파일은 **솔루션 탐색기**에서 볼 수 있습니다. 마법사에서 프로젝트용 파일에 대 한 자세한 내용은 프로젝트에서 생성 한 파일을 참조 하세요. `ReadMe.txt`합니다. 파일 형식에 대한 자세한 내용은 [Visual C++ 프로젝트용으로 만들어지는 파일 형식](../build/reference/file-types-created-for-visual-cpp-projects.md)을 참조하세요.

## <a name="see-also"></a>참고 항목

[빈 Windows 데스크톱 응용 프로그램 만들기](../windows/creating-an-empty-windows-desktop-application.md)<br/>
[Visual C++ 프로젝트 형식](../build/reference/visual-cpp-project-types.md)