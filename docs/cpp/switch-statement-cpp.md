---
title: switch 문 (C++)
ms.date: 05/06/2019
f1_keywords:
- default_cpp
- switch_cpp
- case_cpp
helpviewer_keywords:
- switch keyword [C++]
- case keyword [C++], in switch statements
- default keyword [C++]
ms.assetid: 6c3f3ed3-5593-463c-8f4b-b33742b455c6
ms.openlocfilehash: 8136b03d9e54b4d49bcb1417238066bd86bc6b89
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65221943"
---
# <a name="switch-statement-c"></a>switch 문 (C++)

정수 계열 식의 값에 따라 코드의 여러 섹션 중에서 선택할 수 있습니다.

## <a name="syntax"></a>구문

```
   switch ( init; expression )
   case constant-expression : statement
   [default  : statement]
```

## <a name="remarks"></a>설명

합니다 *식* 는 정수 계열 형식으로 변환 하는 명확한 변환을 하는 클래스 형식 또는 정수 계열 형식 이어야 합니다. 에 설명 된 대로 정수 계열 확장 이루어집니다 [표준 변환](standard-conversions.md)합니다.

합니다 **전환** 일련의 문 본문으로 구성 됩니다 **사례** 레이블 및 선택적 **기본** 레이블. 없는 두 상수 식도 **사례** 문이 동일한 값으로 계산할 수 있습니다. 합니다 **기본** 레이블은 한 번만 나타날 수 있습니다. 레이블된 문은 구문적 요구 사항이 있지만 **전환** 문을 없으면 의미가 없습니다.   기본 문은 끝에 오지 않아도 되며 switch 문의 본문 중 어느 위치에나 나타날 수 있습니다. case 또는 default 레이블은 switch 문 내에만 나타날 수 있습니다.

합니다 *상수-식* 각 **사례** 레이블 형식으로 변환 됩니다 *식* 과 비교 *식* 에 대 한 같음입니다. 해당 문으로 제어가 전달 **사례** *상수-식* 값과 일치 *식*합니다. 결과적으로 발생하는 동작은 다음 표에 나와 있습니다.

### <a name="switch-statement-behavior"></a>switch 문 동작

|조건|작업|
|---------------|------------|
|변환된 값이 승격된 제어 식의 값과 일치합니다.|제어가 해당 레이블 뒤에 오는 문으로 전송됩니다.|
|상수를 일치 하는 상수 없을 합니다 **사례** 레이블의 **기본** 레이블이 합니다.|제어가 합니다 **기본** 레이블.|
|상수를 일치 하는 상수 없을 합니다 **사례** 레이블의 **기본** 레이블이 없습니다.|뒤의 문으로 제어가 합니다 **전환** 문입니다.|

이후 일치 하는 식이 발견 되 면 경우 제어가 방해 되지 않습니다 **사례** 하거나 **기본** 레이블. [중단](../cpp/break-statement-cpp.md) 문 실행을 중지 하 고 뒤의 문으로 제어를 전송 되는 **전환** 문입니다. 없이 **중단** 문, 일치에서 모든 문 **사례** 의 끝에 레이블을 **전환**등을 **기본**는 실행 합니다. 예를 들어:

```cpp
// switch_statement1.cpp
#include <stdio.h>

int main() {
   char *buffer = "Any character stream";
   int capa, lettera, nota;
   char c;
   capa = lettera = nota = 0;

   while ( c = *buffer++ )   // Walks buffer until NULL
   {
      switch ( c )
      {
         case 'A':
            capa++;
            break;
         case 'a':
            lettera++;
            break;
         default:
            nota++;
      }
   }
   printf_s( "\nUppercase a: %d\nLowercase a: %d\nTotal: %d\n",
      capa, lettera, (capa + lettera + nota) );
}
```

위의 예제에서 `capa`는 `c`가 대문자 `A`인 경우 증가됩니다. **중단** 뒤의 문으로 `capa++` 의 실행을 종료 합니다 **전환** 문 본문 및 제어를 전달 합니다 **하는 동안** 루프. 없이 합니다 **나누기** 문의 실행은 "이동" 다음 레이블이 지정 된 문, 있도록 `lettera` 및 `nota` 도 증가 됩니다. 용도 비슷하지만 의해 제공 되는 **나누기** 방침 `case 'a'`합니다. 경우 `c` 는 소문자 `a`, `lettera` 증가 및 **중단** 문이 종료 되는 **전환** 문 본문입니다. 하는 경우 `c` 아닙니다를 `a` 또는 `A`의 **기본** 문이 실행 됩니다.

**Visual Studio 2017 이상:** (사용할 수 있습니다 [/std: c + + 17](../build/reference/std-specify-language-standard-version.md))는 `[[fallthrough]]` 표준 C + + 17 특성을 지정 합니다. 사용할 수는 **전환** 문을 해당 제어 이동 동작이 의도 된 컴파일러 (또는 코드를 읽는 사람에 게) 힌트로 합니다. Microsoft C++ 컴파일러 현재 경고 하지 않습니다 fallthrough 동작에 있으므로이 특성에 컴파일러 동작에 영향을 주지 않습니다. Labeled 문; 내에서 빈 문에 특성이 적용 되는 참고 즉 세미콜론 필요는 없습니다.

```cpp
int main()
{
    int n = 5;
    switch (n)
    {

    case 1:
        a();
        break;
    case 2:
        b();
        d();
        [[fallthrough]]; // I meant to do this!
    case 3:
        c();
        break;
    default:
        d();
        break;
    }

    return 0;
}
```

**Visual Studio 2017 버전 15.3 이상** (사용할 수 있습니다 [/std: c + + 17](../build/reference/std-specify-language-standard-version.md)):  Switch 문을 소개 하 고 범위가 블록 switch 문의 제한 된 변수를 초기화할 수 있습니다.

```cpp
    switch (Gadget gadget(args); auto s = gadget.get_status())
    {
    case status::good:
        gadget.zip();
        break;
    case status::bad:
        throw BadGadget();
    };
```

내부 블록을 **전환** 문은으로 연결할 수는 초기화를 사용 하 여 정의 포함할 수 있습니다-즉, 모든 가능한 실행 경로 의해 무시 되지 않습니다. 이러한 선언을 사용하여 정의된 이름에는 로컬 범위가 있습니다. 예를 들어:

```cpp
// switch_statement2.cpp
// C2360 expected
#include <iostream>
using namespace std;
int main(int argc, char *argv[])
{
    switch( tolower( *argv[1] ) )
    {
        // Error. Unreachable declaration.
        char szChEntered[] = "Character entered was: ";

    case 'a' :
        {
        // Declaration of szChEntered OK. Local scope.
        char szChEntered[] = "Character entered was: ";
        cout << szChEntered << "a\n";
        }
        break;

    case 'b' :
        // Value of szChEntered undefined.
        cout << szChEntered << "b\n";
        break;

    default:
        // Value of szChEntered undefined.
        cout << szChEntered << "neither a nor b\n";
        break;
    }
}
```

A **전환** 문은 중첩 될 수 있습니다. 이러한 경우 **사례** 또는 **기본** 레이블을 연결 가장 가까운 **전환** 바깥쪽 문을 합니다.

**Microsoft 전용**

Microsoft C의 경우 값의 수를 제한 하지 않습니다는 **전환** 문입니다. 이 수는 사용 가능한 메모리에 의해서만 제한됩니다. ANSI C 257 개 이상의 case 레이블이 허용을 **전환** 문입니다.

기본적으로 Microsoft C에는 Microsoft 확장을 사용하도록 설정되어 있습니다. 사용 된 [/Za](../build/reference/za-ze-disable-language-extensions.md) 컴파일러 옵션을 이러한 확장을 사용 하지 않도록 설정 합니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[선택 문(C++)](../cpp/selection-statements-cpp.md)<br/>
[C++ 키워드](../cpp/keywords-cpp.md)