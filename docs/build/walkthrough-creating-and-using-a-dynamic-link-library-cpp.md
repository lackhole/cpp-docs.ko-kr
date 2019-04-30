---
title: '연습: 만들고 고유한 동적 연결 라이브러리를 사용 하 여 (C++)'
ms.custom: conceptual
ms.date: 09/24/2018
helpviewer_keywords:
- libraries [C++], DLLs
- DLLs [C++], walkthroughs
ms.assetid: 3ae94848-44e7-4955-bbad-7d40f493e941
ms.openlocfilehash: 248b423659d026774d4945ee6330a39dc4c6e16e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62314557"
---
# <a name="walkthrough-create-and-use-your-own-dynamic-link-library-c"></a>연습: 만들고 고유한 동적 연결 라이브러리를 사용 하 여 (C++)

이 단계별 연습으로 작성 된 고유한 동적 연결 라이브러리 (DLL)를 만들려면 Visual Studio IDE를 사용 하는 방법을 보여 줍니다 C++를 사용 하 여 다른 및 C++ 앱. Dll은 가장 유용한 종류의 Windows 구성 요소 중 하나입니다. 앱의 크기를 축소 하 고 서비스 및 앱 확장을 쉽게 수행할 수 있도록 코드 및 리소스를 공유 하는 방법으로 이러한를 사용할 수 있습니다. 이 연습에서는 일부 수학 함수를 구현 하는 DLL 만들고 DLL에서 함수를 사용 하는 콘솔 앱을 만듭니다. 이 과정에서 몇 가지 프로그래밍 하는 방법과 Windows Dll에 사용 된 규칙에 대 한 소개를 얻게 됩니다.

이 연습에서는 다음 작업 방법을 배웁니다.

- Visual Studio에서 DLL 프로젝트를 만듭니다.

- Dll 내보내기 함수 및 변수를 추가 합니다.

- Visual Studio에서 콘솔 앱 프로젝트를 만듭니다.

- 콘솔 앱에서 DLL에서 가져온 변수와 함수를 사용 합니다.

- 완성된 된 앱을 실행 합니다.

DLL를 정적으로 연결 된 라이브러리와 같은 _내보냅니다_ 변수, 함수 및 리소스 이름과 앱 _가져옵니다_ 해당 이름을 해당 변수, 함수 및 리소스를 사용 합니다. 정적으로 연결 된 라이브러리에 Windows 앱에서 가져오기를 로드 시 또는 링크 타임에 연결 하는 대신 런타임 시 DLL에서 내보내기에 연결 됩니다. Windows 표준에 속하지 않는 추가 정보 필요 C++ 이러한 연결을 만들 수 있는 컴파일 모델입니다. MSVC 컴파일러 구현 일부 Microsoft 전용 확장을 C++ 이 추가 정보를 제공 합니다. 이러한 확장으로 설명 합니다.

이 연습에서는 두 Visual Studio 솔루션 DLL을 작성 하는 하나 및 클라이언트 앱을 작성 하는 것입니다. DLL은 플랫폼 호출 및 규칙 연결 일치할 다른 언어를 사용 하 여 빌드한 앱에서 호출 될 수 있으므로 C 호출 규칙을 사용 합니다. 클라이언트 앱에서는 _암시적 링크_, Windows가 로드 시 DLL에 대 한 앱을 연결 하는 위치입니다. 이 연결 앱을 정적으로 연결 된 라이브러리의 함수 처럼 DLL에서 제공한 함수를 호출할 수 있습니다.

이 연습에서는 몇 가지 일반적인 상황을 다루지 않습니다. 사용 하는 표시 되지 않지만 C++ 다른 프로그래밍 언어에서 Dll입니다. 리소스 전용 DLL을 만드는 방법을 표시 되지는 않습니다. 또한 런타임 시 아닌 로드 시 Dll을 로드 하려고 명시적 링크의 사용도 표시 되지 않습니다. 안심할 수, 시각적 개체를 사용할 수 있습니다 C++ 이러한 모든 작업을 수행할 수 있습니다. Dll에 대 한 자세한 정보 링크를 참조 하세요 [Dll 시각적 개체의 C++ ](dlls-in-visual-cpp.md)합니다. 암시적 링크 및 명시적 링크에 대 한 자세한 내용은 참조 하세요. [사용할 링크 방법 결정](linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)합니다. 만드는 방법은 C++ 프로그래밍 참조를 C 언어 링크 규칙을 사용 하는 언어 사용에 대 한 Dll [내보내기 C++ C 언어 실행 파일에서 사용 하기 위한 함수가](exporting-cpp-functions-for-use-in-c-language-executables.md)합니다. .NET 언어 사용에 대 한 Dll을 만드는 방법에 대 한 자세한 내용은 [Visual Basic 응용 프로그램에서 DLL 함수 호출](calling-dll-functions-from-visual-basic-applications.md)합니다.

이 연습에서는 Visual Studio 2017을 사용 하지만 코드 및 지침의 대부분 이전 버전에 적용 됩니다. 새 프로젝트를 빌드하는 단계는 Visual Studio 2017 버전 15.3부터 변경 합니다. 이 연습에는 최신 및 이전 버전에 대 한 프로젝트를 만드는 방법을 설명 합니다. Visual Studio의 버전과 일치 하는 단계를 찾습니다.

## <a name="prerequisites"></a>전제 조건

- Microsoft Windows 7 이상을 실행 하는 컴퓨터입니다. 최상의 개발 환경을 위해 Windows 10이 좋습니다.

- Visual Studio 2017의 복사본입니다. 다운로드 하 여 Visual Studio를 설치 하는 방법에 대 한 정보를 참조 하세요 [Visual Studio 2017 설치](/visualstudio/install/install-visual-studio)합니다. 설치 관리자를 실행 해야 합니다 **를 사용한 데스크톱 개발 C++**  작업 확인란이 선택 되어 있습니다. Visual Studio를 설치할 때이 워크 로드를 설치 하지 않은 경우 걱정 하지 마세요. 설치 관리자를 다시 실행 하 고 지금 설치 수 있습니다.

   ![사용한 데스크톱 개발 C++ ](media/desktop-development-with-cpp.png "를 사용한 데스크톱 개발C++")

- Visual Studio IDE를 사용 하 여의 기본 사항 이해 합니다. 이전 Windows 데스크톱 앱을 사용한 경우 아마도 유지할 수 있습니다. 참조에 대 한 소개 [Visual Studio IDE 기능 둘러보기](/visualstudio/ide/visual-studio-ide)합니다.

- 기본 사항을 충분히 이해 합니다 C++ 과정을 따르려면 언어입니다. 걱정 하지 마십시오, 너무 복잡 아무일도 하지 않는 것입니다.

## <a name="create-the-dll-project"></a>DLL 프로젝트 만들기

DLL 프로젝트를 만드는 작업의이 집합에서 코드를 추가 빌드합니다. 시작 하려면 Visual Studio IDE를 시작 하 고 하는 경우 로그인 합니다. Visual Studio 2017 버전 15.3에 대 한 지침 앞에 옵니다. 이전 버전에 대 한 지침은 나중으로 따라서 건너 뛰 세요 해야 할 경우.

### <a name="to-create-a-dll-project-in-visual-studio-2017-version-153-or-later"></a>DLL에서에서 프로젝트를 만들려면 Visual Studio 2017 버전 15.3 이상

1. 메뉴 모음에서 **파일** > **새로 만들기** > **프로젝트**를 선택하여 **새 프로젝트** 대화 상자를 엽니다.

1. 왼쪽된 창에서 합니다 **새 프로젝트** 대화 상자에서 **설치 됨** 및 **Visual C++**  필요한 경우 선택한 후 **Windows데스크톱**. 가운데 창에서 선택 **Windows 데스크톱 마법사**합니다. 입력 `MathLibrary` 에 **이름을** 상자에서 프로젝트의 이름을 지정 합니다.

   ![MathLibrary 프로젝트 이름을](media/mathlibrary-new-project-name-153.png "MathLibrary 프로젝트 이름을")

1. 선택 합니다 **확인** 해제 하려면 단추를 **새 프로젝트** 대화 상자 및 시작 합니다 **Windows 데스크톱 프로젝트** 마법사.

1. 에 **Windows 데스크톱 프로젝트** 마법사 **응용 프로그램 종류**를 선택 **동적 연결 라이브러리 (.dll)** 합니다.

   ![Windows 데스크톱 프로젝트 마법사에서 DLL을 만들](media/mathlibrary-desktop-project-wizard-dll.png "Windows 데스크톱 프로젝트 마법사에서 DLL 만들기")

1. **확인** 단추를 선택하여 프로젝트를 만듭니다.

> [!NOTE]
> Visual Studio 2017 버전 15.3의에서 문제를 해결 하려면 추가 단계가 필요 합니다. 이 변경을 수행 해야 하는 경우를 확인 하려면 다음이 지침을 따릅니다.
>
>1. **솔루션 탐색기**아직 없는 선택한 경우 합니다 **MathLibrary** 프로젝트 **솔루션 'MathLibrary'** 합니다.
>
>1. 메뉴 모음에서 **프로젝트** > **속성**을 선택합니다.
>
>1. **속성 페이지** 대화 상자의 왼쪽 창에서 **구성 속성** > **C/C++** 아래의 **전처리기**를 선택합니다. **전처리기 정의** 속성의 콘텐츠를 확인합니다.<br/><br/>![전처리기 정의 속성을 확인하세요](media/mathlibrary-153bug-preprocessor-definitions-check.png "전처리기 정의 속성 확인")<br/><br/> **전처리기 정의** 목록에 **MATHLIBRARY&#95;EXPORTS**가 표시되면 아무 것도 변경하지 않아도 됩니다. **MathLibrary&#95;EXPORTS**가 대신 표시되면 다음 단계를 계속 수행합니다.
>
>1. 맨 위에 있는 합니다 **속성 페이지** 대화 상자에서 변경 합니다 **구성** 드롭다운을 **모든 구성**합니다.
>
>1. 속성 창에서 선택에 대 한 입력란 옆에 있는 드롭다운 컨트롤 **전처리기 정의**를 선택한 후 **편집**합니다.<br/><br/>![전처리기 정의 속성 편집](media/mathlibrary-153bug-preprocessor-definitions-property.png "전처리기 정의 속성 편집")
>
>1. 위쪽 창에는 **전처리기 정의** 대화 상자에서 새 기호를 추가 `MATHLIBRARY_EXPORTS`합니다.<br/><br/>![MATHLIBRARY_EXPORTS 기호를 추가할](media/mathlibrary-153bug-preprocessor-definitions-dialog.png "MATHLIBRARY_EXPORTS 기호를 추가 합니다.")
>
>1. 선택 **확인** 해제 하는 **전처리기 정의** 대화 상자에서 선택한 후 **확인** 프로젝트 속성에 변경 내용을 저장 하려면.

### <a name="to-create-a-dll-project-in-older-versions-of-visual-studio"></a>이전 버전의 Visual Studio에서 DLL 프로젝트를 만들려면

1. 메뉴 모음에서 **파일** > **새로 만들기** > **프로젝트**를 선택합니다.

1. 왼쪽된 창에서를 **새 프로젝트** 대화 상자에서 **설치 됨** > **템플릿**를 선택한 **시각적 C++** 를 선택한 다음 가운데 창에서 **Win32 콘솔 응용 프로그램**합니다. 입력 `MathLibrary` 에 **이름** 편집 상자에서 프로젝트의 이름을 지정 합니다.

   ![MathLibrary 프로젝트 이름을](media/mathlibrary-project-name.png "MathLibrary 프로젝트 이름을")

1. 선택 합니다 **확인** 해제 하려면 단추를 **새 프로젝트** 대화 상자 및 시작 합니다 **Win32 응용 프로그램 마법사**.

   ![Win32 응용 프로그램 마법사 개요](media/mathlibrary-project-wizard-1.png "Win32 응용 프로그램 마법사 개요")

1. **다음** 단추를 선택합니다. 에 **응용 프로그램 설정** 페이지의 **응용 프로그램 종류**를 선택 **DLL**합니다.

   ![Win32 응용 프로그램 마법사에서 DLL을 만듭니다](media/mathlibrary-project-wizard-2.png "Win32 응용 프로그램 마법사에서 DLL 만들기")

1. **마침** 단추를 선택하여 프로젝트를 만듭니다.

마법사를 완료 된 솔루션에서 생성 된 프로젝트 및 원본 파일을 볼 수 있습니다 합니다 **솔루션 탐색기** Visual Studio의 창.

![Visual Studio에서 솔루션을 생성](media/mathlibrary-solution-explorer-153.png "Visual Studio에서 솔루션을 생성 합니다.")

오른쪽 이제이 DLL 하지 많은 작업을 수행 합니다. DLL 함수를 선언 하려면 헤더 파일을 만들려면 다음을 내보내고 다음 함수 정의 더 유용 하 게 하려면 DLL에 대 한 추가 합니다.

### <a name="to-add-a-header-file-to-the-dll"></a>DLL에 헤더 파일을 추가 하려면

1. 메뉴 모음에서 사용자 함수에 대 한 헤더 파일을 만들려면 **프로젝트** > **새 항목 추가**합니다.

1. 에 **새 항목 추가** 대화 상자의 왼쪽된 창에서 선택 **시각적 C++** 합니다. 가운데 창에서 **헤더 파일 (.h)** 을 선택합니다. 지정 `MathLibrary.h` 헤더 파일의 이름으로 합니다.

   ![새 항목 추가 대화 상자에서 추가 헤더](media/mathlibrary-add-new-item-header-file.png "새 항목 추가 대화 상자에서 추가 헤더 파일")

1. 선택 된 **추가** 새 편집기 창에 표시 되는 빈 헤더 파일을 생성 하는 단추입니다.

   ![편집기에서 빈 MathLibrary.h 파일](media/edit-empty-mathlibrary-header.png "편집기에서 빈 MathLibrary.h 파일")

1. 헤더 파일의 내용을이 코드로 바꿉니다.

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

이 헤더 파일을 일반화 된 피보나치 시퀀스 두 지정 된 초기 값을 생성 하기 위해 일부 함수를 선언 합니다. 에 대 한 호출 `fibonacci_init(1, 1)` 친숙 한 피보나치 숫자 시퀀스를 생성 합니다.

파일의 맨 위에 있는 전처리기 문을 확인할 수 있습니다. 기본적으로 새 프로젝트 템플릿은 DLL에 대 한 추가  **<em>PROJECTNAME</em>&#95;내보내기** DLL 프로젝트에 대해 정의 된 전처리기 매크로입니다. 이 예제에서는 Visual Studio는 다음과 같이 정의 됩니다. **MATHLIBRARY&#95;내보내기** MathLibrary DLL 프로젝트를 빌드할 경우. (Visual Studio 2017 버전 15.3에서에서 마법사를 대문자로이 기호 정의 강제 하지 않습니다. "MathLibrary" 프로젝트 이름을 지정할 경우 정의 된 기호는 MathLibrary&#95;MATHLIBRARY 대신 내보내기&#95;내보냅니다. That's 이유는이 기호를 추가 하려면 위의 추가 단계입니다.)

경우는 **MATHLIBRARY&#95;내보내기** 매크로가 정의 된를 **MATHLIBRARY&#95;API** 매크로 집합을 `__declspec(dllexport)` 함수 선언에서 한정자입니다. 이 한정자는 컴파일러 및 링커에서의 다른 응용 프로그램에서 사용할 수 있도록 DLL에서 함수 또는 변수를 내보낼 수를 알려줍니다. 때 **MATHLIBRARY&#95;내보내기** 정의 되어 있지 예를 들어, 헤더 파일을 클라이언트 응용 프로그램에서 포함 되 면 **MATHLIBRARY&#95;API** 적용 되는 `__declspec(dllimport)` 한정자를는 선언입니다. 이 한정자는 함수 또는 응용 프로그램에는 변수 가져오기를 최적화합니다. 자세한 내용은 [dllexport, dllimport](../cpp/dllexport-dllimport.md)합니다.

### <a name="to-add-an-implementation-to-the-dll"></a>DLL에 구현을 추가 하려면

1. 편집기 창에서 탭을 선택 **MathLibrary.cpp** 이미 열려 있으면입니다. 그렇지 않은 경우에 **솔루션 탐색기**오픈 **MathLibrary.cpp** 에 **소스 파일** 의 폴더를 **MathLibrary** 프로젝트.

1. 편집기에서 MathLibrary.cpp 파일의 내용을 다음 코드로 바꿉니다.

   ```cpp
   // MathLibrary.cpp : Defines the exported functions for the DLL.
   #include "stdafx.h"
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

모든 지금 작동 하는지 확인 하려면 동적 연결 라이브러리를 컴파일하십시오. 를 컴파일하려면 선택 **빌드합니다** > **솔루션 빌드** 메뉴 모음에서. 출력 같이 표시 됩니다.

```Output
1>------ Build started: Project: MathLibrary, Configuration: Debug Win32 ------
1>stdafx.cpp
1>MathLibrary.cpp
1>dllmain.cpp
1>Generating Code...
1>   Creating library C:\Users\username\Source\Repos\MathLibrary\Debug\MathLibrary.lib and object C:\Users\username\Source\Repos\MathLibrary\Debug\MathLibrary.exp
1>MathLibrary.vcxproj -> C:\Users\username\Source\Repos\MathLibrary\Debug\MathLibrary.dll
1>MathLibrary.vcxproj -> C:\Users\username\Source\Repos\MathLibrary\Debug\MathLibrary.pdb (Partial PDB)
========== Build: 1 succeeded, 0 failed, 0 up-to-date, 0 skipped ==========
```

축에서 만든 시각적 개체를 사용 하 여 DLL C++! 그런 다음 해당 DLL에서 내보내기 기능을 사용 하는 클라이언트 앱을 만들어야 합니다.

## <a name="create-a-client-app-that-uses-the-dll"></a>DLL을 사용 하는 클라이언트 앱 만들기

DLL을 만들면 DLL 사용할 수 있는 방법을 고려해 야 합니다. DLL에서 내보낸 함수를 호출 하는 코드를 컴파일하려면 선언은 클라이언트 소스 코드에 포함 되어야 합니다. 링커 있어야 이러한 DLL 함수이 호출 해결 되 면 링크 타임에 *가져오기 라이브러리*, 실제 코드 대신 함수를 찾는 방법에 대 한 Windows에 대 한 정보를 포함 하는 특별 한 라이브러리 파일입니다. 및 런타임 시 DLL 클라이언트 운영 체제를 찾을 수 있는 위치를 사용할 수 있어야 합니다.

DLL을 사용 하는지 여부를 소유 하거나 타사 DLL 클라이언트 앱 프로젝트를 찾아야 DLL을 선언 하는 헤더 내보냅니다, 링크 및 자체 DLL에 대 한 가져오기 라이브러리입니다. 한 가지 방법은 클라이언트 프로젝트에 모든이 파일을 복사 하는 것입니다. 클라이언트 개발에 있는 동안 변경할 수 없는 타사 Dll이이 방법을 사용 하는 가장 좋은 방법은 수 있습니다. 그러나 또한 DLL을 빌드할 때 것이 좋습니다 중복을 방지 하려면. 개발 중인 DLL 파일의 복사본을 만들면 실수로 하나의 복사본이 아니라, 헤더 파일을 변경할 수도 있습니다 오래 된 라이브러리를 사용 합니다. 이 문제를 방지 하려면 DLL 프로젝트에서 DLL 헤더 파일을 포함 하 여 클라이언트 프로젝트의 포함 경로 설정 하는 것이 좋습니다. 또한 DLL 프로젝트에서 DLL 가져오기 라이브러리를 포함 하 여 클라이언트 프로젝트의 라이브러리 경로 설정 합니다. 마지막으로, 빌드 출력 디렉터리에 DLL 프로젝트에서 빌드된 DLL을 복사 합니다. 이 단계에서는 클라이언트 앱을 빌드하면 동일한 DLL 코드를 사용 하도록 합니다.

### <a name="to-create-a-client-app-in-visual-studio-2017-version-153-or-later"></a>클라이언트에서에서 앱을 만들려면 Visual Studio 2017 버전 15.3 이상

1. 만들려는 C++ 메뉴 모음에서 만든 DLL을 사용 하는 앱 선택 **파일** > **새로 만들기** > **프로젝트**.

1. 왼쪽된 창에서를 **새 프로젝트** 대화 상자에서 **Windows 데스크톱** 아래 **설치 됨** > **시각적 C++** . 가운데 창에서 선택 **Windows 데스크톱 마법사**합니다. 프로젝트의 이름을 지정 `MathClient`를 **이름을** 편집 상자입니다.

   ![클라이언트 프로젝트의 이름을](media/mathclient-new-project-name-153.png "클라이언트 프로젝트의 이름을")

1. 선택할 **확인** 시작 하는 **Windows 바탕 화면 프로젝트** 마법사. 마법사에서 선택 **확인** 클라이언트 앱 프로젝트를 만듭니다.

### <a name="to-create-a-client-app-in-older-versions-of-visual-studio-2017"></a>Visual Studio 2017의 이전 버전의 클라이언트 앱을 만들려면

1. 만들려는 C++ 메뉴 모음에서 만든 DLL을 사용 하는 앱 선택 **파일** > **새로 만들기** > **프로젝트**.

1. 왼쪽된 창에는 **새 프로젝트** 대화 상자에서 **Win32** 아래에 있는 **설치 됨** > **템플릿**  >  **시각적 C++** 합니다. 가운데 창에서 **Win32 콘솔 애플리케이션**을 선택합니다. 프로젝트의 이름을 지정 `MathClient`를 **이름을** 편집 상자입니다.

   ![클라이언트 프로젝트의 이름을](media/mathclient-project-name.png "클라이언트 프로젝트의 이름을")

1. 선택 합니다 **확인** 해제 하려면 단추를 **새 프로젝트** 대화 상자 및 시작 합니다 **Win32 응용 프로그램 마법사**. **Win32 응용 프로그램 마법사** 대화 상자의 **개요** 페이지에서 **다음** 단추를 선택합니다.

1. 에 **응용 프로그램 설정** 페이지의 **응용 프로그램 종류**를 선택 **콘솔 응용 프로그램** 아직 선택 하지 않은 경우.

1. **마침** 단추를 선택하여 프로젝트를 만듭니다.

마법사를 완료 하는 경우에 최소한의 콘솔 응용 프로그램 프로젝트를 자동으로 만들어집니다. 기본 소스 파일의 이름을 이전에 입력 한 프로젝트 이름과 같습니다. 이 예제에서는 이름이 **MathClient.cpp**합니다. 작성할 수 있지만 아직 DLL을 사용 하지 않습니다.

다음으로, 소스 코드에서 MathLibrary 함수를 호출 하려면 프로젝트가 MathLibrary.h 파일을 포함 해야 합니다. 클라이언트 앱 프로젝트에이 헤더 파일을 복사 합니다. 다음 기존 항목을 프로젝트에 추가할 수 있습니다. 이 방법은 타사 라이브러리에 적합 한 수 있습니다. 그러나 작업 중인 코드를 DLL에 대 한 동시에 클라이언트로, 하는 다른 표시 되지 않는 한 헤더 파일의 변경 내용에 발생할 수 있습니다. 이 문제를 방지 하려면 변경할 수 있습니다 합니다 **Additional Include Directories** 원래 머리글에 대 한 경로 포함 하도록 프로젝트의 경로입니다.

### <a name="to-add-the-dll-header-to-your-include-path"></a>DLL 헤더를 추가 하 여 경로 포함 합니다.

1. 엽니다는 **속성 페이지** 대화 상자를 **MathClient** 프로젝트입니다.

1. 에 **Configuration** 드롭다운 목록 상자에서 **모든 구성** 아직 선택 하지 않은 경우.

1. 왼쪽된 창에서 선택 **일반적인** 아래에서 **구성 속성** > **C /C++**.

1. 속성 창의 드롭다운 목록 컨트롤을 옆에 선택 합니다 **Additional Include Directories** 편집 상자를 선택한 후 **편집**합니다.

   ![추가 포함 디렉터리 속성을 편집할](media/mathclient-additional-include-directories-property.png "Additional Include Directories 속성 편집")

1. 위쪽 창에서 두 번 클릭 합니다 **Additional Include Directories** 대화 상자 편집 컨트롤을 사용 하도록 설정 합니다.

1. 편집 컨트롤에서의 위치로 경로 지정 합니다 **MathLibrary.h** 헤더 파일입니다. 이 경우에 DLL 프로젝트에서.h 파일이 포함 된 폴더에 클라이언트 프로젝트에서.cpp 파일이 포함 된 폴더에서 상대 경로 사용할 수 있습니다. 클라이언트 프로젝트가 DLL 솔루션과 같은 폴더에 별도 솔루션의 경우 상대 경로 다음과 같습니다.

   `..\..\MathLibrary\MathLibrary`

   동일한 솔루션에는 DLL과 클라이언트 프로젝트 또는 솔루션은 서로 다른 폴더에 상대 경로 적절히 조정 해야 합니다.

   ![추가 포함 디렉터리 속성에 헤더 위치를 추가](media/mathclient-additional-include-directories.png "Additional Include Directories 속성에 헤더 위치를 추가 합니다.")

1. 헤더 파일에 경로 입력 한 후는 **Additional Include Directories** 대화 상자를 선택 합니다 **확인** 돌아가려면 단추를 **속성 페이지** 대화 상자에서 및 선택 합니다 **확인** 변경 내용을 저장 하는 단추입니다.

이제 포함할 수 있습니다 합니다 **MathLibrary.h** 파일을 클라이언트 응용 프로그램에서 선언 된 함수를 사용 합니다. 내용을 바꿉니다 **MathClient.cpp** 이 코드를 사용 하 여:

```cpp
// MathClient.cpp : Client app for MathLibrary DLL.
#include "pch.h"
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

이 코드를 컴파일할 수는 있지만 연결을 해제 하면 링커는 아직 앱을 빌드하는 데 필요한 가져오기 라이브러리를 찾을 수 없기 때문입니다. 링커는 성공적으로 연결할 MathLibrary.lib 파일을 찾아야 합니다. 설정 하 여 빌드에 MathLibrary.lib 파일을 추가 합니다 **추가 종속성** 속성입니다. 다시 한 번 클라이언트 앱 프로젝트에 라이브러리 파일을 복사할 수 있지만 라이브러리와 클라이언트 앱을 개발 중인 경우 다른 표시 되지 않는 한 복사본에 변경 내용에 발생할 수 있습니다는. 이 문제를 방지 하려면 변경할 수 있습니다 합니다 **추가 라이브러리 디렉터리** 연결 하면 원래 라이브러리 경로 포함 하도록 프로젝트의 경로입니다.

### <a name="to-add-the-dll-import-library-to-your-project"></a>DLL 가져오기 라이브러리 프로젝트에 추가 하려면

1. 엽니다는 **속성 페이지** 대화 상자를 **MathClient** 프로젝트입니다.

1. 에 **Configuration** 드롭다운 목록 상자에서 **모든 구성** 아직 선택 하지 않은 경우.

1. 왼쪽된 창에서 선택 **입력** 아래에서 **구성 속성** > **링커**합니다. 속성 창의 드롭다운 목록 컨트롤을 옆에 선택 합니다 **추가 종속성** 편집 상자를 선택한 후 **편집**합니다.

   ![추가 종속성 속성을 편집할](media/mathclient-additional-dependencies-property.png "추가 종속성 속성 편집")

1. 에 **추가 종속성** 대화 상자에서 추가 `MathLibrary.lib` 위쪽의 목록에 컨트롤을 편집 합니다.

   ![추가 라이브러리 종속성](media/mathclient-additional-dependencies.png "라이브러리 종속성 추가")

1. 선택할 **확인** 돌아가려면 합니다 **속성 페이지** 대화 상자.

1. 왼쪽된 창에서 선택 **일반적인** 아래에서 **구성 속성** > **링커**합니다. 속성 창의 드롭다운 목록 컨트롤을 옆에 선택 합니다 **추가 라이브러리 디렉터리** 편집 상자를 선택한 후 **편집**합니다.

   ![추가 라이브러리 디렉터리 속성 편집](media/mathclient-additional-library-directories-property.png "추가 라이브러리 디렉터리 속성 편집")

1. 위쪽 창에서 두 번 클릭 합니다 **추가 라이브러리 디렉터리** 대화 상자 편집 컨트롤을 사용 하도록 설정 합니다. 편집 컨트롤에서의 위치로 경로 지정 합니다 **MathLibrary.lib** 파일입니다. 매크로 적합 디버그 및 릴리스 빌드를 사용 하려면이 값을 입력 합니다.

   `..\..\MathLibrary\$(IntDir)`

   ![추가 라이브러리 디렉터리](media/mathclient-additional-library-directories.png "추가 라이브러리 디렉터리")

1. 라이브러리 파일에 경로 입력 한 후 합니다 **추가 라이브러리 디렉터리** 대화 상자를 선택 합니다 **확인** 돌아가려면 단추를 **속성 페이지** 대화 상자.

이제 클라이언트 앱 컴파일하고 성공적으로 연결할 수 있습니다 하지만 여전히 반드시 실행 하는 데 필요한 합니다. 운영 체제에서 앱을 로드 하면 MathLibrary DLL를 찾습니다. 특정 시스템 디렉터리, 환경 경로 또는 로컬 앱 디렉터리에서 DLL 찾을 수 없으면, 로드가 실패 합니다. 이 문제를 방지 하는 한 방법은 DLL 빌드 프로세스의 일부로 클라이언트 실행 파일을 포함 하는 디렉터리에 복사할 것입니다. DLL을 복사 하려면 추가할 수 있습니다는 **빌드 후 이벤트** 프로젝트에 명령을 추가 하려면 복사 하는 DLL 빌드 출력 디렉터리에 있습니다. 여기에 지정 된 명령이 없는 또는 변경 된 매크로 사용 하 여 구성에 대 한 올바른 일반 정품 또는 디버그 위치에서 복사 하 고 경우에 DLL을 복사 합니다.

### <a name="to-copy-the-dll-in-a-post-build-event"></a>빌드 후 이벤트에서 DLL을 복사 하려면

1. 엽니다는 **속성 페이지** 대화 상자를 **MathClient** 아직 열려 있지 않은 경우 프로젝트입니다.

1. 구성 드롭다운 목록 상자에서 선택 **모든 구성** 아직 선택 하지 않은 경우.

1. 왼쪽된 창에서 선택 **빌드 후 이벤트** 아래에서 **구성 속성** > **빌드 이벤트**합니다.

1. 속성 창에서에서 편집 컨트롤을 선택 합니다 **명령줄** 필드를 제거한 후이 명령을 입력:

   `xcopy /y /d "..\..\MathLibrary\$(IntDir)MathLibrary.dll" "$(OutDir)"`

   ![추가 빌드 후 명령](media/mathclient-post-build-command-line.png "빌드 후 명령 추가")

1. 선택 된 **확인** 프로젝트 속성에 변경 내용을 저장 하는 단추입니다.

이제 클라이언트 앱에는 빌드 및 실행 하는 데 필요한 선택 하 여 응용 프로그램을 빌드합니다 **빌드합니다** > **솔루션 빌드** 메뉴 모음에서. 합니다 **출력** Visual Studio 창에에서 다음과 같은 항목이 포함 해야 합니다.

```Output
1>------ Build started: Project: MathClient, Configuration: Debug Win32 ------
1>pch.cpp
1>MathClient.cpp
1>MathClient.vcxproj -> C:\Users\username\Source\Repos\MathClient\Debug\MathClient.exe
1>MathClient.vcxproj -> C:\Users\username\Source\Repos\MathClient\Debug\MathClient.pdb (Partial PDB)
1>1 File(s) copied
========== Build: 1 succeeded, 0 failed, 0 up-to-date, 0 skipped ==========
```

축 하 DLL에서 함수를 호출 하는 응용 프로그램을 만들었습니다. 이제 무엇을 표시 하도록 응용 프로그램을 실행 합니다. 메뉴 모음에서 선택 **디버깅할** > **디버깅 하지 않고 시작**합니다. Visual Studio에서 실행 하려면 프로그램에 대 한 명령 창을 엽니다. 출력의 마지막 부분이 같습니다.

![클라이언트 앱을 디버깅 하지 않고 시작](media/mathclient-run-without-debugging.png "클라이언트 앱을 디버깅 하지 않고 시작")

명령 창을 닫으려면 아무 키나를 누릅니다.

DLL 및 클라이언트 응용 프로그램을 만든 했으므로 실험할 수 있습니다. 클라이언트 앱 코드에서 중단점을 설정 해 디버거에서 앱을 실행 합니다. 라이브러리 호출 한 단계씩 실행할 때 어떻게 되는지 확인 합니다. 라이브러리에 다른 함수를 추가 하거나 DLL을 사용 하는 다른 클라이언트 앱을 작성 합니다.

앱을 배포할 때 사용 하 여 Dll도 배포 해야 합니다. Dll을 작성 하는 또는 포함 하는 제 3 자에서 사용할 수 있도록 앱을 위한 가장 간단한 방법은 라고도 앱을 동일한 디렉터리에 넣습니다 *app-local 배포*합니다. 배포에 대한 자세한 내용은 [Deployment in Visual C++](../windows/deployment-in-visual-cpp.md)를 참조하세요.

## <a name="see-also"></a>참고자료

[Visual Basic 응용 프로그램에서 DLL 함수 호출](calling-dll-functions-from-visual-basic-applications.md)
