---
title: '연습: 자체 동적 연결 라이브러리 만들기 및 사용(C++)'
description: C++를 사용하여 Visual Studio에서 Windows DLL(동적 연결 라이브러리)을 만듭니다.
ms.custom: conceptual
ms.date: 07/17/2019
helpviewer_keywords:
- libraries [C++], DLLs
- DLLs [C++], walkthroughs
ms.assetid: 3ae94848-44e7-4955-bbad-7d40f493e941
ms.openlocfilehash: 8ca89471177ba2d1fa98bfaf51b86ed15dcd6d2f
ms.sourcegitcommit: 7f5b29e24e1be9b5985044a030977485fea0b50c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/17/2019
ms.locfileid: "68299822"
---
# <a name="walkthrough-create-and-use-your-own-dynamic-link-library-c"></a>연습: 자체 동적 연결 라이브러리 만들기 및 사용(C++)

이 단계별 연습에서는 Visual Studio IDE를 사용하여 C++로 작성된 자체 DLL(동적 연결 라이브러리)을 만든 후 다른 C++ 앱에서 사용하는 방법을 보여 줍니다. DLL(UNIX 기반 운영 체제에서는 공유 라이브러리라고도 함)은 Windows 구성 요소의 가장 유용한 종류 중 하나입니다. DLL을 코드 및 리소스를 공유하는 방법으로 사용하여 앱의 크기를 줄이고 앱을 더 쉽게 제공하고 확장할 수 있습니다. 이 연습에서는 몇 가지 수학 함수를 구현하는 DLL을 만든 후 DLL의 함수를 사용하는 콘솔 앱을 만듭니다. 또한 Windows DLL에서 사용되는 몇 가지 프로그래밍 기술 및 규칙을 소개합니다.

이 연습에서는 다음 작업 방법을 배웁니다.

- Visual Studio에서 DLL 프로젝트를 만듭니다.

- 내보낸 함수 및 변수를 DLL에 추가합니다.

- Visual Studio에서 콘솔 앱 프로젝트를 만듭니다.

- 콘솔 앱에서 DLL에서 가져온 함수 및 변수를 사용합니다.

- 완성된 앱을 실행합니다.

정적으로 연결된 라이브러리와 마찬가지로, DLL은 이름으로 변수, 함수 및 리소스를 _내보내고_, 앱은 해당 이름을 _가져와서_ 해당 변수, 함수 및 리소스를 사용합니다. 정적으로 연결된 라이브러리와 달리, Windows는 링크 타임에 앱의 가져오기를 DLL의 내보내기와 연결하는 것이 아니라 로드 시간 또는 런타임에 앱의 가져오기를 DLL의 내보내기에 연결합니다. Windows에서는 이렇게 연결하려면 표준 C++ 컴파일 모델에 속하지 않는 추가 정보가 필요합니다. MSVC 컴파일러는 C++에 대한 몇 가지 Microsoft 전용 확장을 구현하여 이 추가 정보를 제공합니다. 이 연습에서는 내용을 전개해가면서 해당 확장을 설명합니다.

이 연습에서는 두 개의 Visual Studio 솔루션을 만듭니다. 하나는 DLL을 빌드하는 솔루션이고, 다른 하나는 클라이언트 앱을 빌드하는 솔루션입니다. DLL은 플랫폼, 호출 및 연결 규칙이 일치하는 한, 다른 언어를 사용하여 빌드된 앱에서 호출할 수 있도록 C 호출 규칙을 사용합니다. 클라이언트 앱은 Windows가 로드 시간에 앱을 DLL에 연결하는 ‘암시적 연결’을  사용합니다. 이 연결을 통해 앱은 DLL에서 제공한 함수를 정적으로 연결된 라이브러리의 함수처럼 호출할 수 있습니다.

이 연습에서는 일부 일반적인 상황은 다루지 않습니다. 다른 프로그래밍 언어로 C++ DLL 사용을 표시하지 않으며, 리소스 전용 DLL을 만드는 방법도 보여 주지 않습니다. 또한 로드 시간이 아니라 런타임에 DLL을 로드하는 명시적 연결 사용도 보여 주지 않습니다. Visual Studio를 사용 하 여 이러한 모든 작업을 수행할 수 있습니다. DLL에 대한 자세한 내용의 링크는 [Visual Studio에서 C/C++ DLL 만들기](dlls-in-visual-cpp.md)를 참조하세요. 암시적 연결 및 명시적 연결에 대한 자세한 내용은 [사용할 연결 방법 결정](linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)을 참조하세요. C 언어 연결 규칙을 사용하는 프로그래밍 언어로 사용할 C++ DLL을 만드는 방법에 대한 자세한 내용은 [C++ 함수를 C 언어 실행 파일에서 사용할 수 있도록 내보내기](exporting-cpp-functions-for-use-in-c-language-executables.md)를 참조하세요. .NET 언어로 사용할 DLL을 만드는 방법에 대한 자세한 내용은 [Visual Basic 애플리케이션에서 DLL 함수 호출](calling-dll-functions-from-visual-basic-applications.md)을 참조하세요.

## <a name="prerequisites"></a>전제 조건

- Microsoft Windows 7 이상 버전을 실행하는 컴퓨터. 최상의 개발 환경을 위해서는 Windows 10이 권장됩니다.

- Visual Studio. Visual Studio를 다운로드 및 설치하는 방법에 대한 자세한 내용은 [Visual Studio 설치](/visualstudio/install/install-visual-studio)를 참조하세요. 설치 관리자를 실행할 때 **C++를 사용한 데스크톱 개발** 워크로드를 선택해야 합니다. Visual Studio를 설치할 때 이 워크로드를 설치하지 않은 경우 걱정하지 마세요. 설치 관리자를 다시 실행하고 바로 설치할 수 있습니다.

   ![C++를 사용한 데스크톱 개발](media/desktop-development-with-cpp.png "C++를 사용한 데스크톱 개발")

- Visual Studio IDE 사용의 기본 사항에 대한 이해. 이전에 Windows 데스크톱 앱을 사용한 경우 내용을 따라갈 수 있습니다. 소개 내용을 살펴보려면 [Visual Studio IDE 기능 둘러보기](/visualstudio/ide/visual-studio-ide)를 참조하세요.

- 내용을 따라가기에 충분한 C++ 언어의 기본 사항에 대한 이해. 너무 복잡한 내용을 다루지는 않으므로 걱정하지 마세요.

## <a name="create-the-dll-project"></a>DLL 프로젝트 만들기

이 작업 세트에서는 DLL용 프로젝트를 만들고 코드를 추가하고 빌드합니다. 시작하려면 Visual Studio IDE를 시작하고 필요한 경우 로그인합니다. 사용 중인 Visual Studio 버전에 따라 지침이 약간 다릅니다. 이 페이지의 왼쪽 위에 있는 컨트롤에서 올바른 버전을 선택했는지 확인합니다.

::: moniker range="=vs-2019"

### <a name="to-create-a-dll-project-in-visual-studio-2019"></a>Visual Studio 2019에서 DLL 프로젝트를 만들려면

1. 메뉴 모음에서 **파일** > **새로 만들기** > **프로젝트**를 선택하여 **새 프로젝트 만들기** 대화 상자를 엽니다.

   ![새 DLL 프로젝트 만들기](media/create-new-dll-project-2019.png "MathLibrary 프로젝트 만들기")

1. 대화 상자 맨 위에서 **언어**를 **C++** 로 설정하고 **플랫폼**을 **Windows**로 설정하고 **프로젝트 형식**을 **라이브러리**로 설정합니다. 

1. 필터링된 프로젝트 형식 목록에서 **DLL(동적 연결 라이브러리)** 을 선택한 후 **다음**을 선택합니다. 다음 페이지에서 **이름** 상자에 `MathLibrary`를 입력하여 프로젝트 이름을 지정하고 원하는 경우 프로젝트 위치를 지정합니다.

1. **만들기** 단추를 선택하여 프로젝트를 만듭니다.

::: moniker-end

::: moniker range="vs-2017"

### <a name="to-create-a-dll-project-in-visual-studio-2017"></a>Visual Studio 2017에서 DLL 프로젝트를 만들려면

1. 메뉴 모음에서 **파일** > **새로 만들기** > **프로젝트**를 선택하여 **새 프로젝트** 대화 상자를 엽니다.

1. **새 프로젝트** 대화 상자의 왼쪽 창에서 **설치됨** 및 **Visual C++** 를 확장하고 필요한 경우 **Windows 데스크톱**을 선택합니다. 가운데 창에서 **Windows 데스크톱 마법사**를 선택합니다. **이름** 상자에 `MathLibrary`를 입력하여 프로젝트 이름을 지정합니다.

   ![MathLibrary 프로젝트 이름 지정](media/mathlibrary-new-project-name-153.png "MathLibrary 프로젝트 이름 지정")

1. **확인** 단추를 선택하여 **새 프로젝트** 대화 상자를 닫고 **Windows 데스크톱 프로젝트** 마법사를 시작합니다.

1. **Windows 데스크톱 프로젝트** 마법사의 **애플리케이션 유형**에서 **동적 연결 라이브러리(.dll)** 를 선택합니다.

   ![Windows 데스크톱 프로젝트 마법사에서 DLL 만들기](media/mathlibrary-desktop-project-wizard-dll.png "Windows 데스크톱 프로젝트 마법사에서 DLL 만들기")

1. **확인** 단추를 선택하여 프로젝트를 만듭니다.

> [!NOTE]
> Visual Studio 2017 버전 15.3에서 문제를 해결하려면 추가 단계가 필요합니다. 다음 지침에 따라 이 변경 사항을 수행해야 할지 확인하세요.
>
>1. **솔루션 탐색기**의 **솔루션 ‘MathLibrary’** 에서 **MathLibrary** 프로젝트가 아직 선택되어 있지 않으면 선택합니다.
>
>1. 메뉴 모음에서 **프로젝트** > **속성**을 선택합니다.
>
>1. **속성 페이지** 대화 상자의 왼쪽 창의 **구성 속성** > **C/C++** 에서 **전처리기**를 선택합니다. **전처리기 정의** 속성의 콘텐츠를 확인합니다.<br/><br/>![전처리기 정의 속성을 확인하세요](media/mathlibrary-153bug-preprocessor-definitions-check.png "전처리기 정의 속성 확인")<br/><br/>**전처리기 정의** 목록에 **MATHLIBRARY&#95;EXPORTS**가 표시되면 아무 것도 변경하지 않아도 됩니다. **MathLibrary&#95;EXPORTS**가 대신 표시되면 다음 단계를 계속 수행합니다.
>
>1. **속성 페이지** 대화 상자 맨 위에서 **구성** 드롭다운을 **모든 구성**으로 변경합니다.
>
>1. 속성 창에서 **전처리기 정의** 편집 상자 옆에 있는 드롭다운 컨트롤을 선택한 후 **편집**을 선택합니다.<br/><br/>![전처리기 정의 속성 편집](media/mathlibrary-153bug-preprocessor-definitions-property.png "전처리기 정의 속성 편집")
>
>1. **전처리기 정의** 대화 상자의 위쪽 창에서 새 기호 `MATHLIBRARY_EXPORTS`를 추가합니다.<br/><br/>![MATHLIBRARY_EXPORTS 기호 추가](media/mathlibrary-153bug-preprocessor-definitions-dialog.png "MATHLIBRARY_EXPORTS 기호 추가")
>
>1. **확인**을 선택하여 **전처리기 정의** 대화 상자를 닫은 후 **확인**을 선택하여 프로젝트 속성의 변경 사항을 저장합니다.

::: moniker-end

::: moniker range="=vs-2015"

### <a name="to-create-a-dll-project-in-older-versions-of-visual-studio"></a>이전 버전의 Visual Studio에서 DLL 프로젝트를 만들려면

1. 메뉴 모음에서 **파일** > **새로 만들기** > **프로젝트**를 선택합니다.

1. **새 프로젝트** 대화 상자의 왼쪽 창에서 **설치됨** > **템플릿**을 확장하고 **Visual C++** 를 선택한 후 가운데 창에서 **Win32 콘솔 애플리케이션**을 선택합니다. **이름** 편집 상자에 `MathLibrary`를 입력하여 프로젝트 이름을 지정합니다.

   ![MathLibrary 프로젝트 이름 지정](media/mathlibrary-project-name.png "MathLibrary 프로젝트 이름 지정")

1. **확인** 단추를 선택하여 **새 프로젝트** 대화 상자를 닫고 **Win32 애플리케이션 마법사**를 시작합니다.

   ![Win32 애플리케이션 마법사 개요](media/mathlibrary-project-wizard-1.png "Win32 애플리케이션 마법사 개요")

1. **다음** 단추를 선택합니다. **애플리케이션 설정** 페이지의 **애플리케이션 유형**에서 **DLL**을 선택합니다.

   ![Win32 애플리케이션 마법사에서 DLL 만들기](media/mathlibrary-project-wizard-2.png "Win32 애플리케이션 마법사에서 DLL 만들기")

1. **마침** 단추를 선택하여 프로젝트를 만듭니다.

마법사가 솔루션을 완료하면 Visual Studio의 **솔루션 탐색기** 창에서 생성된 프로젝트 및 소스 파일을 볼 수 있습니다.

![Visual Studio에서 생성된 솔루션](media/mathlibrary-solution-explorer-153.png "Visual Studio에서 생성된 솔루션")

지금은 이 DLL이 크게 하는 일이 없습니다. 다음으로, DLL이 내보내는 함수를 선언하는 헤더 파일을 만든 후 DLL에 함수 정의를 추가하여 더 유용하게 만듭니다.

::: moniker-end

### <a name="to-add-a-header-file-to-the-dll"></a>DLL에 헤더 파일을 추가하려면

1. 함수의 헤더 파일을 만들려면 메뉴 모음에서 **프로젝트** > **새 항목 추가**를 선택합니다.

1. **새 항목 추가** 대화 상자의 왼쪽 창에서 **Visual C++** 를 선택합니다. 가운데 창에서 **헤더 파일 (.h)** 을 선택합니다. 헤더 파일의 이름으로 `MathLibrary.h`를 지정합니다.

   ![새 항목 추가 대화 상자에서 헤더 추가](media/mathlibrary-add-new-item-header-file.png "새 항목 추가 대화 상자에서 헤더 파일 추가")

1. **추가** 단추를 선택하여 빈 헤더 파일(새 편집기 창에 표시됨)을 생성합니다.

   ![편집기의 빈 MathLibrary.h 파일](media/edit-empty-mathlibrary-header.png "편집기의 빈 MathLibrary.h 파일")

1. 헤더 파일의 내용을 다음 코드로 바꿉니다.

   ```cpp
   // MathLibrary.h - Contains declarations of math functions
   #pragma once

   #ifdef MATHLIBRARY_EXPORTS
   #define MATHLIBRARY_API __declspec(dllexport)
   #else
   #define MATHLIBRARY_API __declspec(dllimport)
   #endif

   // The Fibonacci recurrence relation describes a sequence F
   // where F(n) is { n = 0, a
   //               { n = 1, b
   //               { n > 1, F(n-2) + F(n-1)
   // for some initial integral values a and b.
   // If the sequence is initialized F(0) = 1, F(1) = 1,
   // then this relation produces the well-known Fibonacci
   // sequence: 1, 1, 2, 3, 5, 8, 13, 21, 34, ...

   // Initialize a Fibonacci relation sequence
   // such that F(0) = a, F(1) = b.
   // This function must be called before any other function.
   extern "C" MATHLIBRARY_API void fibonacci_init(
       const unsigned long long a, const unsigned long long b);

   // Produce the next value in the sequence.
   // Returns true on success and updates current value and index;
   // false on overflow, leaves current value and index unchanged.
   extern "C" MATHLIBRARY_API bool fibonacci_next();

   // Get the current value in the sequence.
   extern "C" MATHLIBRARY_API unsigned long long fibonacci_current();

   // Get the position of the current value in the sequence.
   extern "C" MATHLIBRARY_API unsigned fibonacci_index();
   ```

이 헤더 파일은 두 개의 초기 값이 지정된 일반화된 피보나치 시퀀스를 생성하는 몇 가지 함수를 선언합니다. `fibonacci_init(1, 1)` 호출은 친숙한 피보나치 수열을 생성합니다.

파일 맨 위의 전처리기 문을 확인합니다. 기본적으로 DLL의 새 프로젝트 템플릿은 DLL 프로젝트의 정의된 전처리기 매크로에 **\<em>PROJECTNAME\</em>&#95;EXPORTS**를 추가합니다. 이 예에서 Visual Studio는 MathLibrary DLL 프로젝트가 빌드될 때 **MATHLIBRARY&#95;EXPORTS**를 정의합니다. 

::: moniker range="=vs-2017"

(Visual Studio 2017 버전 15.3의 마법사는 이 기호 정의를 대문자로 강제 변환하지 않습니다. 프로젝트 이름을 “MathLibrary”로 지정하는 경우 정의된 기호는 MATHLIBRARY&#95;EXPORTS가 아니라 MathLibrary&#95;EXPORTS입니다. 따라서 위에 이 기호를 추가하는 추가 단계가 있는 것입니다.)

::: moniker-end

**MATHLIBRARY&#95;EXPORTS** 매크로가 정의되면 **MATHLIBRARY&#95;API** 매크로는 함수 선언에서 `__declspec(dllexport)` 한정자를 설정합니다. 이 한정자는 DLL에서 함수 또는 변수를 내보내도록 컴파일러 및 링커에 알려 다른 애플리케이션에서 사용할 수 있도록 합니다. **MATHLIBRARY&#95;EXPORTS**가 정의되지 않은 경우(예: 헤더 파일이 클라이언트 애플리케이션에 의해 포함되는 경우) **MATHLIBRARY&#95;API**는 선언에 `__declspec(dllimport)` 한정자를 적용합니다. 이 한정자는 애플리케이션에서 함수 또는 변수의 가져오기를 최적화합니다. 자세한 내용은 [dllexport, dllimport](../cpp/dllexport-dllimport.md)를 참조하세요.

### <a name="to-add-an-implementation-to-the-dll"></a>DLL에 구현을 추가하려면

::: moniker range="vs-2019"

1. **솔루션 탐색기**에서 **소스 파일** 노드를 마우스 오른쪽 단추로 클릭하고 이전 단계에서 새 헤더 파일을 추가한 것과 같은 방법으로 `MathLibrary.cpp`라는 새 .cpp 파일을 추가합니다.

::: moniker-end

1. 편집기 창에서 **MathLibrary.cpp**가 이미 열려 있는 경우 해당 탭을 선택합니다. 그렇지 않으면 **솔루션 탐색기**에서 **MathLibrary** 프로젝트의 **소스 파일** 폴더에 있는 **MathLibrary.cpp**를 엽니다.

1. 편집기에서 MathLibrary.cpp 파일의 내용을 다음 코드로 바꿉니다.

   ```cpp
   // MathLibrary.cpp : Defines the exported functions for the DLL.
   #include "stdafx.h" // use pch.h in Visual Studio 2019
   #include <utility>
   #include <limits.h>
   #include "MathLibrary.h"

   // DLL internal state variables:
   static unsigned long long previous_;  // Previous value, if any
   static unsigned long long current_;   // Current sequence value
   static unsigned index_;               // Current seq. position

   // Initialize a Fibonacci relation sequence
   // such that F(0) = a, F(1) = b.
   // This function must be called before any other function.
   void fibonacci_init(
       const unsigned long long a,
       const unsigned long long b)
   {
       index_ = 0;
       current_ = a;
       previous_ = b; // see special case when initialized
   }

   // Produce the next value in the sequence.
   // Returns true on success, false on overflow.
   bool fibonacci_next()
   {
       // check to see if we'd overflow result or position
       if ((ULLONG_MAX - previous_ < current_) ||
           (UINT_MAX == index_))
       {
           return false;
       }

       // Special case when index == 0, just return b value
       if (index_ > 0)
       {
           // otherwise, calculate next sequence value
           previous_ += current_;
       }
       std::swap(current_, previous_);
       ++index_;
       return true;
   }

   // Get the current value in the sequence.
   unsigned long long fibonacci_current()
   {
       return current_;
   }

   // Get the current index position in the sequence.
   unsigned fibonacci_index()
   {
       return index_;
   }
   ```

지금까지 수행한 모든 사항이 작동하는지 확인하려면 동적 연결 라이브러리를 컴파일합니다. 컴파일하려면 메뉴 모음에서 **빌드** > **솔루션 빌드**를 선택합니다. 출력은 다음과 같습니다. DLL 실행 파일 및 관련 컴파일러 출력은 솔루션 폴더 바로 아래에 있는 *Debug* 라는 폴더에 배치 됩니다. 릴리스 빌드를 만드는 경우 출력은 *릴리스*라는 폴더에 배치 됩니다.

```Output
1>------ Build started: Project: MathLibrary, Configuration: Debug Win32 ------
1>MathLibrary.cpp
1>dllmain.cpp
1>Generating Code...
1>   Creating library C:\Users\username\Source\Repos\MathLibrary\Debug\MathLibrary.lib and object C:\Users\username\Source\Repos\MathLibrary\Debug\MathLibrary.exp
1>MathLibrary.vcxproj -> C:\Users\username\Source\Repos\MathLibrary\Debug\MathLibrary.dll
1>MathLibrary.vcxproj -> C:\Users\username\Source\Repos\MathLibrary\Debug\MathLibrary.pdb (Partial PDB)
========== Build: 1 succeeded, 0 failed, 0 up-to-date, 0 skipped ==========
```

축 하 합니다. Visual Studio를 사용 하 여 DLL을 만들었습니다. 다음으로, DLL에서 내보낸 함수를 사용하는 클라이언트 앱을 만듭니다.

## <a name="create-a-client-app-that-uses-the-dll"></a>DLL을 사용하는 클라이언트 앱 만들기

DLL을 만들 때는 DLL을 사용하는 방법에 대해 생각해야 합니다. DLL에서 내보낸 함수를 호출하는 코드를 컴파일하려면 클라이언트 소스 코드에 선언을 포함해야 합니다. 링크 타임에 DLL 함수에 대한 해당 호출이 확인되면 링커는 실제 코드 대신 함수를 찾는 방법에 대한 Windows의 정보를 포함하는 특수 라이브러리 파일인 ‘가져오기 라이브러리’가  있어야 합니다. 또한 런타임에 운영 체제가 찾을 수 있는 위치에서 클라이언트가 DLL을 사용할 수 있어야 합니다.

자체 DLL이든 또는 타사 DLL이든 관계없이 DLL을 사용하려면 클라이언트 앱 프로젝트에서 DLL 내보내기, 링커의 가져오기 라이브러리 및 DLL 자체를 선언하는 헤더를 찾아야 합니다. 한 가지 방법은 해당 파일을 모두 클라이언트 프로젝트에 복사하는 것입니다. 클라이언트가 개발 중일 때 변경될 가능성이 없는 타사 DLL의 경우 이 매서드가 DLL을 사용하는 최상의 방법이 될 수 있습니다. 그러나 DLL을 빌드하기도 할 경우에는 중복을 피하는 것이 좋습니다. 개발 중인 DLL 파일의 복사본을 만드는 경우 실수로 한 복사본의 헤더 파일은 변경하고 다른 복사본의 헤더 파일은 변경하지 않거나 오래된 라이브러리를 사용할 수 있습니다. 이 문제를 방지하려면 클라이언트 프로젝트에 포함 경로를 설정하여 DLL 프로젝트의 DLL 헤더 파일을 포함하는 것이 좋습니다. 또한 클라이언트 프로젝트에 라이브러리 경로를 설정하여 DLL 프로젝트의 DLL 가져오기 라이브러리를 포함합니다. 마지막으로 DLL 프로젝트의 빌드된 DLL을 빌드 출력 디렉터리에 복사합니다. 이 단계에서는 클라이언트 앱이 사용자가 빌드한 것과 같은 DLL 코드를 사용할 수 있습니다.

::: moniker range="vs-2019"

### <a name="to-create-a-client-app-in-visual-studio-2019"></a>Visual Studio 2019에서 클라이언트 앱을 만들려면

1. 메뉴 모음에서 **파일** > **새로 만들기** > **프로젝트**를 선택하여 **새 프로젝트 만들기** 대화 상자를 엽니다.

1. 대화 상자 맨 위에서 **언어**를 **C++** 로 설정하고 **플랫폼**을 **Windows**로 설정하고 **프로젝트 형식**을 **콘솔**로 설정합니다. 

1. 필터링된 프로젝트 형식 목록에서 **콘솔 앱**을 선택한 후 **다음**을 선택합니다. 다음 페이지에서 **이름** 상자에 `MathClient`를 입력하여 프로젝트 이름을 지정하고 원하는 경우 프로젝트 위치를 지정합니다.

   ![클라이언트 프로젝트 이름 지정](media/mathclient-project-name-2019.png "클라이언트 프로젝트 이름 지정")

1. **만들기** 단추를 선택하여 클라이언트 프로젝트를 만듭니다.

::: moniker-end

::: moniker range="vs-2017"

### <a name="to-create-a-client-app-in-visual-studio-2017"></a>Visual Studio 2017에서 클라이언트 앱을 만들려면

1. 만든 DLL을 사용하는 C++ 앱을 만들려면 메뉴 모음에서 **파일** > **새로 만들기** > **프로젝트**를 선택합니다.

1. **새 프로젝트** 대화 상자의 왼쪽 창의 **설치됨** > **Visual C++** 에서 **Windows 데스크톱**을 선택합니다. 가운데 창에서 **Windows 데스크톱 마법사**를 선택합니다. **이름** 편집 상자에 프로젝트 이름 `MathClient`를 지정합니다.

   ![클라이언트 프로젝트 이름 지정](media/mathclient-new-project-name-153.png "클라이언트 프로젝트 이름 지정")

1. **확인**을 선택하여 **Windows 데스크톱 프로젝트** 마법사를 시작합니다. 마법사에서 **확인**을 선택하여 클라이언트 앱 프로젝트를 만듭니다.

::: moniker-end

::: moniker range="vs-2015"

### <a name="to-create-a-client-app-in-older-versions-of-visual-studio-2017"></a>이전 버전의 Visual Studio 2017에서 클라이언트 앱을 만들려면

1. 만든 DLL을 사용하는 C++ 앱을 만들려면 메뉴 모음에서 **파일** > **새로 만들기** > **프로젝트**를 선택합니다.

1. **새 프로젝트** 대화 상자의 왼쪽 창의 **설치됨** > **템플릿** > **Visual C++** 에서 **Win32**를 선택합니다. 가운데 창에서 **Win32 콘솔 애플리케이션**을 선택합니다. **이름** 편집 상자에 프로젝트 이름 `MathClient`를 지정합니다.

   ![클라이언트 프로젝트 이름 지정](media/mathclient-project-name.png "클라이언트 프로젝트 이름 지정")

1. **확인** 단추를 선택하여 **새 프로젝트** 대화 상자를 닫고 **Win32 애플리케이션 마법사**를 시작합니다. **Win32 응용 프로그램 마법사** 대화 상자의 **개요** 페이지에서 **다음** 단추를 선택합니다.

1. **애플리케이션 설정** 페이지의 **애플리케이션 유형**에서 **콘솔 애플리케이션**이 아직 선택되어 있지 않으면 선택합니다.

1. **마침** 단추를 선택하여 프로젝트를 만듭니다.

::: moniker-end

마법사가 완료되면 최소한의 콘솔 애플리케이션 프로젝트가 만들어집니다. 기본 소스 파일의 이름은 앞에서 입력한 프로젝트 이름과 같습니다. 이 예에서는 이름이 **MathClient.cpp**입니다. 이 프로젝트를 빌드할 수 있지만, 아직 DLL이 사용되지는 않습니다.

다음으로, 소스 코드에서 MathLibrary 함수를 호출하려면 프로젝트가 MathLibrary.h 파일을 포함해야 합니다. 이 헤더 파일을 클라이언트 앱 프로젝트에 복사한 후 프로젝트에 기존 항목으로 추가할 수 있습니다. 이 방법은 타사 라이브러리에 적합할 수 있습니다. 그러나 클라이언트와 동시에 DLL의 코드를 작업 중인 경우 한 헤더 파일의 변경 사항이 다른 헤더 파일에는 표시되지 않을 수 있습니다. 이 문제를 방지하려면 원래 헤더 경로를 포함하도록 프로젝트의 **추가 포함 디렉터리** 경로를 변경하면 됩니다.

### <a name="to-add-the-dll-header-to-your-include-path"></a>포함 경로에 DLL 헤더를 추가하려면

1. **솔루션 탐색기**에서 **MathClient** 노드를 마우스 오른쪽 단추로 클릭하여 **속성 페이지** 대화 상자를 엽니다.

1. **구성** 드롭다운 상자에서 **모든 구성**이 아직 선택되어 있지 않으면 선택합니다.

1. 왼쪽 창의 **구성 속성** > **C/C++** 에서 **일반**을 선택합니다.

1. 속성 창에서 **추가 포함 디렉터리** 편집 상자 옆에 있는 드롭다운 컨트롤을 선택한 후 **편집**을 선택합니다.

   ![추가 포함 디렉터리 속성 편집](media/mathclient-additional-include-directories-property.png "추가 포함 디렉터리 속성 편집")

1. **추가 포함 디렉터리** 대화 상자의 위쪽 창을 두 번 클릭하여 편집 컨트롤을 사용하도록 설정합니다.

1. 편집 컨트롤에서 **MathLibrary.h** 헤더 파일 위치 경로를 지정합니다. 아래쪽 화살표를 클릭 한 다음  **\<> 편집**을 선택 합니다. 폴더 아이콘을 클릭 한 다음 줄임표 ( **...** )를 클릭 하 여 올바른 폴더로 이동할 수 있습니다.
 
   이 경우 클라이언트 프로젝트의 .cpp 파일이 들어 있는 폴더의 상대 경로를 DLL 프로젝트의 .h 파일을 포함 하는 폴더로 입력할 수도 있습니다. 클라이언트 프로젝트가 DLL 솔루션과 같은 폴더의 별도 솔루션에 있는 경우 상대 경로는 다음과 같아야 합니다.

   `..\MathLibrary\MathLibrary`

   DLL 및 클라이언트 프로젝트가 동일한 솔루션에 있거나 솔루션이 다른 폴더에 있으면 상대 경로를 적절 하 게 조정 하거나 앞에서 설명한 방법을 사용 하 여 폴더를 검색 해야 합니다.

   ![추가 포함 디렉터리 속성에 헤더 위치 추가](media/mathclient-additional-include-directories.png "추가 포함 디렉터리 속성에 헤더 위치 추가")

1. **추가 포함 디렉터리** 대화 상자에서 헤더 파일에 대 한 경로를 입력 한 후 **확인** 단추를 선택 하 여 **속성 페이지** 대화 상자로 돌아간 다음 **확인** 단추를 선택 하 여 변경 내용을 저장 합니다.

이제 **MathLibrary.h** 파일을 포함하고 해당 파일이 클라이언트 애플리케이션에서 선언하는 함수를 사용할 수 있습니다. 다음 코드를 사용하여 **MathClient.cpp**의 내용을 바꿉니다.

```cpp
// MathClient.cpp : Client app for MathLibrary DLL.
// #include "pch.h" Uncomment for Visual Studio 2017 and earlier
#include <iostream>
#include "MathLibrary.h"

int main()
{
    // Initialize a Fibonacci relation sequence.
    fibonacci_init(1, 1);
    // Write out the sequence values until overflow.
    do {
        std::cout << fibonacci_index() << ": "
            << fibonacci_current() << std::endl;
    } while (fibonacci_next());
    // Report count of values written before overflow.
    std::cout << fibonacci_index() + 1 <<
        " Fibonacci sequence values fit in an " <<
        "unsigned 64-bit integer." << std::endl;
}
```

링커가 아직 앱을 빌드하는 데 필요한 가져오기 라이브러리를 찾을 수 없으므로 이 코드를 컴파일할 수는 있지만, 연결할 수는 없습니다. 연결하려면 링커가 MathLibrary.lib 파일을 찾아야 합니다. **추가 종속성** 속성을 설정하여 MathLibrary.lib 파일을 빌드에 추가합니다. 다시 한번 언급하면 라이브러리 파일을 클라이언트 앱 프로젝트에 복사할 수는 있지만, 라이브러리와 클라이언트 앱 둘 다 개발 중인 경우 한 복사본의 변경 사항이 다른 복사본에는 표시되지 않을 수 있습니다. 이 문제를 방지하려면 연결할 때 원래 라이브러리 경로를 포함하도록 프로젝트의 **추가 라이브러리 디렉터리** 경로를 변경하면 됩니다.

### <a name="to-add-the-dll-import-library-to-your-project"></a>프로젝트에 DLL 가져오기 라이브러리를 추가하려면

1. **솔루션 탐색기**에서 **MathClient** 노드를 마우스 오른쪽 단추로 클릭하여 **속성 페이지** 대화 상자를 엽니다.

1. **구성** 드롭다운 상자에서 **모든 구성**이 아직 선택되어 있지 않으면 선택합니다. 이 설정은 경로가 디버그 및 릴리스 빌드 둘 다에 대해 설정되도록 합니다.

1. 왼쪽 창의 **구성 속성** > **링커**에서 **입력**을 선택합니다. 속성 창에서 **추가 종속성** 편집 상자 옆에 있는 드롭다운 컨트롤을 선택한 후 **편집**을 선택합니다.

   ![추가 종속성 속성 편집](media/mathclient-additional-dependencies-property.png "추가 종속성 속성 편집")

1. **추가 종속성** 대화 상자에서 맨 위 편집 컨트롤의 목록에 `MathLibrary.lib`를 추가합니다.

   ![라이브러리 종속성 추가](media/mathclient-additional-dependencies.png "라이브러리 종속성 추가")

1. **확인**을 선택하여 **속성 페이지** 대화 상자로 돌아갑니다.

1. 왼쪽 창의 **구성 속성** > **링커**에서 **일반**을 선택합니다. 속성 창에서 **추가 라이브러리 디렉터리** 편집 상자 옆에 있는 드롭다운 컨트롤을 선택한 후 **편집**을 선택합니다.

   ![추가 라이브러리 디렉터리 속성 편집](media/mathclient-additional-library-directories-property.png "추가 라이브러리 디렉터리 속성 편집")

1. **추가 라이브러리 디렉터리** 대화 상자의 위쪽 창을 두 번 클릭하여 편집 컨트롤을 사용하도록 설정합니다. 편집 컨트롤에서 **MathLibrary.lib** 파일 위치 경로를 지정합니다. 솔루션 폴더 바로 아래에 있는 `Debug` 라는 폴더에 있습니다. 릴리스 빌드를 만들면 출력이 라는 `Release`폴더에 배치 됩니다. 다음 매크로를 사용 하 여 링커에서 만든 빌드 종류에 관계 없이 DLL을 찾을 수 있습니다.

   **Visual Studio 2019:**

   `..\MathLibrary\$(IntDir)`

   **Visual Studio 2017 이전 버전:**

   `..\..\MathLibrary\$(IntDir)`

   ![라이브러리 디렉터리 추가](media/mathclient-additional-library-directories.png "라이브러리 디렉터리 추가")

1. **추가 라이브러리 디렉터리** 대화 상자에서 라이브러리 파일 경로를 입력한 후에는 **확인** 단추를 선택하여 **속성 페이지** 대화 상자로 돌아갑니다.

이제 클라이언트 앱을 컴파일하고 연결할 수 있지만, 아직 실행하는 데 필요한 모든 사항이 갖춰지지는 않았습니다. 운영 체제가 앱을 로드할 때 MathLibrary DLL을 찾습니다. 특정 시스템 디렉터리, 환경 경로 또는 로컬 앱 디렉터리에서 DLL을 찾을 수 없는 경우 로드에 실패합니다. 이 문제를 방지하는 한 가지 방법은 빌드 프로세스의 일부로 클라이언트 실행 파일을 포함하는 디렉터리에 DLL을 복사하는 것입니다. DLL을 복사하려면 프로젝트에 **빌드 후 이벤트**를 추가하여 DLL을 빌드 출력 디렉터리에 복사하는 명령을 추가하면 됩니다. 여기에 지정된 명령은 DLL이 누락되었거나 변경된 경우에만 DLL을 복사하고, 매크로를 사용하여 구성에 대해 올바른 디버그 또는 릴리스 위치로/에서 복사합니다.

### <a name="to-copy-the-dll-in-a-post-build-event"></a>빌드 후 이벤트에 DLL을 복사하려면

1. **솔루션 탐색기**에서 **MathClient** 노드를 마우스 오른쪽 단추로 클릭하여 **속성 페이지** 대화 상자를 엽니다.

1. 구성 드롭다운 상자에서 **모든 구성**이 아직 선택되어 있지 않으면 선택합니다.

1. 왼쪽 창의 **구성 속성** > **빌드 이벤트**에서 **빌드 후 이벤트**를 선택합니다.

1. 속성 창의 **명령줄** 필드에서 편집 컨트롤을 선택한 후 다음 명령을 입력합니다.

   **Visual Studio 2019:**

   `xcopy /y /d "..\MathLibrary\$(IntDir)MathLibrary.dll" "$(OutDir)"`

    **Visual Studio 2017 이전 버전:**

   `xcopy /y /d "..\..\MathLibrary\$(IntDir)MathLibrary.dll" "$(OutDir)"`

   ![빌드 후 명령 추가](media/mathclient-post-build-command-line.png "빌드 후 명령 추가")

1. **확인** 단추를 선택하여 프로젝트 속성의 변경 사항을 저장합니다.

이제 클라이언트 앱을 빌드 및 실행하는 데 필요한 모든 사항이 갖춰졌습니다. 메뉴 모음에서 **빌드** > **솔루션 빌드**를 선택하여 애플리케이션을 빌드합니다. Visual Studio의 **출력** 창에는 visual studio의 버전에 따라 다음 예제와 같은 항목이 있어야 합니다.

```Output
1>------ Build started: Project: MathClient, Configuration: Debug Win32 ------
1>pch.cpp
1>MathClient.cpp
1>MathClient.vcxproj -> C:\Users\username\Source\Repos\MathClient\Debug\MathClient.exe
1>MathClient.vcxproj -> C:\Users\username\Source\Repos\MathClient\Debug\MathClient.pdb (Partial PDB)
1>1 File(s) copied
========== Build: 1 succeeded, 0 failed, 0 up-to-date, 0 skipped ==========
```

축하합니다. DLL의 함수를 호출하는 애플리케이션을 만들었습니다. 이제 애플리케이션을 실행하여 수행하는 작업을 확인합니다. 메뉴 모음에서 **디버그** > **디버깅하지 않고 시작**을 선택합니다. Visual Studio에서 프로그램을 실행하기 위한 명령 창이 열립니다. 출력의 마지막 부분은 다음과 같습니다.

![디버깅하지 않고 클라이언트 앱 시작](media/mathclient-run-without-debugging.png "디버깅하지 않고 클라이언트 앱 시작")

아무 키나 눌러 명령 창을 닫습니다.

이제 DLL과 클라이언트 애플리케이션을 만들었으므로 실험할 수 있습니다. 클라이언트 앱의 코드에 중단점을 설정하고 디버거에서 앱을 실행합니다. 라이브러리 호출을 한 단계씩 코드 실행할 때 어떤 일이 발생하는지 확인합니다. 라이브러리에 DLL을 사용하는 다른 함수를 추가하거나, DLL을 사용하는 다른 클라이언트 앱을 작성합니다.

앱을 배포할 때 앱에 사용되는 DLL도 배포해야 합니다. 직접 빌드하거나 타사에서 포함하는 DLL을 앱에서 사용할 수 있도록 하는 가장 간단한 방법은 DLL을 앱과 같은 디렉터리에 배치하는 것입니다. 이를 ‘app-local 배포’라고도 합니다.  배포에 대한 자세한 내용은 [Deployment in Visual C++](../windows/deployment-in-visual-cpp.md)를 참조하세요.

## <a name="see-also"></a>참고자료

[Visual Basic 응용 프로그램에서 DLL 함수 호출](calling-dll-functions-from-visual-basic-applications.md)
