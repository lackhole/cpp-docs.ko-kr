---
title: C++ 명령줄 인수 구문 분석
ms.date: 11/04/2016
helpviewer_keywords:
- quotation marks, command-line arguments
- double quotation marks
- command line [C++], parsing
- parsing, command-line arguments
- startup code, parsing command-line arguments
ms.assetid: e634e733-ac2f-4298-abe2-7e9288c94951
ms.openlocfilehash: 53873fa9340253ab5e8459eb442385641246f930
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62396121"
---
# <a name="parsing-c-command-line-arguments"></a>C++ 명령줄 인수 구문 분석

**Microsoft 전용**

Microsoft C/C++ 시작 코드는 운영 체제 명령줄에서 입력된 인수를 해석할 때 다음 규칙을 사용합니다.

- 인수는 공백이나 탭과 같은 흰 공백으로 구분합니다.

- 캐럿 문자(^)는 이스케이프 문자나 구분 기호로 인식되지 않습니다. 해당 문자는 프로그램에서 `argv` 배열로 전달되기 전에 운영 체제의 명령줄 구문 분석기에서 모두 처리됩니다.

- 큰 따옴표로 묶은 문자열("*string*")은 공백의 포함과 상관 없이 단일 인수로 해석됩니다. 따옴표로 묶은 문자열은 인수에 포함될 수 있습니다.

- 백슬래시 다음의 큰따옴표(\\")는 리터럴 큰따옴표 문자(")로 해석됩니다.

- 백슬래시는 큰따옴표 바로 앞에 있지 않으면 리터럴로 해석됩니다.

- 짝수 개의 백슬래시 뒤에 큰 따옴표가 오는 경우 각 쌍의 백슬래시에 대해 하나의 백슬래시가 `argv` 배열에 배치되고 큰 따옴표는 문자열 구분 기호로 해석됩니다.

- 홀수 개의 백슬래시 뒤에 큰 따옴표가 있으면 각 쌍의 백슬래시에 대해 하나의 백슬래시가 `argv` 배열에 배치되고 큰 따옴표는 나머지 백슬래시에 의해 "닫히지 않게"되어 리터럴 이중 인용 부호(")를 `argv`에 넣어야 합니다.

## <a name="example"></a>예제

다음 프로그램은 명령줄 인수가 전달되는 방법을 보여줍니다.

```cpp
// command_line_arguments.cpp
// compile with: /EHsc
#include <iostream>

using namespace std;
int main( int argc,      // Number of strings in array argv
          char *argv[],   // Array of command-line argument strings
          char *envp[] )  // Array of environment variable strings
{
    int count;

    // Display each command-line argument.
    cout << "\nCommand-line arguments:\n";
    for( count = 0; count < argc; count++ )
         cout << "  argv[" << count << "]   "
                << argv[count] << "\n";
}
```

다음 표에서는 앞의 목록에 있는 규칙을 보여주는 예제와 예상 출력을 보여줍니다.

### <a name="results-of-parsing-command-lines"></a>명령줄 구문 분석 결과

|명령줄 입력|argv[1]|argv[2]|argv[3]|
|-------------------------|---------------|---------------|---------------|
|`"abc" d e`|`abc`|`d`|`e`|
|`a\\b d"e f"g h`|`a\\b`|`de fg`|`h`|
|`a\\\"b c d`|`a\"b`|`c`|`d`|
|`a\\\\"b c" d e`|`a\\b c`|`d`|`e`|

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[main: 프로그램 시작](../cpp/main-program-startup.md)
