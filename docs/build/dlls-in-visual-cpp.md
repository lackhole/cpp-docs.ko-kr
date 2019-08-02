---
title: Visual Studio에서 C/C++ DLL 빌드
ms.date: 07/18/2019
helpviewer_keywords:
- executable files [C++]
- dynamic linking [C++]
- linking [C++], dynamic vs. static
- DLLs [C++]
- DLLs [C++], about DLLs
ms.assetid: 5216bca4-51e2-466b-b221-0e3e776056f0
ms.openlocfilehash: 9f5b34fda8a429f8e55631e1e0125ed6f79d5bae
ms.sourcegitcommit: 0867d648e0955ebad7260b5fbebfd6cd4d58f3c7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/19/2019
ms.locfileid: "68341076"
---
# <a name="create-cc-dlls-in-visual-studio"></a>Visual Studio에서 C/C++ DLL 빌드

Windows에서 DLL (동적 연결 라이브러리)은 함수 및 리소스의 공유 라이브러리 역할을 하는 실행 파일의 일종입니다. 동적 링크는 실행 파일이 함수를 호출 하거나 별도 파일에 저장 된 리소스를 사용할 수 있도록 하는 운영 체제 기능입니다. 이러한 함수 및 리소스는 사용하는 실행 파일과 별도로 컴파일 및 배포할 수 있습니다. DLL은 독립 실행형 실행 파일이 아닙니다. 호출 하는 응용 프로그램의 컨텍스트에서 실행 됩니다. 응용 프로그램이 로드 될 때 (*암시적 링크*) 또는 런타임에 요청 시 (*명시적 링크*) 운영 체제에서 DLL을 응용 프로그램의 메모리 공간에 로드할 수 있습니다. DLL을 통해 실행 파일 간에 함수 및 리소스를 쉽게 공유할 수 있습니다. 즉, 여러 개의 응용 프로그램이 메모리에 있는 하나의 DLL 복사본 내용을 동시에 액세스할 수 있습니다.

## <a name="differences-between-dynamic-linking-and-static-linking"></a>동적 링크와 정적 링크의 차이점

정적 링크는 정적 라이브러리의 모든 개체 코드를 빌드할 때이를 사용 하는 실행 파일에 복사 합니다. 동적 링크에는 런타임에 데이터 항목이 나 함수를 포함 하는 DLL을 찾아서 로드 하는 데 필요한 정보만 포함 됩니다. DLL을 만들 때이 정보를 포함 하는 가져오기 라이브러리도 만듭니다. DLL을 호출 하는 실행 파일을 빌드하면 링커에서 가져오기 라이브러리의 내보낸 기호를 사용 하 여 Windows 로더에 대 한 정보를 저장 합니다. 로더가 DLL을 로드 하면 DLL이 응용 프로그램의 메모리 공간에 매핑됩니다. Dll의 특수 함수 `DllMain`(있는 경우)를 호출 하 여 dll에 필요한 초기화를 수행 합니다.

<a name="differences-between-applications-and-dlls"></a>

## <a name="differences-between-applications-and-dlls"></a>응용 프로그램과 Dll의 차이점

Dll과 응용 프로그램은 모두 실행 가능한 모듈 이지만 여러 가지 면에서 차이가 있습니다. 최종 사용자에 게 가장 명백한 차이점은 Dll은 직접 실행할 수 있는 응용 프로그램이 아니라는 것입니다. 시스템의 관점에서 볼 때 응용 프로그램과 Dll 간에는 다음과 같은 두 가지 기본적인 차이점이 있습니다.

- 응용 프로그램은 시스템에서 동시에 실행 되는 인스턴스를 여러 개 가질 수 있지만 DLL은 하나의 인스턴스만 가질 수 있습니다.

- 스택, 실행 스레드, 전역 메모리, 파일 핸들 및 메시지 큐와 같은 작업을 소유할 수 있는 프로세스로 응용 프로그램을 로드할 수 있지만 DLL은 사용할 수 없습니다.

<a name="advantages-of-using-dlls"></a>

## <a name="advantages-of-using-dlls"></a>Dll 사용의 이점

코드 및 리소스에 대 한 동적 링크는 정적 링크에 비해 여러 가지 이점을 제공 합니다.

- 동적 링크는 메모리를 절약 하 고 스와핑을 감소 시킵니다. 많은 프로세스에서 DLL을 동시에 사용 하 여 메모리에서 DLL의 읽기 전용 부분에 대 한 단일 복사본을 공유할 수 있습니다. 반면 정적으로 연결 된 라이브러리를 사용 하 여 빌드된 모든 응용 프로그램에는 Windows에서 메모리로 로드 해야 하는 라이브러리 코드의 전체 복사본이 있습니다.

- 동적 링크는 디스크 공간 및 대역폭을 절약 합니다. 많은 응용 프로그램은 디스크에서 DLL의 단일 복사본을 공유할 수 있습니다. 반면, 정적 링크 라이브러리를 사용 하 여 빌드된 각 응용 프로그램에는 더 많은 디스크 공간을 사용 하 고 전송 하는 데 더 많은 대역폭을 사용 하는 실행 가능 이미지에 연결 된 라이브러리 코드가 있습니다.

- 유지 관리, 보안 픽스 및 업그레이드는 더 쉬울 수 있습니다. 응용 프로그램에서 DLL의 일반 함수를 사용 하는 경우 함수 인수 및 반환 값이 변경 되지 않는 한 버그 수정을 구현 하 고 DLL에 업데이트를 배포할 수 있습니다. Dll이 업데이트 되 면이를 사용 하는 응용 프로그램을 다시 컴파일하거나 다시 연결할 필요가 없으며 배포 되는 즉시 새 DLL을 사용 하 게 됩니다. 이와 대조적으로 정적으로 연결 된 개체 코드에서 수정한 내용은이를 사용 하는 모든 응용 프로그램을 다시 연결 하 고 다시 배포 해야 합니다.

- Ddl을 사용 하 여 출시 후 지원을 제공할 수 있습니다. 예를 들어, 응용 프로그램을 배송할 때 사용할 수 없는 디스플레이를 지원 하도록 디스플레이 드라이버 DLL을 수정할 수 있습니다.

- 명시적 링크를 사용 하 여 런타임 시 DLL을 검색 하 고 로드할 수 있습니다. 예를 들어 응용 프로그램 확장을 사용 하 여 응용 프로그램을 다시 빌드하거나 재배포 하지 않고도 앱에 새 기능을 추가

- 동적 링크를 사용 하면 다양 한 프로그래밍 언어로 작성 된 응용 프로그램을 쉽게 지원할 수 있습니다. 다른 프로그래밍 언어로 작성 된 프로그램은 프로그램이 함수의 호출 규칙을 따르는 동안 동일한 DLL 함수를 호출할 수 있습니다. 프로그램 및 DLL 함수는 함수에서 해당 인수를 스택에 푸시하는 순서, 함수 또는 응용 프로그램이 스택 정리를 담당 하는지 여부 및 인수가 있는지 여부와 같은 방식으로 호환 되어야 합니다. 레지스터에 전달 되었습니다.

- 동적 링크는 MFC 라이브러리 클래스를 확장 하는 메커니즘을 제공 합니다. 기존 MFC 클래스에서 클래스를 파생 시키고 MFC 응용 프로그램에서 사용할 수 있도록 MFC 확장명 DLL에 배치할 수 있습니다.

- 동적 링크를 사용 하면 응용 프로그램의 국가별 버전을 보다 쉽게 만들 수 있습니다. Dll은 로캘별 리소스를 제공 하는 편리한 방법으로,이를 통해 응용 프로그램의 국가별 버전을 훨씬 쉽게 만들 수 있습니다. 지역화 된 여러 버전의 응용 프로그램을 제공 하는 대신 각 언어의 문자열과 이미지를 별도의 리소스 DLL에 배치 하면 응용 프로그램에서 런타임에 해당 로캘에 대 한 적절 한 리소스를 로드할 수 있습니다.

Dll을 사용 하면 응용 프로그램이 자체 포함 되지 않기 때문에 발생할 수 있는 단점이 있습니다. 이는 설치의 일부로 배포 하거나 직접 확인 해야 하는 별도의 DLL 모듈이 있는지 여부에 따라 달라 집니다.

## <a name="more-information-on-how-to-create-and-use-dlls"></a>Dll을 만들고 사용 하는 방법에 대 한 자세한 정보

다음 항목은 Visual Studio에서 C/C++ dll을 만드는 방법에 대 한 자세한 정보를 제공 합니다.

[연습: 동적 연결 라이브러리 만들기 및 사용(C++)](walkthrough-creating-and-using-a-dynamic-link-library-cpp.md)<br/>
Visual Studio를 사용하여 DLL을 만들고 사용하는 방법에 대해 설명합니다.

[DLL의 종류](kinds-of-dlls.md)<br/>
빌드할 수 있는 다양한 종류의 DLL에 대한 정보를 제공합니다.

[DLL에 대 한 질문과 대답](dll-frequently-asked-questions.md)<br/>
DLL 관련 질문과 대답을 제공합니다.

[DLL에 실행 파일 링크](linking-an-executable-to-a-dll.md)<br/>
DLL에 대한 명시적 및 암시적 링크에 대해 설명합니다.

[DLL 초기화](run-time-library-behavior.md#initializing-a-dll)<br/>
DLL이 로드 될 때 실행 되어야 하는 DLL 초기화 코드에 대해 설명 합니다.

[DLL 및 Visual C++ 런타임 라이브러리 동작](run-time-library-behavior.md)<br/>
런타임 라이브러리가 DLL 시동을 순서대로 수행하는 과정을 설명합니다.

[LoadLibrary 및 AfxLoadLibrary](loadlibrary-and-afxloadlibrary.md)<br/>
**LoadLibrary** 및 `AfxLoadLibrary` 를 사용 하 여 런타임에 DLL에 명시적으로 연결 하는 방법을 설명 합니다.

[GetProcAddress](getprocaddress.md)<br/>
**GetProcAddress** 를 사용 하 여 DLL의 내보낸 함수 주소를 가져오는 방법을 설명 합니다.

[FreeLibrary 및 AfxFreeLibrary](freelibrary-and-afxfreelibrary.md)<br/>
**Freelibrary** 를 사용 하 `AfxFreeLibrary` 는 방법과 DLL 모듈이 더 이상 필요 하지 않은 경우에 대해 설명 합니다.

[동적 연결 라이브러리 검색 순서](/windows/desktop/Dlls/dynamic-link-library-search-order)<br/>
시스템에서 DLL을 찾기 위해 Windows 운영 체제가 사용하는 검색 경로에 대해 설명합니다.

[동적으로 MFC에 링크된 기본 MFC DLL의 모듈 상태](module-states-of-a-regular-dll-dynamically-linked-to-mfc.md)<br/>
MFC에 동적으로 연결 되는 기본 MFC DLL의 모듈 상태에 대해 설명 합니다.

[MFC 확장명 DLL](extension-dlls-overview.md)<br/>
기존 MFC 라이브러리 클래스에서 파생된 다시 사용할 수 있는 클래스를 구현하는 DLL에 대해 설명합니다.

[리소스 전용 DLL 만들기](creating-a-resource-only-dll.md)<br/>
아이콘, 비트맵, 문자열 및 대화 상자 등의 리소스만 포함된 리소스 전용 DLL에 대해 설명합니다.

[MFC 애플리케이션의 지역화된 리소스: 위성 DLL](localized-resources-in-mfc-applications-satellite-dlls.md)<br/>
여러 언어로 지역화된 응용 프로그램을 만드는 데 도움이 되는 위성 DLL에 대한 향상된 지원을 제공합니다.

[가져오기 및 내보내기](importing-and-exporting.md)<br/>
DLL에서 함수를 내보내거나 응용 프로그램으로 공용 기호를 가져오는 방법에 대해 설명합니다.

[액티브 기술 및 DLL](active-technology-and-dlls.md)<br/>
DLL 내에서 개체 서버가 구현될 수 있도록 합니다.

[DLL의 자동화](automation-in-a-dll.md)<br/>
MFC DLL 마법사 지원의 자동화 옵션이 무엇인지 설명합니다.

[MFC DLL의 명명 규칙](../mfc/mfc-library-versions.md#mfc-static-library-naming-conventions)<br/>
MFC에 포함된 DLL 및 라이브러리가 구조적 명명 규칙을 지키는 방법에 대해 설명합니다.

[Visual Basic 응용 프로그램에서 DLL 함수 호출](calling-dll-functions-from-visual-basic-applications.md)<br/>
Visual Basic 응용 프로그램에서 DLL 함수를 호출하는 방법에 대해 설명합니다.

## <a name="related-sections"></a>관련 단원

[DLL의 일부로 MFC 사용](../mfc/tn011-using-mfc-as-part-of-a-dll.md)<br/>
Windows 동적 연결 라이브러리의 일부로 MFC 라이브러리를 사용할 수 있도록 하는 일반적인 MFC Dll에 대해 설명 합니다.

[MFC의 DLL 버전](../mfc/tn033-dll-version-of-mfc.md)<br/>
MFC 응용 프로그램 및 MFC 확장명 Dll을 사용 하 여 Mfcxx.dll 및 Mfcxxd.dll (여기서 x는 MFC 버전 번호) 공유 동적 연결 라이브러리를 사용 하는 방법을 설명 합니다.
