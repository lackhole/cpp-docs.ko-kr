---
title: 인수 정의
ms.date: 11/04/2016
helpviewer_keywords:
- envp argument
- main function, arguments
- arguments [C++], for main function
- argv argument
- argc argument
ms.assetid: 6148cbf3-ebe8-44f2-b277-de4b723991c7
ms.openlocfilehash: 92e213b5accbf8fd5f48ac2111a169e585d82a1d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62184447"
---
# <a name="argument-definitions"></a>인수 정의

다음과 같은 프로토타입 인수를 사용하면

```cpp
int main( int argc, char* argv[], char* envp[]);
int wmain( int argc, wchar_t* argv[], wchar_t* envp[]);
```

인수를 편리하게 명령줄에서 구문 분석하고 원하는 환경 변수를 선택적으로 액세스할 수 있습니다. 인수 정의는 다음과 같습니다.

*argc*<br/>
*argv*에 따라오는 인수 갯수로 정수 형식입니다. *argc* 매개변수는 항상 1보다 크거나 같습니다.

*argv*<br/>
프로그램을 실행할 때 사용자가 입력한 명령줄 인수를 나타내는 null로 끝나는 문자열 배열입니다. 규칙에 따라 `argv[0]`은 프로그램이 호출되는 명령이고, `argv[1]`은 첫 번째 명령줄 인수이며 `argv[argc]`는 항상 NULL입니다. 명렬줄 처리를 없애려고 한다면 [명령줄 처리 사용자 지정](../cpp/customizing-cpp-command-line-processing.md)을 참조합니다.

첫 번째 명령줄 인수는 항상 `argv[1]`이고 마지막 인수는 `argv[argc-1]`입니다.

> [!NOTE]
> 규칙상 `argv[0]`은 프로그램이 호출되는 명령입니다. 그러나 [CreateProcess](/windows/desktop/api/libloaderapi/nf-libloaderapi-getmodulefilenamea)를 사용하여 프로세스를 생성할 때 첫번째와 두번째 인수(*lpApplicationName*과 *lpCommandLine*)를 모두 사용하는 경우 `argv[0]`은 실행 파일 이름이 아닐 수도 있습니다. [GetModuleFileName](/windows/desktop/api/libloaderapi/nf-libloaderapi-getmodulefilenamea)을 사용하여 실행 파일 이름과 해당 정규화된 경로를 검색합니다.

## <a name="microsoft-specific"></a>Microsoft 전용

*envp*<br/>
많은 UNIX 시스템에서 일반적인 확장인 *envp* 배열을 Microsoft C++에서 사용할 수 있습니다. 이것은 사용자 환경에 설정된 변수를 나타내는 문자열 배열입니다. 이 배열은 NULL 항목으로 종료됩니다. **char** (`char *envp[]`)에 대한 포인터의 배열이나 **char** (`char **envp`)에 대한 포인터의 포인터로 선언할 수 있습니다. 프로그램이 `main` 대신 `wmain`을 사용하면 **char** 대신 **wchar_t** 데이터 형식을 사용하세요. `main`이나 `wmain`에 전달된 환경 블록은 현재 환경의 "변경되지 않는" 복사본입니다. 나중에 `putenv`나 `_wputenv`를 호출하여 환경을 변경하면 현재 환경(`getenv`나 `_wgetenv`, `_environ`이나 `_wenviron` 변수가 반환)이 변경되지만 *envp*가 가리키는 블록은 변경되지 않습니다. 환경 처리를 하지 않기 위한 정보는 [명령줄 처리 사용자 지정](../cpp/customizing-cpp-command-line-processing.md)을 참조하세요. 이 인수는 C에서는 ANSI와 호환되지만 C++에서는 호환되지 않습니다.

**Microsoft 전용 종료**

## <a name="example"></a>예제

다음 예제에서는 *argc*, *argv* 및 *envp* 인수를 `main`에서 사용하는 방법을 보여줍니다.

```cpp
// argument_definitions.cpp
// compile with: /EHsc
#include <iostream>
#include <string.h>

using namespace std;
int main( int argc, char *argv[], char *envp[] ) {
    int iNumberLines = 0;    // Default is no line numbers.

    // If /n is passed to the .exe, display numbered listing
    // of environment variables.

    if ( (argc == 2) && _stricmp( argv[1], "/n" ) == 0 )
         iNumberLines = 1;

    // Walk through list of strings until a NULL is encountered.
    for( int i = 0; envp[i] != NULL; ++i ) {
        if( iNumberLines )
            cout << i << ": " << envp[i] << "\n";
    }
}
```

## <a name="see-also"></a>참고자료

[main: 프로그램 시작](../cpp/main-program-startup.md)
