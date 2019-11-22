---
title: 문자열 및 I/O 서식 지정(모던 C++)
description: 최신 C++에서 사용할 수 있는 형식이 지정 된 문자열 i/o를 선택 합니다.
ms.date: 05/30/2019
ms.topic: conceptual
ms.assetid: 3954e8de-a59b-4175-89c9-4ee842ab89ed
ms.openlocfilehash: facb0b62cc1e92ed09a9ba729d766e5db7404282
ms.sourcegitcommit: 069e3833bd821e7d64f5c98d0ea41fc0c5d22e53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2019
ms.locfileid: "74308188"
---
# <a name="string-and-io-formatting-modern-c"></a>문자열 및 I/O 서식 지정(모던 C++)

C++[ \<iostream >](../standard-library/iostream.md) 클래스, 함수 및 연산자는 서식이 지정된 문자열 I/O를 지원합니다. 예를 들어 다음 코드는 정수를 16진수로 출력하도록 `cout`을 설정하는 방법을 보여줍니다. 첫째, 서식 상태가 `cout`에 전달되면 변경될 때까지 그대로 유지되므로 나중에 다시 설정하기 위해 현재 상태를 저장합니다. 한 줄의 코드에만 적용되는 것은 아닙니다.

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

이 방법은 형식이 안전하고 확장 가능하지만 복잡하고 자세한 정보 표시도 됩니다.

## <a name="alternative-format-options"></a>서식 옵션의 대안

표준 방법은 아니지만, 대안으로 Boost C++ 라이브러리의 `Boost.Format`을 사용할 수 있습니다. Boost 라이브러리는 [Boost](https://www.boost.org/) 웹사이트에서 다운로드할 수 있습니다.

`Boost.Format`의 장점은 다음과 같습니다.

- Safe: 형식이 안전 하 고, 너무 적거나 너무 많은 항목을 지정 하는 등 오류에 대 한 예외를 throw 합니다.

- 확장 가능: 스트리밍할 수 있는 모든 형식에 대해 작동 합니다.

- 편리한: 표준 Posix 및 비슷한 형식 문자열입니다.

`Boost.Format`은 안전하고 확장 가능한 C++ [ \<iostream >](../standard-library/iostream-programming.md) 기능을 기반으로 하고 있지만 성능 최적화가 되지는 않았습니다. 성능 최적화가 필요한 경우 빠르고 사용하기 쉬운 C [printf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)나 [sprintf](../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)를 고려하십시오. 그러나 취약점으로 인하여 확장 가능하거나 안전하지 않습니다. 그러나 취약점 으로부터 확장 하거나 안전 하지 않습니다. (안전한 버전이 존재하지만 성능이 약간 저하됩니다. 자세한 내용은 [printf_s, _printf_s_l, wprintf_s, _wprintf_s_l](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md) 및 [sprintf_s, _sprintf_s_l, swprintf_s, _swprintf_s_l](../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md))를 참조하세요.

다음 코드는 Boost 서식 지정 기능 중 일부를 보여 줍니다.

```cpp
    string s = str( format("%2% %2% %1%\n") % "world" % "hello" );
    // s contains "hello hello world"

    for( auto i = 0; i < names.size(); ++i )
        cout << format("%1% %2% %|40t|%3%\n") % first[i] % last[i] % tel[i];
    // Georges Benjamin Clemenceau             +33 (0) 123 456 789
    // Jean de Lattre de Tassigny              +33 (0) 987 654 321
```

## <a name="see-also"></a>참고 항목

[다시 시작C++](../cpp/welcome-back-to-cpp-modern-cpp.md)<br/>
[C++ 언어 참조](../cpp/cpp-language-reference.md)<br/>
[C++ 표준 라이브러리](../standard-library/cpp-standard-library-reference.md)<br/>
[\<iostream>](../standard-library/iostream.md)<br/>
[\<limits>](../standard-library/limits.md)<br/>
[\<iomanip>](../standard-library/iomanip.md)
