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

C++[ \<iostream >](../standard-library/iostream.md) 클래스, 함수 및 연산자 서식된 문자열 I/O를 지원 합니다. 다음 코드를 설정 하는 방법을 표시 하는 예를 들어 `cout` 16 진수로 출력 정수 형식을 지정 합니다. 형식 상태는에 전달 하는 한 번 때문에 나중에 다시 설정 하려면 현재 상태를 저장 하는 먼저 `cout`를 이런 방식으로 변경 될 때까지 유지 합니다. 코드 한 줄으로 바로 적용 되지 않습니다.

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

이 방법은 형식이 안전 하 고 확장 가능 하지만 복잡 하 고 자세한 정보 표시도 됩니다.

## <a name="alternative-format-options"></a>다른 서식 옵션

사용할 수 있습니다 `Boost.Format` Boost에서 C++ 라이브러리에도 표준이 아닙니다. [Boost](https://www.boost.org/) 웹 사이트에서 Boost 라이브러리를 다운로드할 수 있습니다.

몇 가지 이점은 `Boost.Format` 됩니다.

- 안전: 형식에 안전한 코드이며, 형식이 안전한 오류에 대 한 예외 사양 너무 적거나 너무 많은 항목의 예를 들어를 throw 합니다.

- 확장 가능: 스트리밍할 수 있는 모든 형식에 사용할 수 있습니다.

- 간편함: 표준 Posix와 유사한 형식 문자열입니다.

하지만 `Boost.Format` 기반으로 하는 C++ [ \<iostream >](../standard-library/iostream-programming.md) 시설에 안전 하 고 확장할 수는 없는 성능 최적화. 성능 최적화가 필요하면 빠르고 사용하기 쉬운 C [printf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md) 및 [sprintf](../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)를 고려하십시오. 그러나 확장 가능한 또는 취약성 으로부터 안전 하 게 되지 않습니다. (안전한 버전이 존재하지만 성능이 약간 저하됩니다. 자세한 내용은 [printf_s, _printf_s_l, wprintf_s, _wprintf_s_l](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md) 및 [sprintf_s, _sprintf_s_l, swprintf_s, _swprintf_s_l](../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md))를 참조하십시오.

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
