---
title: 프로젝트 만들기(ATL 자습서, 1부)
ms.custom: get-started-article
ms.date: 05/06/2019
ms.assetid: f6b727d1-390a-4b27-b82f-daadcd9fc059
ms.openlocfilehash: 292faf1769baa2e1c3fc6e52ba6df065cf08766e
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65221410"
---
# <a name="creating-the-project-atl-tutorial-part-1"></a>프로젝트 만들기(ATL 자습서, 1부)

이 자습서에서는 다각형을 표시하는 ActiveX 개체를 생성하는 비-어트리뷰트 ATL 프로젝트를 단계별로 안내합니다. 생성된 개체는 사용자가 다각형을 구성하는 변의 수를 바꾸고 화면을 새로 고치는 코드가 가능한 옵션을 포함합니다.

> [!NOTE]
> 일반적으로 ATL 및 MFC는 Visual Studio의 Express 버전에서는 지원 되지 않습니다.

> [!NOTE]
> 이 자습서에서는 다각형 샘플과 동일한 소스 코드를 만듭니다. 소스 코드를 수동으로 입력하지 않을 경우 [다각형 샘플 요약](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/Controls/Polygon)에서 다운로드 할 수 있습니다. 자습서를 통해 작업 하거나 자신의 프로젝트에 오류가 있는지 확인하는데 다각형 소스 코드를 참조할 수 있습니다.
> 컴파일하기 위해 stdafx.h 파일의 수정이 필요합니다.
> ```
> #ifndef WINVER
> #define WINVER 0x0400
> #endif
> ```
> 다음 문자열로 바꾸세요.
> ```
> #ifndef WINVER
> #define WINVER 0x0500
> #define _WIN32_WINNT 0x0500
> #endif
> ```
> 컴파일러는 여전히 올바르게 종료하지 않는 `regsvr32`에 대해 문제가 발생하지만 컨트롤의 DLL을 빌드하여 사용할 수 있도록 해야합니다.

### <a name="to-create-the-initial-atl-project-using-the-atl-project-wizard"></a>ATL 프로젝트 마법사를 사용하여 초기 ATL 프로젝트를 만들려면

1. Visual Studio 2017 및 이전 버전: **파일** > **새** > **프로젝트**합니다. 엽니다는 **시각적 C++**  탭을 선택한 **MFC/ATL**. 그리고 **ATL 프로젝트**를 선택합니다.

   In Visual Studio 2019: 선택할 **파일** > **새로 만들기** > **프로젝트**검색 상자에 "atl"를 입력 하 고 선택 **ATL 프로젝트**합니다.

1. *Polygon*을 프로젝트 이름으로 입력합니다.

    소스 코드의 위치는 일반적으로 기본적으로 \Users\\\<사용자 이름 > \source\repos, 및 새 폴더를 자동으로 생성 됩니다.

1. **확인**을 클릭하면 **ATL 프로젝트** 마법사가 열립니다.  

1. **응용 프로그램 설정**을 클릭하면 사용할 수 있는 옵션이 표시됩니다.

1. 컨트롤을 만들 때 컨트롤은 in-process 서버여야 합니다. **응용 프로그램 종류**는 DLL로 그대로 합니다.

1. 다른 옵션의 기본값을 그대로 사용하고 **확인**을 클릭합니다.

**ATL 프로젝트 마법사**는 여러 개의 파일을 생성하여 프로젝트를 만듭니다. **솔루션 탐색기**에서 `Polygon` 개체를 확장하여 이러한 파일들을 볼 수 있습니다. 파일은 다음과 같습니다. 

|파일|설명|
|----------|-----------------|
|Polygon.cpp|`DllMain`, `DllCanUnloadNow`, `DllGetClassObject`, `DllRegisterServer` 및 `DllUnregisterServer`의 구현이 포함되어 있습니다. 프로젝트의 ATL 개체의 목록인 개체 맵의 포함 됩니다. 이 옵션은 처음에 비어 있습니다.|
|Polygon.def|이 모듈 정의 파일은 링커에게 DLL에서 필요로 하는 내보내기에 대한 정보를 제공합니다.|
|마우스 오른쪽 단추로 Polygon.idl|인터페이스 정의 언어 파일입니다. 개체에 특정 인터페이스를 설명합니다.|
|Polygon.rgs|이 레지스트리 스크립트를 사용하면 프로그램의 DLL 등록을 위한 정보가 있습니다.|
|Polygon.rc|버전 정보 및 프로젝트 이름이 문자열로 포함된 리소스 파일입니다.|
|Resource.h|리소스 파일용 헤더 파일.|
|Polygonps.def|이 모듈 정의 파일은 경계를 넘어 호출하는 프록시와 스텁 코드에서 필요한 내보내기 정보를 링커에 제공합니다.|
|stdafx.cpp|`#include`되는 ATL의 헤더 파일입니다.|
|stdafx.h|`#include`되는 ATL의 구현 파일입니다.|

1. **솔루션 탐색기**에서 마우스 오른쪽 단추로 `Polygon` 프로젝트를 클릭합니다.

1. 바로 가기 메뉴의 **속성**을 클릭합니다.

1. **링커**를 클릭합니다. **Pre-UserRedirection** 옵션을 **예**로 변경합니다.

1. **확인**을 클릭합니다.

다음 단계에서는 프로젝트에 컨트롤을 추가합니다.

[2 단계로 이동 합니다.](../atl/adding-a-control-atl-tutorial-part-2.md)

## <a name="see-also"></a>참고자료

[자습서](../atl/active-template-library-atl-tutorial.md)
