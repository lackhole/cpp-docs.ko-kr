---
title: 일반 규칙 및 제한 사항
ms.date: 11/04/2016
ms.assetid: 6c48902d-4259-4761-95d4-e421d69aa050
ms.openlocfilehash: 931ae04ef47262f15d037a2b5eeb35bd01a8419d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62153777"
---
# <a name="general-rules-and-limitations"></a>일반 규칙 및 제한 사항

## <a name="microsoft-specific"></a>Microsoft 전용

- 함수를 선언 하거나 하지 않고 개체를 **dllimport** 하거나 **dllexport** 특성, 함수 또는 개체가 DLL 인터페이스의 일부가 되지 않습니다. 따라서 해당 모듈 또는 같은 프로그램의 다른 모듈에 함수 또는 개체의 정의가 있어야 합니다. 함수 또는 개체가 DLL 인터페이스 부분을 만들려면 함수 또는 다른 모듈에는 개체의 정의 선언 해야 합니다 **dllexport**합니다. 그렇게 하지 않으면 링커 오류가 생성됩니다.

   함수를 선언 하거나 개체를 **dllexport** 특성을 해당 정의가 같은 프로그램의 일부 모듈에 나타나야 합니다. 그렇게 하지 않으면 링커 오류가 생성됩니다.

- 프로그램의 모듈 하나에 모두 포함 하는 경우 **dllimport** 하 고 **dllexport** 동일 함수 또는 개체에 대 한 선언을 합니다 **dllexport** 특성 우선 통해 합니다 **dllimport** 특성입니다. 그러나 이 경우 컴파일러 경고가 생성됩니다. 예를 들어:

    ```cpp
    __declspec( dllimport ) int i;
    __declspec( dllexport ) int i;   // Warning; inconsistent;
                                     // dllexport takes precedence.
    ```

- C++을 전역적으로 선언 또는 정적 로컬 데이터 포인터를 초기화할 수 있습니다 또는 사용 하 여 선언 된 데이터 개체의 주소를 **dllimport** C에서 오류를 생성 하는 특성 또한 사용 하 여 선언 된 함수의 주소로 정적 로컬 함수 포인터를 초기화할 수 있습니다 합니다 **dllimport** 특성입니다. C에서는 이러한 대입으로 인해 포인터가 함수의 주소 대신 DLL 가져오기 썽크(함수로 제어를 전송하는 코드 스텁)의 주소로 설정됩니다. C++에서는 포인터가 함수의 주소로 설정됩니다. 예를 들어:

    ```cpp
    __declspec( dllimport ) void func1( void );
    __declspec( dllimport ) int i;

    int *pi = &i;                             // Error in C
    static void ( *pf )( void ) = &func1;     // Address of thunk in C,
                                              // function in C++

    void func2()
    {
       static int *pi = &i;                  // Error in C
       static void ( *pf )( void ) = &func1; // Address of thunk in C,
                                             // function in C++
    }
    ```

   그러나 포함 하는 프로그램 때문에 합니다 **dllexport** 개체의 선언에서 특성은 프로그램의 어딘가에 해당 개체에 대 한 정의 제공 해야, 전역 또는 로컬 정적 함수 포인터를 초기화할 수 있습니다 주소를 **dllexport** 함수입니다. 마찬가지로,의 주소로 전역 또는 로컬 정적 데이터 포인터를 초기화할 수 있습니다는 **dllexport** 데이터 개체입니다. 예를 들어, 다음 코드는 C 또는 C++에서 오류를 발생시키지 않습니다.

    ```cpp
    __declspec( dllexport ) void func1( void );
    __declspec( dllexport ) int i;

    int *pi = &i;                              // Okay
    static void ( *pf )( void ) = &func1;      // Okay

    void func2()
    {
        static int *pi = &i;                   // Okay
        static void ( *pf )( void ) = &func1;  // Okay
    }
    ```

- 적용 하는 경우 **dllexport** 으로 표시 되지 않는 기본 클래스를 포함 하는 일반 클래스 **dllexport**, 컴파일러가 C4275를 생성 합니다.

   컴파일러는 기본 클래스가 클래스 템플릿의 특수화인 경우 동일한 경고를 생성합니다. 이 해결 하려면 사용 하 여 기본 클래스 표시 **dllexport**합니다. 클래스 템플릿의 특수화의 문제점은 어디에 배치할지를 **__declspec (dllexport)**; 클래스 템플릿은 표시할 수 없습니다. 대신 명시적으로 클래스 템플릿을 인스턴스화하고 사용 하 여이 명시적 인스턴스화를 표시 **dllexport**합니다. 예를 들어:

    ```cpp
    template class __declspec(dllexport) B<int>;
    class __declspec(dllexport) D : public B<int> {
    // ...
    ```

   템플릿 인수가 파생 클래스일 경우 이 해결 방법은 실패합니다. 예를 들어:

    ```cpp
    class __declspec(dllexport) D : public B<D> {
    // ...
    ```

   컴파일러의 의미 체계 변경 템플릿 사용 하 여 일반적인 패턴 이므로 **dllexport** 시점과 하나 이상의 기본 클래스가 클래스 템플릿의 특수화는 하나 이상의 기본 클래스가 있는 클래스에 적용 되는 경우 . 이 경우 컴파일러가 암시적으로 적용 됩니다 **dllexport** 클래스 템플릿의 특수화에 있습니다. 다음을 수행 하 고 경고를 가져올 수 있습니다.

    ```cpp
    class __declspec(dllexport) D : public B<D> {
    // ...
    ```

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[dllexport, dllimport](../cpp/dllexport-dllimport.md)