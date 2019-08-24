---
title: 스레드
ms.date: 05/07/2019
f1_keywords:
- thread_cpp
helpviewer_keywords:
- thread local storage (TLS)
- thread __declspec keyword
- TLS (thread local storage), compiler implementation
- __declspec keyword [C++], thread
ms.assetid: 667f2a77-6d1f-4b41-bee8-05e67324fab8
ms.openlocfilehash: 59a1af8a7eb73207f84ddf2194d5fe9e77d7d46a
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65221969"
---
# <a name="thread"></a>스레드

**Microsoft 전용**

합니다 **스레드** 확장된 저장소 클래스 한정자는 스레드 지역 변수를 선언 하는 데 사용 됩니다. 이식 가능한 C + + 11 안의 이상를 사용 합니다 [thread_local](../cpp/storage-classes-cpp.md#thread_local) 이식 가능한 코드에 대 한 저장소 클래스 지정자. Windows에서 `thread_local` 로 구현 됩니다 **__declspec (thread)** 합니다.

## <a name="syntax"></a>구문

> **__declspec( thread )** *declarator*

## <a name="remarks"></a>설명

TLS(스레드 로컬 스토리지)는 다중 스레드 프로세스의 각 스레드가 스레드 데이터를 위한 스토리지를 할당하는 메커니즘입니다. 표준 다중 스레드 프로그램에서 데이터는 지정된 프로세스의 모든 스레드에서 공유되지만 스레드 로컬 스토리지는 스레드별 데이터를 할당하기 위한 메커니즘입니다. 에 대 한 전체 설명은 스레드를 참조 하세요 [다중 스레딩](../parallel/multithreading-support-for-older-code-visual-cpp.md)합니다.

스레드 로컬 변수의 선언을 사용 해야 합니다 [확장 된 특성 구문은](../cpp/declspec.md) 하며 **__declspec** 키워드를 사용 합니다 **스레드** 키워드. 예를 들어, 다음 코드는 정수 스레드 로컬 변수를 선언한 다음 값으로 초기화합니다.

```cpp
__declspec( thread ) int tls_i = 1;
```

동적으로 로드 된 라이브러리의 스레드 로컬 변수를 사용할 때 제대로 초기화 하지 하는 스레드 지역 변수를 일으킬 수 있는 요소에 유의 해야 합니다.

1. 변수 (생성자)가 함수 호출으로 초기화 되 면이 함수 에서만 호출 되는 이진/DLL이 로드 프로세스에 발생 하는 스레드의 및 binary/DLL 로드 된 후에 시작 된 이러한 스레드에 대 한 합니다. DLL을 로드할 때 이미 실행 중인 다른 모든 스레드에 대 한 초기화 함수가 호출 되지 않습니다. 동적 초기화 없으면 DLL 프로세스에서 스레드가 시작 될 때 메시지는 가져옵니다를 되지 활발에 대 한 DllMain 호출 하지만 DLL에서 발생 합니다.

1. 상수 값을 사용 하 여 정적으로 초기화 되는 스레드 지역 변수는 일반적으로 모든 스레드에서 올바르게 초기화 됩니다. 그러나 2017 년 12 월이 알려진된 규칙 문제를 Microsoft C++ 컴파일러 수신 constexpr 변수 정적 초기화 하는 대신 동적 가능해 집니다.

   참고: 이러한 문제를 모두는 컴파일러의 업데이트 이후 수정 해야 합니다.

또한 스레드 로컬 개체 및 변수를 선언 하는 경우 다음이 지침을 준수 해야 합니다.

- 적용할 수 있습니다 합니다 **스레드** 클래스 및 데이터 선언과 정의에 특성 **스레드** 함수 선언 또는 정의에 사용할 수 없습니다.

- 지정할 수 있습니다 합니다 **스레드** 정적 저장 기간이 있는 데이터 항목에만 특성입니다. 여기에 전역 데이터 개체 (둘 다 **정적** 하 고 **extern**), 지역 정적 개체 및 클래스의 정적 데이터 멤버입니다. 자동 데이터 개체를 선언할 수 없습니다는 **스레드** 특성입니다.

- 사용 해야 합니다 **스레드** 선언 및 정의 동일한 파일 또는 별도 파일에서 발생 하는지 여부를 선언 및 스레드 로컬 개체의 정의 대 한 특성입니다.

- 사용할 수 없습니다는 **스레드** 특성은 형식 한정자로 합니다.

- 개체의 선언 하는 사용 하기 때문에 합니다 **스레드** 특성은 허용, 이러한 두 예제는 의미 체계가 같습니다:

    ```cpp
    // declspec_thread_2.cpp
    // compile with: /LD
    __declspec( thread ) class B {
    public:
       int data;
    } BObject;   // BObject declared thread local.

    class B2 {
    public:
       int data;
    };
    __declspec( thread ) B2 BObject2;   // BObject2 declared thread local.
    ```

- 표준 C에서는 비정적 범위의 개체에 한해 자신에 대한 참조를 포함하는 식으로 개체 또는 변수를 초기화할 수 있습니다. C++에서는 일반적으로 자신에 대한 참조를 포함하는 식으로 개체를 동적으로 초기화할 수 있지만 스레드 로컬 개체에 대해서는 이렇게 초기화할 수 없습니다. 예를 들어:

   ```cpp
   // declspec_thread_3.cpp
   // compile with: /LD
   #define Thread __declspec( thread )
   int j = j;   // Okay in C++; C error
   Thread int tls_i = sizeof( tls_i );   // Okay in C and C++
   ```

   한 **sizeof** 초기화 되는 개체를 포함 하는 식 자체에 대 한 참조를 구성 하지 않습니다 하 고 C에서 허용 됩니다 하 고 C++합니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[__declspec](../cpp/declspec.md)<br/>
[키워드](../cpp/keywords-cpp.md)<br/>
[TLS(스레드 로컬 저장소)](../parallel/thread-local-storage-tls.md)