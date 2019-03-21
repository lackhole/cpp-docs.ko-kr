---
title: Win32 프로젝트 마법사, 애플리케이션 설정
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.win32.appset
helpviewer_keywords:
- application settings [C++]
- Win32 Project Wizard, application settings
ms.assetid: d6b818f0-9b23-4793-a6c5-df1c8c594bad
ms.openlocfilehash: 160c0a11408705f261feee41bcae0a72a1760a7d
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57821965"
---
# <a name="application-settings-win-32-project-wizard"></a>Win32 프로젝트 마법사, 애플리케이션 설정

마법사의 이 페이지를 사용하여 Win32 프로젝트에 대한 옵션을 설정 합니다.  

## <a name="application-type"></a>애플리케이션 유형

지정된 응용 프로그램 유형을 만듭니다.  

|옵션|설명|  
|------------|-----------------|  
|**콘솔 응용 프로그램**|콘솔 응용 프로그램을 만듭니다. 콘솔 프로그램은 콘솔 창에서 문자 모드 지원을 제공하는 [콘솔 함수](https://msdn.microsoft.com/en-us/library/ms813137.aspx)로 개발됩니다. Visual C++ [런타임 라이브러리](../c-runtime-library/c-run-time-library-reference.md)는 또한 **printf_s()** 및 **scanf_s()**와 같은 표준 I/O 함수를 사용하여 콘솔 창에서 출력 및 입력을 제공합니다. 콘솔 응용 프로그램에 그래픽 사용자 인터페이스가 없습니다. .exe로 컴파일되고 명령줄에서 독립 실행형 응용 프로그램으로 실행할 수 있습니다.<br /><br /> Windows 응용 프로그램에 MFC 또는 ATL 지원을 추가 할 수 없습니다.|  
|**Windows 응용 프로그램**|Win32 프로그램을 만듭니다. Win32 프로그램은 실행 가능한 응용 프로그램(EXE)으로 C 또는 C++로 작성되고, Win32 API를 호출하여 그래픽 사용자 인터페이스를 만들 수 있습니다.<br /><br /> MFC를 추가할 수 없습니다. 또는 Windows 응용 프로그램에 ATL을 지원합니다.|  
|**DLL**|Win32 동적 연결 라이브러리 (DLL)를 만듭니다. Win32 DLL은 C 또는 C++로 작성된 바이너리 파일로, MFC 클래스 대신 Win32 API를 호출하며 동시에 여러 응용 프로그램에서 사용할 수 있는 함수의 공유 라이브러리 역할을 합니다.<br /><br /> DLL 응용 프로그램에 MFC 또는 ATL 지원을 추가 할 수 없습니다. DLL에서 기호를 내보내도록 할 수 있습니다.|  
|**정적 라이브러리**|정적 라이브러리를 만듭니다. 정적 라이브러리는 개체와 개체 함수 그리고 실행 파일을 빌드할 때 프로그램에 연결되는 데이터를 포함하는 파일입니다. 이 항목에서는 시작 파일을 만드는 방법과 정적 라이브러리에 대한 [프로젝트 속성](../build/reference/property-pages-visual-cpp.md)에 대해 설명합니다.  정적 라이브러리 파일은 다음과 같은 이점을 제공합니다.<br /><br />-Win32 정적 라이브러리는 작업 중인 응용 프로그램에서 MFC 클래스 대신 Win32 API를 호출하는 경우에 유용합니다.<br />-Windows 응용 프로그램의 나머지 부분이 C 또는 C++로 작성되었는지 여부와 관계없이 연결된 프로세스는 동일합니다.<br />-비 MFC 프로그램과 MFC 기반 프로그램 모두 정적 라이브러리를 연결할 수 있습니다.|

## <a name="additional-options"></a>추가 옵션

지원 및 해당 형식에 따라 응용 프로그램에 대 한 옵션을 정의합니다.  

|옵션|설명|  
|------------|-----------------|  
|**빈 프로젝트**|프로젝트 파일이 비어 있는지를 확인합니다. 소스 코드 파일(예:.cpp 파일, 헤더 파일, 아이콘, 도구 모음, 대화 상자 등)의 집합이 있고 Visual C++ 개발 환경에서 프로젝트를 만들 경우 먼저 빈 프로젝트를 만든 다음 파일을 프로젝트에 추가해야 합니다.<br /><br /> 이 옵션은 정적 라이브러리 프로젝트를 선택할 수 없는 경우 사용합니다.|  
|**내보내기 기호**|DLL 프로젝트에서 기호를 내보내도록 지정 합니다.|  
|**미리 컴파일된 헤더**|정적 라이브러리 프로젝트에서는 미리 컴파일된 헤더를 사용하도록 지정합니다.|  
|보안 SDL(Security Development Lifecycle) 검사|SDL에 대한 자세한 내용은 [Microsoft 보안 SDL(Security Development Lifecycle) 프로세스 지침](../build/reference/sdl-enable-additional-security-checks.md)을 참조하세요.| 

## <a name="add-support-for"></a>에 대 한 지원 추가

Visual C++에서 제공 되는 라이브러리에 대한 지원을 추가 합니다.  

|옵션|설명|  
|------------|-----------------|  
|**ATL**|액티브 템플릿 라이브러리 (ATL)의 클래스를 추가 지원하여 프로젝트를 빌드합니다. Win32 콘솔 응용 프로그램에만 해당 됩니다.<br /><br /> **참고** 이 옵션은 ATL 코드 마법사를 이용하여 ATL 개체를 추가할 수 있도록 지원하지 않습니다. ATL 프로젝트나 MFC 프로젝트에서만 ATL 개체를 추가할 수 있습니다.|  
|**MFC**|MFC 라이브러리에 대한 지원을 프로젝트에 빌드합니다. Win32 콘솔 응용 프로그램 및 정적 라이브러리만 해당됩니다.|  

## <a name="see-also"></a>참고 항목

[Win32 응용 프로그램 마법사](../windows/win32-application-wizard.md)
