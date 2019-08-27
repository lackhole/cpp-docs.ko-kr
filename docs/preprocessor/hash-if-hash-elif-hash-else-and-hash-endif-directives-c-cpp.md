---
title: '##elif, if, #else 및 #endif 지시문 (C /C++)'
ms.date: 11/04/2016
f1_keywords:
- '#else'
- '#endif'
- '#if'
- '#elif'
- defined
- __has_include
helpviewer_keywords:
- '#elif directive'
- conditional compilation, directives
- endif directive (#endif)
- preprocessor, directives
- '#else directive'
- '#endif directive'
- if directive (#if)
- else directive (#else)
- '#if directive'
- elif directive (#elif)
- defined directive
ms.assetid: c77a175f-6ca8-47d4-8df9-7bac5943d01b
ms.openlocfilehash: 90fbab45c6408c30198c2a52a42545718002cc11
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62409891"
---
# <a name="if-elif-else-and-endif-directives-cc"></a>#if, #elif, #else, and #endif 지시문 (C/C++)

합니다 **#if** 지시문에 **#elif**를 **#else**, 및 **#endif** 지시문을 소스 파일 부분 들의 컴파일 제어 합니다. 식을 작성 하는 경우 (후 합니다 **#if**)에 0이 아닌 값이 바로 다음 줄 그룹 합니다 **#if** 지시문은 변환 단위에서 유지 됩니다.

## <a name="grammar"></a>문법

*conditional* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*if-part elif-parts*<sub>opt</sub> *else-part*<sub>opt</sub> *endif-line*

*if-part* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*경우에 줄 텍스트*

*if-line* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **#if**  *constant-expression*<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **#ifdef**  *identifier*<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **#ifndef**  *identifier*

*elif-parts* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*elif 줄 텍스트*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*elif 부분 elif 줄 텍스트*

*elif-line* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **#elif**  *constant-expression*

*else-part* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*다른 줄 텍스트*

*else-line* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **#else**

*endif-line* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **#endif**

각 **#if** 소스 파일의 지시문은 닫는 일치 되어야 **#endif** 지시문입니다. 임의 개수의 **#elif** 지시문 사이 나타날 수는 **#if** 및 **#endif** 지시문을 사용할 수 있지만 최대 **#else** 지시문 허용 됩니다. 합니다 **#else** 지시문을 있으면 해야 하기 전에 마지막 지시문 **#endif**합니다.

합니다 **#if**를 **#elif**를 **#else**, 및 **#endif** 지시문을 다른 텍스트 부분에서 중첩 **#if**지시문입니다. 중첩 된 각 **#else**를 **#elif**, 또는 **#endif** 지시문은 가장 가까운 이전 속한 **#if** 지시문입니다.

모든 조건부 컴파일 지시문와 같은 **#if** 하 고 **#ifdef**를 닫는 일치 해야 **#endif** 지시문 전에 파일 끝에;이 고, 그렇지 오류가 메시지가 생성 됩니다. 조건부 컴파일 지시문에 포함 된 파일을 포함할 경우 동일한 조건을 만족 해야 합니다. 포함 파일의 끝에 일치 하지 않는 조건부 컴파일 지시문이 없는 이어야 합니다.

매크로 대체 다음에 나오는 명령줄의 부분 안에서 수행 되는 **#elif** 매크로 호출에 사용할 수 있도록 명령을 *상수-식*.

전처리기의 지정 된 항목 중 하나를 선택 합니다. *텍스트* 처리할 수 있도록 합니다. 에 지정 된 블록이 *텍스트* 임의의 텍스트 시퀀스를 수 있습니다. 두 줄 이상을 차지할 수 있습니다. 일반적으로 *텍스트* 은 컴파일러 또는 전처리기에 의미가 있는 프로그램 텍스트입니다.

전처리기는 선택한 처리 *텍스트* 컴파일러에 전달 합니다. 하는 경우 *텍스트* 이러한 지시문은 전처리기가 수행 하는 전처리기 지시문을 포함 합니다. 전처리기에서 선택한 텍스트 블록만 컴파일됩니다.

전처리기가 단일 *텍스트* 각각 다음 상수 식을 평가 하 여 항목 **#if** 하거나 **#elif** true (0이 아닌) 상수를 발견할 때까지 지시문 식입니다. 모든 텍스트를 선택 (부터 다른 전처리기 지시문 포함 **#** ) 관련까지 **#elif**를 **#else**, 또는 **#endif** .

경우 모든 *상수-식* 이 false 없으면 또는 **#elif** 표시 하는 지시문, 전처리기 후 텍스트 블록을 선택 합니다 **#else** 절. 경우는 **#else** 절을 생략 하면 및의 모든 인스턴스 *상수-식* 에 **#if** 블록 false 인 경우 텍스트 블록이 없습니다. 선택 합니다.

합니다 *상수-식* 는 이러한 추가 제한이 있는 정수 상수 식:

- 식은 정수 계열 형식 이어야 하 고만 정수 상수, 문자 상수를 포함할 수 있습니다 및 **정의** 연산자입니다.

- 식에서는 `sizeof` 또는 형식 캐스팅 연산자를 사용할 수 없습니다.

- 대상 개발 환경은 모든 범위의 정수를 나타내지 못할 수 있습니다.

- 변환 유형을 나타냅니다 **int** 형식과 동일 **긴**, 및 **부호 없는 int** 동일 **부호 없는 long**합니다.

- 변환기는 문자 상수를 대상 개발 환경에 대한 집합과 다른 코드 값의 집합으로 변환할 수 있습니다. 대상 개발 환경의 속성을 확인하려면 대상 개발 환경용으로 작성된 애플리케이션의 LIMITS.H에서 매크로 값을 확인합니다.

- 식은 환경 조회를 수행해서는 안 되며 대상 컴퓨터의 구현 정보에서 영향을 받지 않아야 합니다.

## <a name="defined"></a>정의

전처리기 연산자 **정의** 다음 구문을 사용 하 여 표시 된 것과 같이 특수 상수 식에서 사용할 수 있습니다.

defined( `identifier` )

defined `identifier`

이 상수 식은 true (0이 아닌) 것으로 간주 됩니다는 *식별자* 현재 정의 된; 조건이 false 이면 그렇지 않은 경우 (0). 빈 텍스트로 정의된 식별자는 정의된 것으로 간주됩니다. 합니다 **정의** 지시문에서 사용할 수는 **#if** 및 **#elif** 지시문 되지만 다른 위치입니다.

다음 예에서 합니다 **#if** 및 **#endif** 지시문 중 세 가지 함수 호출 중 하나의 컴파일을 제어 합니다.

```C
#if defined(CREDIT)
    credit();
#elif defined(DEBIT)
    debit();
#else
    printerror();
#endif
```

`credit` 식별자가 정의된 경우 `CREDIT`에 대한 함수 호출이 컴파일됩니다. `DEBIT` 식별자가 정의된 경우 `debit`에 대한 함수 호출이 컴파일됩니다. 식별자가 정의되지 않은 경우에는 `printerror`에 대한 호출이 컴파일됩니다. C와 C++에서 `CREDIT` 및 `credit`은 대/소문자가 다르기 때문에 고유한 식별자입니다.

다음 예제의 조건부 컴파일 문은 `DLEVEL`이라는 이전에 정의된 기호화된 상수를 가정합니다.

```C
#if DLEVEL > 5
    #define SIGNAL  1
    #if STACKUSE == 1
        #define STACK   200
    #else
        #define STACK   100
    #endif
#else
    #define SIGNAL  0
    #if STACKUSE == 1
        #define STACK   100
    #else
        #define STACK   50
    #endif
#endif
#if DLEVEL == 0
    #define STACK 0
#elif DLEVEL == 1
    #define STACK 100
#elif DLEVEL > 5
    display( debugptr );
#else
    #define STACK 200
#endif
```

첫 번째 **#if** 블록의 두 집합이 표시 중첩 **#if**합니다 **#else**, 및 **#endif** 지시문입니다. `DLEVEL > 5`가 true인 경우에만 지시문의 첫 번째 집합이 처리됩니다. 그렇지 않은 경우 다음의 문이 **#else** 처리 됩니다.

합니다 **#elif** 하 고 **#else** 의 값을 기반으로 선택 항목 4 개 중 하나를 수행 하려면 두 번째 예제에서는 지시문을 사용 하는 `DLEVEL`합니다. `STACK` 상수는 `DLEVEL`의 정의에 따라 0, 100 또는 200으로 설정됩니다. `DLEVEL`이 5보다 크면 다음 문이

```C
#elif DLEVEL > 5
display(debugptr);
```

컴파일되며 `STACK`은 정의되지 않습니다.

조건부 컴파일은 동일한 헤더 파일이 여러 번 포함되는 것을 방지하기 위해 일반적으로 사용됩니다. 헤더 파일에서 클래스가 자주 정의되는 C++에서는 다음과 같은 구문을 사용하여 여러 정의를 방지할 수 있습니다.

```cpp
/*  EXAMPLE.H - Example header file  */
#if !defined( EXAMPLE_H )
#define EXAMPLE_H

class Example
{
...
};

#endif // !defined( EXAMPLE_H )
```

앞의 코드에서는 기호화된 상수 `EXAMPLE_H`가 정의되어 있는지 여부를 확인합니다. 정의되어 있는 경우 해당 파일이 이미 포함되었으며 다시 처리될 필요가 없습니다. 정의되어 있지 않은 경우에는 `EXAMPLE_H` 상수가 이미 처리된 대로 EXAMPLE.H를 표시하도록 정의됩니다.

## <a name="__has_include"></a>__has_include

**Visual Studio 2017 버전 15.3 이상:**  라이브러리 헤더를 포함 하기 위해 사용할 수 있는지 결정 합니다.

```cpp
#ifdef __has_include
#  if __has_include(<filesystem>)
#    include <filesystem>
#    define have_filesystem 1
#  elif __has_include(<experimental/filesystem>)
#    include <experimental/filesystem>
#    define have_filesystem 1
#    define experimental_filesystem
#  else
#    define have_filesystem 0
#  endif
#endif
```

## <a name="see-also"></a>참고자료

[전처리기 지시문](../preprocessor/preprocessor-directives.md)