---
title: 문자열 및 I-O 서식(모던 C++)
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 3954e8de-a59b-4175-89c9-4ee842ab89ed
ms.openlocfilehash: c051a7d70042456d30bee0ebb2b362c5d05b8e37
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62266922"
---
# <a name="string-and-io-formatting-modern-c"></a>문자열 및 I/O 서식 지정(모던 C++)

C++ [iostreams](../standard-library/iostream.md)는 서식 문자열 I/O를 지원합니다. 예를 들어 상태 서식은 cout에 전달되면 코드 한 줄 정도가 아니라 대규모로 변경될 때까지 해당 방식으로 유지됩니다. 다음 코드에서는 현재 상태를 저장하고 나중에 다시 설정하여 정수가 16진수로 출력되게 서식을 지정하도록 cout를 설정하는 방법을 보여 줍니다.

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

이 방법은 여러 측면에서 매우 번거로울 수 있습니다. 대신 비표준이지만 Boost C++ 라이브러리에서 Boost.Format을 사용할 수도 있습니다. [Boost](http://www.boost.org/) 웹 사이트에서 Boost 라이브러리를 다운로드할 수 있습니다.

Boost.Format의 몇 가지 이점은 다음과 같습니다.

- 안전: 형식에 안전한 코드이며, 너무 적거나 너무 많은 항목을 지정할 경우 오류에 대한 예외를 throw합니다.

- 확장 가능: 스트리밍할 수 있는 모든 형식에 사용할 수 있습니다.

- 간편함: 표준 Posix와 유사한 형식 문자열입니다.

Boost.Format이 안전하고 확장 가능한 C++ [iostreams](../standard-library/iostream-programming.md)에 내장되어 있지만 성능은 최적화되어 있지 않습니다. 성능 최적화가 필요하면 빠르고 사용하기 쉬운 C [printf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md) 및 [sprintf](../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)를 고려하십시오. 그러나 확장할 수 없으며 취약성으로부터 안전하지 않습니다. (안전한 버전이 존재하지만 성능이 약간 저하됩니다. 자세한 내용은 [printf_s, _printf_s_l, wprintf_s, _wprintf_s_l](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md) 및 [sprintf_s, _sprintf_s_l, swprintf_s, _swprintf_s_l](../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md))를 참조하십시오.

다음 코드는 Boost 서식 기능 중 일부를 보여 줍니다.

```cpp
    string s = str( format("%2% %2% %1%\n") % "world" % "hello" );
    // s contains "hello hello world"

    for( auto i = 0; i < names.size(); ++i )
        cout << format("%1% %2% %|40t|%3%\n") % first[i] % last[i] % tel[i];
    // Georges Benjamin Clemenceau             +33 (0) 123 456 789
    // Jean de Lattre de Tassigny              +33 (0) 987 654 321
```

## <a name="see-also"></a>참고 항목

[C++의 진화(모던 C++)](../cpp/welcome-back-to-cpp-modern-cpp.md)<br/>
[C++ 언어 참조](../cpp/cpp-language-reference.md)<br/>
[C++ 표준 라이브러리](../standard-library/cpp-standard-library-reference.md)<br/>
[\<iostream>](../standard-library/iostream.md)<br/>
[\<limits>](../standard-library/limits.md)<br/>
[\<iomanip>](../standard-library/iomanip.md)
