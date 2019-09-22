---
title: 문자열 및 I/O 서식 지정(모던 C++)
description: Modern의 서식된 문자열 I/O 사용할 수 있는 선택 C++입니다.
ms.date: 05/30/2019
ms.topic: conceptual
ms.assetid: 3954e8de-a59b-4175-89c9-4ee842ab89ed
ms.openlocfilehash: e22c745798109a2dbef82297c45256593823f806
ms.sourcegitcommit: 28eae422049ac3381c6b1206664455dbb56cbfb6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/31/2019
ms.locfileid: "66450506"
---
# <a name="string-and-io-formatting-modern-c"></a>문자열 및 I/O 서식 지정(모던 C++)

C++[ \<iostream >](../standard-library/iostream.md) 클래스, 함수 및 연산자는 서식된 문자열 I/O를 지원합니다. 예를들어 다음 코드는 정수를 16진수로 출력하도록 `cout`을 설정하는 방법을 보여줍니다. 첫째, 포맷 상태가 `cout`에 전달되면 변경 될 때까지 그대로 유지되므로 나중에 다시 설정하기 위해 현재상태를 저장합니다. 한 줄의 코드에만 적용되는 것은 아닙니다.

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

이 방법은 형식이 안전하고 확장 가능하지만 복잡 하고 자세한 정보 표시도 됩니다.

## <a name="alternative-format-options"></a>서식 옵션의 대안

표준 방법은 아니지만, 대안으로 Boost C++ 라이브러리의 `Boost.Format`을 사용할 수 있습니다. Boost 라이브러리는 [Boost](https://www.boost.org/) 웹사이트에서 다운로드할 수 있습니다.

`Boost.Format`의 장점은 다음과 같습니다.

- 안전: 형식에 안전한 코드이며, 오류 발생시 예외를 통하여 처리합니다. 예를 들어 너무 적거나 많은 항목을 전달할 경우 입니다.

- 확장 가능: 스트림(stream) 할 수 있는 모든 형식에 사용할 수 있습니다.

- 간편함: 표준 Posix와 유사한 형식 문자열입니다.

하지만 `Boost.Format`은 안전하고 확장가능한 C++ [ \<iostream >](../standard-library/iostream-programming.md) 기능을 기반으로 하고 있지만 성능 최적화가 되지는 않았습니다. 성능 최적화가 필요한 경우 빠르고 사용하기 쉬운 C [printf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)나 [sprintf](../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)를 고려하십시오. 그러나 취약점으로 인하여 확장가능하거나 안전하지 않습니다. (안전한 버전이 존재하지만 성능이 약간 저하됩니다. 자세한 내용은 [printf_s, _printf_s_l, wprintf_s, _wprintf_s_l](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md) 및 [sprintf_s, _sprintf_s_l, swprintf_s, _swprintf_s_l](../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md))를 참조하세요.

다음 코드는 Boost 서식화 기능 중 일부를 보여 줍니다.

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
