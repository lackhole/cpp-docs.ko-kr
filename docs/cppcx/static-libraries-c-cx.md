---
title: 정적 라이브러리(C++/CX)
ms.date: 02/03/2017
ms.assetid: 7faf53c8-fa21-42cc-8246-d32533ef9dfa
ms.openlocfilehash: 188ba06518bf6cdd154b7d6bd61216ed1e4ffad3
ms.sourcegitcommit: 18d3b1e9cdb4fc3a76f7a650c31994bdbd2bde64
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/29/2019
ms.locfileid: "64877251"
---
# <a name="static-libraries-ccx"></a>정적 라이브러리(C++/CX)

유니버설 Windows 플랫폼 (UWP) 앱에 사용 되는 정적 라이브러리에서 ISO 표준을 포함할 수 있습니다 C++ STL 형식, 그리고 Windows 런타임 앱 플랫폼에서 제외 되지 않은 Win32 Api에 대 한 호출을 포함 하 여 코드입니다. 정적 라이브러리 Windows 런타임 구성 요소를 사용 하 고 특정 제한 사항이 Windows 런타임 구성 요소를 만들 수 있습니다.

## <a name="creating-static-libraries"></a>정적 라이브러리 만들기


새 프로젝트를 만들기 위한 지침은 Visual Studio 버전을 설치한 경우에 따라 달라 집니다. 버전 선택기를 올바른 버전으로 설정 왼쪽 위에 있는 있는지 확인 합니다.

::: moniker range="vs-2019"

### <a name="to-create-a-uwp-static-library-in-visual-studio-2019"></a>Visual Studio 2019에 UWP 정적 라이브러리를 만들려면

1. 메뉴 모음에서 **파일** > **새로 만들기** > **프로젝트** 열려는 합니다 **새 프로젝트를 만들** 대화 상자.

1. 설정 대화 상자 맨 **언어** 를 **C++** 설정 **플랫폼** 하 **Windows**, 설정 및 **프로젝트 형식을** 하 **UWP**합니다. 

1. 필터링된 된 프로젝트 형식 목록에서 선택 **정적 라이브러리 (유니버설 Windows- C++/CX)** 선택한 **다음**합니다. 다음 페이지에서 프로젝트에 이름을 지정 하 고 원하는 경우 프로젝트 위치를 지정 합니다.

1. 선택 된 **만들기** 프로젝트를 만들려면 단추입니다.

::: moniker-end

::: moniker range="<=vs-2017"

### <a name="to-create-a-uwp-static-library-in-visual-studio-2017-or-visual-studio-2015"></a>Visual Studio 2017 또는 Visual Studio 2015에서 UWP 정적 라이브러리를 만들려면

1. 메뉴 모음에서 **파일** > **새로 만들기** > **프로젝트**를 선택합니다. 아래 **시각적 C++**   >  **Windows 범용** 선택 **정적 라이브러리 (유니버설 Windows)**.

1. **솔루션 탐색기**에서 프로젝트의 바로 가기 메뉴를 열고 **속성**을 선택합니다. 에 **속성** 대화 상자의 합니다 **구성 속성** > **C /C++**  페이지에서 설정 **Windows 런타임 확장 사용**  하 **예 (/ZW)** 합니다.

::: moniker-end

컴파일러 오류 C3861 "식별자를 찾을 수 없습니다." UWP 앱에 대 한 제외 된 Win32 api를 호출 하는 경우 새 정적 라이브러리를 컴파일할 때 발생 Windows 런타임에 대 한 지원 되는 다른 방법을 찾아보려면, 참조 [UWP 앱에서 Windows Api에 대 한 대안](/uwp/win32-and-com/alternatives-to-windows-apis-uwp)합니다.

추가 하는 경우는 C++ 정적 라이브러리 프로젝트 UWP 앱 솔루션에 UWP 지원 속성 설정 되도록 라이브러리 프로젝트의 속성 설정을 업데이트 해야 할 수 있습니다 **Yes**합니다. 이 설정이 없으면 코드가 빌드되고 연결 되지만 오류가 Microsoft Store 대 한 응용 프로그램을 확인 하려고 할 때 발생 합니다. 정적 lib는 해당 lib를 사용하는 프로젝트와 동일한 컴파일러 설정을 사용하여 컴파일해야 합니다.

public `ref` 클래스, 공용 인터페이스 클래스 또는 공용 값 클래스를 만드는 정적 라이브러리를 사용하면 링커가 다음과 같은 경고를 발생시킵니다.

> **warning LNK4264:** 는 Windows 런타임 형식을 작성할 때는 권장 되지 않습니다 Windows 런타임 메타 데이터를 포함 하는 정적 라이브러리와 연결할 참고를 정적 라이브러리로; /ZW로 컴파일된 개체 파일을 보관 합니다.

정적 라이브러리가 라이브러리 자체의 외부에 사용 되는 Windows 런타임 구성 요소를 생성 하지 않는 경우에 경고를 안전 하 게 무시할 수 있습니다. 라이브러리에 정의된 구성 요소가 라이브러리에 사용되지 않는 경우 링커는 공용 메타 데이터에 형식 정보가 있는 경우에도 구현을 최적화할 수 있습니다. 즉, 정적 라이브러리의 공용 구성 요소는 컴파일되지만 런타임에 활성화되지 않습니다. 이러한 이유로 모든 Windows 런타임 구성 요소는 사용을 위한 다른 구성 요소나 앱에서 동적 연결 라이브러리 (DLL)에 구현 되어야 합니다.

## <a name="see-also"></a>참고자료

[스레딩 및 마샬링](../cppcx/threading-and-marshaling-c-cx.md)
