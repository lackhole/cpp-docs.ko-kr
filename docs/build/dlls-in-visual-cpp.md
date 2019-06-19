---
title: Visual Studio에서 C/C++ DLL 빌드
ms.date: 05/06/2019
helpviewer_keywords:
- executable files [C++]
- dynamic linking [C++]
- linking [C++], dynamic vs. static
- DLLs [C++]
- DLLs [C++], about DLLs
ms.assetid: 5216bca4-51e2-466b-b221-0e3e776056f0
ms.openlocfilehash: 7f1c2b71a58c59bf0662aa4ffec53344ce657df0
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65220749"
---
# <a name="create-cc-dlls-in-visual-studio"></a>Visual Studio에서 C/C++ DLL 빌드

Windows, 동적 연결 라이브러리 (DLL)의 함수 및 리소스의 공유 라이브러리로 사용 되는 실행 파일의 종류입니다. 동적 연결 함수를 호출 하거나 별도 파일에 저장 된 리소스를 사용 하 여 실행 파일을 사용 하도록 설정 하는 운영 체제 기능입니다. 이러한 함수 및 리소스는 사용하는 실행 파일과 별도로 컴파일 및 배포할 수 있습니다. DLL을 독립 실행형 실행 파일입니다. 호출 하는 응용 프로그램의 컨텍스트에서 실행 됩니다. 응용 프로그램이 로드 될 때 운영 체제는 응용 프로그램의 메모리 공간에 DLL을 로드할 수 있습니다 (*암시적 링크*), 또는 런타임 시 주문형 (*명시적 링크*). DLL을 통해 실행 파일 간에 함수 및 리소스를 쉽게 공유할 수 있습니다. 즉, 여러 개의 응용 프로그램이 메모리에 있는 하나의 DLL 복사본 내용을 동시에 액세스할 수 있습니다.

## <a name="differences-between-dynamic-linking-and-static-linking"></a>동적 연결 및 정적 연결 간의 차이점

정적 연결 개체 코드를 정적 라이브러리에서 빌드될 때 사용 하는 실행 파일에 복사 합니다. 동적 링크를 찾아 데이터 항목이 나 함수를 포함 하는 DLL을 로드 하려면 런타임에 Windows에 필요한 정보만 포함 됩니다. DLL을 만들 때이 정보를 포함 하는 가져오기 라이브러리를 만들 수도 있습니다. DLL을 호출 하는 실행 파일을 빌드할 때 링커에서는 내보낸된 기호 가져오기 라이브러리 Windows 로더를 위해이 정보를 저장 합니다. 로더가 DLL을 로드 하는 경우 DLL는 응용 프로그램의 메모리 공간에 매핑됩니다. 특별 한 DLL의 함수 있으면 `DllMain`, DLL에 필요한 초기화를 수행 하기 위해 호출 됩니다.

<a name="differences-between-applications-and-dlls"></a>

## <a name="differences-between-applications-and-dlls"></a>응용 프로그램 및 Dll의 차이점

Dll 및 응용 프로그램은 모두 실행 모듈에도 여러 가지 방법으로 다릅니다. 최종 사용자에 게 가장 확실 한 차이점은 Dll 직접 실행할 수 있는 응용 프로그램 되지입니다. 시스템의 관점에서 응용 프로그램과 Dll 사이의 기본적인 차이점 두 가지:

- 응용 프로그램 DLL에는 하나의 인스턴스만 가질 수 있지만 시스템을 동시에 실행 자체의 여러 인스턴스가 있을 수 있습니다.

- 스택, 실행, 전역 메모리, 파일 핸들, 메시지 큐의 스레드 등을 소유할 수 있는 프로세스로 응용 프로그램을 로드할 수 있지만 DLL 수 없습니다.

<a name="advantages-of-using-dlls"></a>

## <a name="advantages-of-using-dlls"></a>Dll 사용의 장점

코드 및 리소스에 정적 링크 대신 동적 링크는 여러 가지 이점을 제공 합니다. DLL을 사용하면 메모리 공간을 절약하고 교환을 줄일 수 있습니다. 여러 응용 프로그램이 DLL의 단일 복사본을 사용할 수 있는 경우 디스크 공간 및 다운로드 대역폭을 절약할 수 있습니다. 별도로 DLL을 배포 및 업데이트할 수 있으므로 모든 코드를 다시 빌드하여 배포하지 않고 출시 후 지원 및 소프트웨어 업데이트를 제공할 수 있습니다. DLL은 다중 언어 프로그램을 지원하고 쉽게 응용 프로그램의 국가별 버전을 만들 수 있게 해주는 로캘별 리소스를 제공하는 편리한 방법입니다. 명시적 링크 검색 하 고 새로운 기능을 제공 하는 확장과 같은 런타임 시 Dll을 로드 하도록 응용 프로그램을 허용할 수 있습니다.

동적 링크는 다음과 같은 이점이 있습니다.

- 동적 링크 메모리에 저장 되 고 교환 줄어듭니다. 많은 프로세스 DLL 동시에 사용할 수, 메모리에서 DLL의 읽기 전용 부분 단일 복사본을 공유 합니다. 반면, 정적 링크 라이브러리를 사용 하 여 기본 제공 되는 모든 응용 프로그램에 Windows는 메모리에 로드 해야 하는 라이브러리 코드의 전체 복사본입니다.

- 디스크 공간 및 대역폭 저장 동적으로 연결 합니다. 대부분의 응용 프로그램에는 디스크에 DLL의 단일 복사본을 공유할 수 있습니다. 반면, 정적 연결 라이브러리를 사용 하 여 빌드된 각 응용 프로그램에 더 많은 공간이 사용 하며 더 많은 대역폭을 전송 하는 해당 실행 가능 이미지에 연결 하는 라이브러리 코드를 있습니다.

- 유지 관리, 보안 수정 하 고 업그레이드 보다 쉬울 수 있습니다. DLL에서 일반 함수를 사용 하는 응용 프로그램을 다음으로 함수 인수 및 반환 값을 변경 되지 버그 수정을 구현를 DLL에 업데이트를 배포 합니다. Dll 업데이트 될 때 사용 하는 응용 프로그램 않아도 컴파일하거나, 없으며 배포 되는 즉시 새 DLL 사용. 반면, 정적으로 연결 된 개체 코드에서 수정 하려면 다시 연결을 사용 하는 모든 응용 프로그램을 다시 배포 해야 합니다.

- 출시 후 지원을 제공 하기 위해 Dll을 사용할 수 있습니다. 예를 들어, 디스플레이 드라이버 DLL 응용 프로그램을 출시할 때 사용할 수 없었던 표시를 지원 하도록 수정할 수 있습니다. 명시적 연결을 사용 하 여 응용 프로그램 확장 Dll 로드할 수 하 고 새 기능을 다시 작성 하거나 다시 배포 하지 않고 앱을 추가할 수 있습니다.

- 동적 연결 하면 보다 쉽게 다양 한 프로그래밍 언어로 작성 된 응용 프로그램을 지원할 수 있습니다. 다른 프로그래밍 언어로 작성 된 프로그램으로 프로그램 함수의 호출 규칙에 따라 동일한 DLL 함수를 호출할 수 있습니다. 프로그램 및 DLL 함수를 다음과 같이 호환 되어야 합니다: 함수 인수가 스택으로 푸시 하도록 하는, 함수 또는 응용 프로그램 스택을 정리 인지 여부 등 인수 순서 레지스터에 전달 합니다.

- 동적 링크 MFC 라이브러리 클래스를 확장 하는 메커니즘을 제공 합니다. 기존 MFC 클래스에서 클래스를 파생 시킬 수 있으며 MFC 응용 프로그램에서 사용 하기 위한 MFC 확장 DLL에에서 배치할 수 있습니다.

- 응용 프로그램의 국가별 버전 생성 등의 쉽게 동적으로 연결 합니다. 로캘별 리소스 DLL에 넣어 훨씬 쉽게 응용 프로그램의 국가별 버전을 만들 수는 있습니다. 응용 프로그램의 여러 지역화 된 버전을 전달 하는 대신 별도 리소스 DLL에에서 문자열 및 각 언어에 대 한 이미지를 배치할 수 있습니다 하 고 응용 프로그램 런타임 시 해당 로캘에 대 한 적절 한 리소스를 로드할 수 있습니다.

잠재적인 단점은 Dll을 사용 하는 응용 프로그램은 자체 포함 된;는 배포 또는 설치의 일부로 직접 확인 해야 하는 별도 DLL 모듈의 존재 여부에 따라 다릅니다.

## <a name="more-information-on-how-to-create-and-use-dlls"></a>만들기 및 Dll을 사용 하는 방법에 대 한 자세한 내용

C를 만드는 방법에 대 한 자세한 정보를 제공 하는 다음 항목 /C++ Visual Studio에서 Dll입니다.

[연습: 동적 연결 라이브러리 만들기 및 사용(C++)](walkthrough-creating-and-using-a-dynamic-link-library-cpp.md)<br/>
Visual Studio를 사용하여 DLL을 만들고 사용하는 방법에 대해 설명합니다.

[DLL의 종류](kinds-of-dlls.md)<br/>
빌드할 수 있는 다양한 종류의 DLL에 대한 정보를 제공합니다.

[DLL에 대 한 질문과 대답](dll-frequently-asked-questions.md)<br/>
DLL 관련 질문과 대답을 제공합니다.

[DLL에 실행 파일 링크](linking-an-executable-to-a-dll.md)<br/>
DLL에 대한 명시적 및 암시적 링크에 대해 설명합니다.

[DLL 초기화](run-time-library-behavior.md#initializing-a-dll)<br/>
DLL이 로드 될 때 실행 되어야 하는 DLL 초기화 코드를 설명 합니다.

[DLL 및 Visual C++ 런타임 라이브러리 동작](run-time-library-behavior.md)<br/>
런타임 라이브러리가 DLL 시동을 순서대로 수행하는 과정을 설명합니다.

[LoadLibrary 및 AfxLoadLibrary](loadlibrary-and-afxloadlibrary.md)<br/>
사용 하 여 설명 **LoadLibrary** 및 `AfxLoadLibrary` 런타임 시 DLL에 명시적으로 연결 합니다.

[GetProcAddress](getprocaddress.md)<br/>
사용 하 여 설명 **GetProcAddress** DLL에서 내보내기 함수의 주소를 가져옵니다.

[FreeLibrary 및 AfxFreeLibrary](freelibrary-and-afxfreelibrary.md)<br/>
사용 하 여 설명 **FreeLibrary** 고 `AfxFreeLibrary` DLL 모듈이 더 이상 필요 없는 경우.

[동적 연결 라이브러리 순서](/windows/desktop/Dlls/dynamic-link-library-search-order)<br/>
시스템에서 DLL을 찾기 위해 Windows 운영 체제가 사용하는 검색 경로에 대해 설명합니다.

[동적으로 MFC에 링크된 기본 MFC DLL의 모듈 상태](module-states-of-a-regular-dll-dynamically-linked-to-mfc.md)<br/>
일반 동적으로 MFC에 링크 된 MFC DLL의 모듈 상태를 설명 합니다.

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
Windows 동적 연결 라이브러리의 일부로 MFC 라이브러리를 사용할 수 있는 기본 MFC Dll에 설명 합니다.

[MFC의 DLL 버전](../mfc/tn033-dll-version-of-mfc.md)<br/>
어떻게 MFCxx.dll를 사용할 수 있습니다 및 MFCxxD.dll (여기서 x는 MFC 버전 번호) 공유 동적 연결 라이브러리 MFC 응용 프로그램 및 MFC 확장명 Dll 사용 하 여 설명 합니다.
