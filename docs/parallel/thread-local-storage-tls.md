---
title: TLS
ms.date: 11/04/2016
helpviewer_keywords:
- multithreading [C++], Thread Local Storage
- TLS [C++]
- threading [C++], Thread Local Storage
- storing thread-specific data
- thread attribute
- Thread Local Storage [C++]
ms.assetid: 80801907-d792-45ca-b776-df0cf2e9f197
ms.openlocfilehash: 5c7bf2ae7cb5bfe71be9a1d72147e97c894064b3
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2019
ms.locfileid: "65448900"
---
# <a name="thread-local-storage-tls"></a>TLS

TLS(스레드 로컬 저장소)는 지정된 다중 스레드 프로세스의 각 스레드에서 스레드별 데이터를 저장하는 위치를 할당하는 방법입니다. 동적으로 바인딩 (런타임) 스레드별 데이터 TLS API를 통해 지원 됩니다 ([TlsAlloc](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-tlsalloc)합니다.  Win32 및 Microsoft C++ 컴파일러 지원 (로드 타임) 스레드별 데이터는 기존 API 구현 외에도 정적으로 바인딩할 이제 합니다.

##  <a name="_core_compiler_implementation_for_tls"></a> TLS의 컴파일러 구현

**C++11:**  `thread_local` 저장소 클래스 지정자는 클래스 멤버 및 개체에 대 한 스레드 로컬 저장소를 지정 하는 방법이 권장된 됩니다. 자세한 내용은 [저장소 클래스 (C++)](../cpp/storage-classes-cpp.md)합니다.

Visual C++ 에서는 다음 Microsoft 전용 특성인 [스레드](../cpp/thread.md)확장된 저장소 클래스 한정자로 합니다. 사용 된 **__declspec** 키워드를 선언 하는 **스레드** 변수. 예를 들어, 다음 코드는 정수 스레드 로컬 변수를 선언한 다음 값으로 초기화합니다.

```
__declspec( thread ) int tls_i = 1;
```

## <a name="rules-and-limitations"></a>규칙 및 제한 사항

정적으로 바인딩된 스레드 로컬 개체 및 변수를 선언할 때는 다음 지침을 준수해야 합니다. 다음이 지침에 모두 적용 [스레드](../cpp/thread.md)도 대부분 [thread_local](../cpp/storage-classes-cpp.md):

- 합니다 **스레드** 특성 클래스 및 데이터 선언과 정의에 적용할 수 있습니다. 함수 선언 또는 정의에는 사용할 수 없습니다. 예를 들어, 다음 코드는 컴파일러 오류를 생성합니다.

    ```
    __declspec( thread )void func();     // This will generate an error.
    ```

- 합니다 **스레드** 한정자를 사용 하 여 데이터 항목에만 지정할 수 있습니다 **정적** 범위입니다. 여기에 전역 데이터 개체 (둘 다 **정적** 하 고 **extern**), 지역 정적 개체 및 정적 데이터 멤버의 C++ 클래스. 자동 데이터 개체를 사용 하 여 선언할 수 없습니다는 **스레드** 특성입니다. 다음 코드는 컴파일러 오류를 생성합니다.

    ```
    void func1()
    {
        __declspec( thread )int tls_i;            // This will generate an error.
    }

    int func2(__declspec( thread )int tls_i )    // This will generate an error.
    {
        return tls_i;
    }
    ```

- 선언 및 정의 스레드 로컬 개체가 모두 지정 해야 합니다 **스레드** 특성입니다. 예를 들어, 다음 코드는 오류를 생성합니다.

    ```
    #define Thread  __declspec( thread )
    extern int tls_i;        // This will generate an error, since the
    int __declspec( thread )tls_i;        // declaration and definition differ.
    ```

- 합니다 **스레드** 특성은 형식 한정자로 사용할 수 없습니다. 예를 들어, 다음 코드는 컴파일러 오류를 생성합니다.

    ```
    char __declspec( thread ) *ch;        // Error
    ```

- 때문에 선언의 C++ 사용 하는 개체를 **스레드** 특성은 허용, 다음 두 예제는 의미 체계가 같습니다.

    ```
    __declspec( thread ) class B
    {
    // Code
    } BObject;  // OK--BObject is declared thread local.

    class B
    {
    // Code
    };
    __declspec( thread ) B BObject;  // OK--BObject is declared thread local.
    ```

- 스레드 로컬 개체의 주소는 상수로 간주되지 않으므로 이 주소를 포함하는 모든 식은 상수 식으로 간주되지 않습니다. 이는 표준 C의 경우 스레드 로컬 변수의 주소를 개체나 포인터에 대한 이니셜라이저로 사용하지 못하게 하는 효과가 있습니다. 예를 들어 다음 코드는 C 컴파일러에서 오류로 플래그 지정됩니다.

    ```
    __declspec( thread )int tls_i;
    int *p = &tls_i;       //This will generate an error in C.
    ```

   이 제한은 C++에서는 적용되지 않습니다. C++에서는 모든 개체의 동적 초기화가 허용되기 때문에, 스레드 로컬 변수의 주소를 사용하는 식을 사용하여 개체를 초기화할 수 있습니다. 이것은 마치 스레드 로컬 개체 생성과 같습니다. 예를 들어 앞에 나온 코드는 C++ 소스 파일로 컴파일하면 오류를 생성하지 않습니다. 스레드 지역 변수의 주소는 이 주소가 사용된 스레드가 존재하는 동안에만 유효합니다.

- 표준 C에서는 비정적 범위의 개체에 한해 자신에 대한 참조를 포함하는 식으로 개체 또는 변수를 초기화할 수 있습니다. C++에서는 일반적으로 자신에 대한 참조를 포함하는 식으로 개체를 동적으로 초기화할 수 있지만 스레드 로컬 개체에 대해서는 이런 종류의 초기화가 허용되지 않습니다. 예를 들어:

    ```
    __declspec( thread )int tls_i = tls_i;                // Error in C and C++
    int j = j;                               // OK in C++, error in C
    __declspec( thread )int tls_i = sizeof( tls_i )       // Legal in C and C++
    ```

   초기화되는 개체를 포함하는 `sizeof` 식은 자신에 대한 참조를 나타내지 않으므로 C와 C++에서 모두 허용됩니다.

   C++에서는 향후 스레드 로컬 저장소 기능이 향상될 수 있으므로 이런 방식으로 스레드 데이터를 동적으로 초기화할 수 없습니다.

- Windows Vista 이전의 Windows 운영 체제에서 `__declspec`(스레드)에 몇 가지 제한 사항이 있습니다. DLL에서 데이터 또는 개체를 `__declspec`( thread )로 선언하는 경우 동적으로 로드하면 보호 오류가 발생할 수 있습니다. DLL을 사용 하 여 로드 한 후 [LoadLibrary](/windows/desktop/api/libloaderapi/nf-libloaderapi-loadlibrarya), 코드를 참조할 때마다 시스템 오류가 발생 합니다 `__declspec`(thread) 데이터. 런타임에 스레드에 대한 전역 변수 공간이 할당되기 때문에, 이 공간의 크기는 응용 프로그램의 요구 사항과 정적으로 연결되는 모든 DLL의 요구 사항을 계산하여 결정됩니다. `LoadLibrary`를 사용할 때는 `__declspec`( thread )로 스레드 로컬 변수를 선언할 수 있도록 이 공간을 확장할 수 없습니다. 와 같은 TLS Api를 사용 하 여 [TlsAlloc](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-tlsalloc)를 사용 하 여 DLL을 로드 될 수 하는 경우 TLS에 할당할 DLL의 `LoadLibrary`합니다.

## <a name="see-also"></a>참고자료

[C 및 Win32를 사용한 다중 스레딩](multithreading-with-c-and-win32.md)
