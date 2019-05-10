---
title: DLL에 실행 파일 링크
ms.date: 11/04/2016
helpviewer_keywords:
- run time [C++], linking
- dynamic load linking [C++]
- linking [C++], DLLs
- DLLs [C++], linking
- implicit linking [C++]
- explicit linking [C++]
- executable files [C++], linking to DLLs
- loading DLLs [C++]
ms.assetid: 7592e276-dd6e-4a74-90c8-e1ee35598ea3
ms.openlocfilehash: b0a3a0acd9fe0270416745696079e382c35ec32d
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65220646"
---
# <a name="link-an-executable-to-a-dll"></a>DLL에 실행 파일 링크

실행 파일에 연결 (또는 로드) DLL의 두 가지 방법 중 하나:

- *암시적 링크*사용 하 여 실행 파일이 로드 될 때 운영 체제 DLL을 로드 하는 위치입니다. 클라이언트 실행 파일 처럼 함수를 정적으로 연결 되었으며 실행 파일 내에 포함 된 DLL의 내보내기 함수를 호출 합니다. 암시적 링크는 라고도 *정적 로드* 하거나 *로드 타임 동적 링크*합니다.

- *명시적 링크*운영 체제에서 런타임 시 주문형 DLL을 로드 하는 위치입니다. 명시적 연결 하 여 DLL을 사용 하는 실행 파일이 함수를 호출 하려면 명시적으로 로드 하 고 DLL을 언로드하지 DLL에서 내보낸 함수에 액세스 해야 합니다. 정적으로 연결 된 라이브러리의 함수에 대 한 호출을 달리 클라이언트 실행 파일은 함수 포인터를 통해 DLL에서 내보낸된 함수를 호출 해야 합니다. 명시적 링크는 라고도 *동적 부하* 하거나 *런타임 동적 링크*합니다.

실행 파일 연결 방법 중 하나를 사용 하 여 동일한 DLL에 연결할 수 있습니다. 이러한 메서드는 함께 사용할 수 없습니다; 또한 하나의 실행 DLL에 암시적으로 연결 하 고 명시적으로 여기에 연결할 다른 합니다.

<a name="determining-which-linking-method-to-use"></a>

## <a name="link-an-executable-to-a-dll"></a>DLL에 실행 파일 링크

암시적 링크 또는 명시적 링크를 사용할 것인지는 응용 프로그램에 대 한 확인 해야 하는 아키텍처 의사 결정입니다. 각 메서드에 장단점이 있습니다.

### <a name="implicit-linking"></a>암시적 링크

암시적 링크는 응용 프로그램의 코드에서 내보낸된 DLL 함수를 호출할 때 발생 합니다. 호출 실행에 대 한 소스 코드 처리가 컴파일되거나 어셈블된 경우 DLL 함수 호출을 개체 코드에서 외부 함수 참조를 생성 합니다. 이 외부 참조를 해결 하려면 응용 프로그램은 DLL 작성자가 제공 하는 가져오기 라이브러리 (.lib 파일)를 사용 하 여 연결 해야 합니다.

가져오기 라이브러리만 DLL을 로드 하 고 DLL에서 함수에 대 한 호출을 구현 하는 코드를 포함 합니다. 가져오기 라이브러리에 외부 함수를 DLL에서 해당 함수에 대 한 코드는 사실이 링커에 전달 합니다. Dll에 대 한 외부 참조를 해결 하려면 링커 시스템 프로세스를 시작 하는 경우 DLL 코드를 찾을 수 있는 위치를 알려 주는 실행 파일에 정보 단순히 추가 합니다.

시스템 동적으로 연결 된 참조를 포함 하는 프로그램을 시작할 때 사용 하 여 정보를 프로그램의 실행 파일에 필요한 Dll을 찾습니다. DLL을 찾을 수 없습니다. 시스템 프로세스를 종료 하 고 오류를 보고 하는 대화 상자가 표시 됩니다. 그렇지 않으면 시스템은 프로세스의 주소 공간에 DLL 모듈을 매핑합니다.

와 같은 한 Dll에 진입점 함수가 초기화 및 종료 코드에 대 한 경우 `DllMain`, 운영 체제 함수를 호출 합니다. 진입점 함수에 전달 된 매개 변수 중 하나이 프로세스에 연결 된 DLL을 지정 하는 코드를 지정 합니다. 진입점 함수가 TRUE를 반환 하지 않는 경우 시스템 프로세스를 종료 하 고 오류를 보고 합니다.

마지막으로 시스템 DLL 함수에 대 한 시작 주소를 제공 하는 프로세스의 실행 코드를 수정 합니다.

나머지 프로그램의 코드와 같은 프로세스 시작 되 고 필요한 경우에 메모리에 로드 될 때 DLL 코드 프로세스의 주소 공간에 매핑됩니다. 결과적으로 `PRELOAD` 및 `LOADONCALL` .def 파일을 더 이상 이전 버전의 Windows에서 로드 하는 컨트롤을 사용 하는 코드 특성의 의미가 없습니다.

### <a name="explicit-linking"></a>명시적 링크

대부분의 응용 프로그램 사용에 대 한 쉬운 링크 방법 이기 때문에 암시적 연결을 사용 합니다. 그러나 명시적 링크의 경우 필요한 경우가 있습니다. 명시적 링크를 사용 하는 몇 가지 일반적인 이유는 다음과 같습니다.

- 응용 프로그램 실행된 시간까지 로드 된 DLL의 이름을 알 수 없습니다. 예를 들어, 응용 프로그램 시작 시 구성 파일에서 DLL 이름과 내보낸된 함수를 가져올 수 있습니다.

- 암시적 링크를 사용 하는 프로세스는 프로세스를 시작할 때 DLL이 없으면 운영 체제에서 종료 됩니다. 명시적 링크를 사용 하는 프로세스가이 상황에서 종료 되지 않았습니다 하 고 오류 로부터 복구 하려고 할 수 있습니다. 예를 들어 프로세스 오류의 사용자에 게 알림 및 DLL에 다른 경로 지정 하는 사용자 수 없습니다.

- 암시적 링크를 사용 하는 프로세스 또한 종료 되 면 할 링크 되는 Dll 중 하나는 `DllMain` 함수에 오류가 발생 합니다. 명시적 링크를 사용 하는 프로세스는이 상황에서 종료 되지 않았습니다.

- 암시적으로 여러 Dll에 링크 하는 응용 프로그램 시작 Windows 응용 프로그램 로드 될 때 모든 Dll을 로드 하기 때문에 속도가 느릴 수 있습니다. 시작 성능 향상을 위해 응용 프로그램 로드 및 대기 직후 필요한 다른 Dll에 명시적으로 연결 하는 데 필요한 때까지 해당 Dll에만 암시적으로 연결할 수 있습니다.

- 명시적 링크 가져오기 라이브러리를 사용 하 여 응용 프로그램을 연결할 필요가 없습니다. DLL의 변경 내용을 변경 하려면 내보내기 서 수를 발생 하는 경우 명시적 링크를 사용 하는 응용 프로그램 호출 하는 경우 다시 연결 않아도 `GetProcAddress` 암시적 연결을 사용 하는 응용 프로그램에 다시 연결 해야 하는 반면 함수와 서 수 값이 아닌 이름을 사용 하는 새 가져오기 라이브러리입니다.

알아야 할 명시적 링크의 두 가지 위험은 다음과 같습니다.

- DLL에는 `DllMain` 진입점 함수, 운영 체제 함수를 호출한 스레드 컨텍스트에서 호출 `LoadLibrary`합니다. DLL은 이미 연결 된 경우 프로세스는 이전 호출으로 인해 진입점 함수가 호출 되지 않습니다 `LoadLibrary` 에 대 한 해당 호출이 했습니다는 `FreeLibrary` 함수입니다. 명시적 연결 문제가 발생할 수 있습니다 DLL을 사용 하는 경우는 `DllMain` 스레드는 이미 존재 하기 때문에 프로세스의 각 스레드에 대 한 초기화를 수행 하는 함수 때 `LoadLibrary` (또는 `AfxLoadLibrary`) 라고 초기화 되지 않습니다.

- DLL에 정적 범위 데이터를 선언 하면 `__declspec(thread)`를 명시적으로 연결 하는 경우 보호 오류가 발생할 수 있습니다. 호출 하 여 DLL이 로드 된 후 `LoadLibrary`, 코드는이 데이터를 참조할 때마다 보호 오류가 발생 합니다. (정적 범위 데이터는 전역 및 로컬 정적 항목을 포함 합니다.) 따라서 DLL을 만들면 스레드 로컬 저장소를 사용 하지 않도록 하거나 동적으로 DLL을 로드 하는 잠재적인 문제에 대 한 DLL 사용자에 게 알림. 자세한 내용은 [동적 연결 라이브러리 (Windows SDK)에 스레드 로컬 저장소를 사용 하 여](/windows/desktop/Dlls/using-thread-local-storage-in-a-dynamic-link-library)입니다.

<a name="linking-implicitly"></a>

## <a name="link-an-executable-to-a-dll"></a>DLL에 실행 파일 링크

암시적 연결 하 여 DLL을 사용 하려면 클라이언트 실행 파일은 DLL의 공급자에서 이러한 파일을 구해야 합니다.

- 하나 이상의 헤더 파일 (.h) 내보낸된 데이터를 함수 선언을 포함 하는 및/또는 C++ DLL의 클래스입니다. 클래스, 함수 및 DLL에서 내보낸 데이터 모두 표시 되어야 합니다 `__declspec(dllimport)` 헤더 파일에 있습니다. 자세한 내용은 [dllexport, dllimport](../cpp/dllexport-dllimport.md)합니다.

- 실행 파일에 연결 하는 가져오기 라이브러리입니다. 링커는 DLL을 빌드할 때 가져오기 라이브러리를 만듭니다. 자세한 내용은 참조 하세요. [합니다. LIB 파일](reference/dot-lib-files-as-linker-input.md)합니다.

- 실제 DLL 파일입니다.

암시적 연결 하 여 DLL을 사용 하려면 실행 데이터, 함수를 선언 하는 헤더 파일을 포함 해야 합니다 또는 C++ 클래스는 내보낸된 데이터, 함수 및 클래스에 대 한 호출을 포함 하는 각 소스 파일에서 해당 DLL에서 내보내기. 코딩 관점에서 다른 함수 호출 처럼 내보낸된 함수를 호출 하는 합니다.

호출 실행 파일을 빌드하려면 가져오기 라이브러리를 사용 하 여 연결 해야 합니다. 를 외부 메이크파일을 사용 하거나 시스템을 구축 하는 경우에 다른 개체 (.obj) 파일을 나열할 수 있는 가져오기 라이브러리 또는 라이브러리는 연결 하는 파일 이름을 지정 합니다.

운영 체제 호출 실행 파일을 로드할 때 DLL 파일을 찾을 수 있어야 합니다. 즉, 응용 프로그램을 배포 하거나 응용 프로그램을 설치 하는 경우 DLL의 존재를 확인 해야 합니다.

<a name="linking-explicitly"></a>

## <a name="how-to-link-explicitly-to-a-dll"></a>DLL에 명시적으로 연결 하는 방법

명시적 연결 하 여 DLL을 사용 하려면 응용 프로그램에 함수를 명시적으로 런타임 시 DLL을 로드 하려면 호출 해야 합니다. 응용 프로그램 DLL에 명시적으로 링크를 하려면 다음을 해야 합니다.

- 호출 [LoadLibrary](loadlibrary-and-afxloadlibrary.md), `LoadLibraryEx`, 또는 비슷한 기능을 DLL을 로드 하 고 모듈 핸들을 얻습니다.

- 호출 [GetProcAddress](getprocaddress.md) 내보낸 응용 프로그램을 호출 하는 함수를 각각에 대 한 함수 포인터를 가져오려고 합니다. 응용 프로그램에 대 한 포인터를 통해 DLL 함수를 호출 하므로 가져오기 라이브러리를 사용 하 여 연결 하지 않아도 되므로 컴파일러가 외부 참조를 생성 하지 않습니다. 그러나 해야는 `typedef` 또는 `using` 문을 호출 하는 내보낸된 함수를 호출 시그니처를 정의 하는 합니다.

- 호출 [FreeLibrary](freelibrary-and-afxfreelibrary.md) DLL을 사용 하 여 완료 합니다.

예를 들어이 샘플 함수 호출 `LoadLibrary` "MyDLL" 라는 DLL을 로드 하기 위해 호출 `GetProcAddress` "DLLFunc1" 라는 함수에 대 한 포인터를 가져오려면 함수를 호출 하 고 결과 저장 한 다음 호출 `FreeLibrary` DLL을 언로드할 수입니다.

```C
#include "windows.h"

typedef HRESULT (CALLBACK* LPFNDLLFUNC1)(DWORD,UINT*);

HRESULT LoadAndCallSomeFunction(DWORD dwParam1, UINT * puParam2)
{
    HINSTANCE hDLL;               // Handle to DLL
    LPFNDLLFUNC1 lpfnDllFunc1;    // Function pointer
    HRESULT hrReturnVal;

    hDLL = LoadLibrary("MyDLL");
    if (NULL != hDLL)
    {
        lpfnDllFunc1 = (LPFNDLLFUNC1)GetProcAddress(hDLL, "DLLFunc1");
        if (NULL != lpfnDllFunc1)
        {
            // call the function
            hrReturnVal = lpfnDllFunc1(dwParam1, puParam2);
        }
        else
        {
            // report the error
            hrReturnVal = ERROR_DELAY_LOAD_FAILED;
        }
        FreeLibrary(hDLL);
    }
    else
    {
        hrReturnVal = ERROR_DELAY_LOAD_FAILED;
    }
    return hrReturnVal;
}
```

와 달리이 예제에서는 대부분의 경우에서 호출 해야 `LoadLibrary` 고 `FreeLibrary` DLL의 여러 함수를 호출 하거나 DLL을 호출 하려는 경우에 특히 지정 된 DLL에 대 한 응용 프로그램에서 한 번만 반복 해 서 작동 합니다.

## <a name="what-do-you-want-to-know-more-about"></a>추가 정보

- [가져오기 라이브러리 및 내보내기 파일을 사용한 작업](reference/working-with-import-libraries-and-export-files.md)

- [동적 연결 라이브러리 순서](/windows/desktop/Dlls/dynamic-link-library-search-order)

## <a name="see-also"></a>참고자료

[C를 만들기 /C++ Visual Studio에서 Dll](dlls-in-visual-cpp.md)
