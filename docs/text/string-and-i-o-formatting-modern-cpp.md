---
title: 문자열 및 I/O 서식 지정(최신 C++)
description: 최신 C++에서 사용할 수 있는 형식이 지정 된 문자열 i/o를 선택 합니다.
ms.date: 05/30/2019
ms.topic: conceptual
ms.assetid: 3954e8de-a59b-4175-89c9-4ee842ab89ed
ms.openlocfilehash: 7ea858a8a8126d3754783edee0dd3ea5409e5f73
ms.sourcegitcommit: 6ddfb8be5e5923a4d90a2c0f93f76a27ce7ac299
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/06/2019
ms.locfileid: "74898822"
---
# <a name="string-and-io-formatting-modern-c"></a>문자열 및 I/O 서식 지정(최신 C++)

C++[\<iostream >](../standard-library/iostream.md) 클래스, 함수 및 연산자는 형식이 지정 된 문자열 i/o를 지원 합니다. 예를 들어 다음 코드는 정수를 16 진수로 출력 하도록 `cout`를 설정 하는 방법을 보여 줍니다. 먼저 현재 상태를 다시 설정 하기 위해 현재 상태를 저장 합니다. 즉, `cout`에 형식 상태가 전달 되 면 변경 될 때까지 해당 방법이 유지 됩니다. 코드의 한 줄에만 적용 되는 것은 아닙니다.

```cpp
#include <iostream>
#include <iomanip>

using namespace std;

int main()
{
    ios state(nullptr);

    cout << "The answer in decimal is: " << 42 << endl;

    state.copyfmt(cout); // save current formatting
    cout << "In hex: 0x" // now load up a bunch of formatting modifiers
        << hex
        << uppercase
        << setw(8)
        << setfill('0')
        << 42            // the actual value we wanted to print out
        << endl;
    cout.copyfmt(state); // restore previous formatting
}
```

이 방법은 형식이 안전 하 고 확장 가능 하지만 복잡 하 고 자세한 정보를 표시 합니다.

## <a name="alternative-format-options"></a>대체 형식 옵션

대신, 비표준 인 경우에도 부스트 C++ 라이브러리의 `Boost.Format`를 사용할 수 있습니다. [부스트](https://www.boost.org/) 웹 사이트에서 모든 부스트 라이브러리를 다운로드할 수 있습니다.

`Boost.Format`의 이점은 다음과 같습니다.

- Safe: 형식이 안전 하 고, 너무 적거나 너무 많은 항목을 지정 하는 등 오류에 대 한 예외를 throw 합니다.

- 확장 가능: 스트림할 수 있는 모든 형식에 사용할 수 있습니다.

- 편리한: 표준 POSIX 및 비슷한 형식 문자열입니다.

`Boost.Format`는 C++ 안전 하 고 확장 가능한 [\<iostream >](../standard-library/iostream-programming.md) 기능을 기반으로 하지만 성능이 최적화 되지 않습니다. 성능 최적화가 필요한 경우 빠르고 쉽게 사용할 수 있는 C [printf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md) 및 [sprintf](../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)를 고려 합니다. 그러나 취약점 으로부터 확장 하거나 안전 하지 않습니다. (안전한 버전이 존재하지만 성능이 약간 저하됩니다. 자세한 내용은 [printf_s, _printf_s_l, wprintf_s, _wprintf_s_l](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md) 및 [sprintf_s,](../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md)_sprintf_s_l, swprintf_s)를 참조 하세요.

다음 코드는 Boost 서식 기능 중 일부를 보여 줍니다.

```cpp
    string s = str( format("%2% %2% %1%\n") % "world" % "hello" );
    // s contains "hello hello world"

    for( auto i = 0; i < names.size(); ++i )
        cout << format("%1% %2% %|40t|%3%\n") % first[i] % last[i] % tel[i];
    // Georges Benjamin Clemenceau             +33 (0) 123 456 789
    // Jean de Lattre de Tassigny              +33 (0) 987 654 321
```

## <a name="see-also"></a>참조

[다시 시작C++](../cpp/welcome-back-to-cpp-modern-cpp.md)<br/>
[C++ 언어 참조](../cpp/cpp-language-reference.md)<br/>
[C++ 표준 라이브러리](../standard-library/cpp-standard-library-reference.md)<br/>
[\<iostream>](../standard-library/iostream.md)<br/>
[\<limits>](../standard-library/limits.md)<br/>
[\<iomanip>](../standard-library/iomanip.md)
