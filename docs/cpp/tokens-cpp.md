---
title: 토큰 (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- tokens [C++]
- parsing, C++ tokens
- translation units
- white space, in C++ tokens
ms.assetid: aa812fd0-6d47-4f3f-aee0-db002ee4d8b9
ms.openlocfilehash: 1606df56191ec00ffea543dedd3fd4eda98d01c2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62330442"
---
# <a name="tokens-c"></a>토큰 (C++)

토큰은 컴파일러에 의미 있는 C++ 프로그램의 최소 요소입니다. C++ 파서는 식별자, 키워드, 리터럴, 연산자, 문장 부호 및 기타 구분 기호 등의 토큰을 인식합니다. 이러한 토큰의 스트림은 변환 단위를 구성합니다.

토큰은 일반적으로 *공백*으로 구분됩니다. 하나 이상으로 구성된 다음 요소입니다.

- 비어 있음

- 가로 또는 세로 탭

- 새로운 줄

- Form feed

- 설명

파서는 키워드, 식별자, 리터럴, 연산자 및 문장 부호를 인식합니다. 특정 토큰 종류에 대한 자세한 내용은 [키워드](../cpp/keywords-cpp.md), [식별자](../cpp/identifiers-cpp.md), [숫자, 부울 및 포인터 리터럴](../cpp/numeric-boolean-and-pointer-literals-cpp.md), [문자열 및 문자 리터럴](../cpp/string-and-character-literals-cpp.md), [사용자 정의 리터럴](../cpp/user-defined-literals-cpp.md), [C++ 기본 제공 연산자, 우선 순위 및 계산 방향](../cpp/cpp-built-in-operators-precedence-and-associativity.md)및 [문장 부호](../cpp/punctuators-cpp.md)를 참조하세요. 토큰을 구분하는 데 필요한 경우를 제외하고 공백은 무시됩니다.

전처리 토큰은 전처리 단계에서 사용되어 컴파일러에 전달될 토큰 스트림을 생성합니다. 전처리 토큰 범주는 헤더 이름, 식별자, 전처리 숫자, 문자 리터럴, 문자열 리터럴, 전처리 연산자 및 문장 부호, 다른 범주 중 하나와 일치하지 않는 공백이 아닌 단일 문자입니다. 문자 및 문자열 리터럴은 사용자 정의 리터럴일 수 있습니다. 전처리 토큰은 공백이나 주석으로 구분할 수 있습니다.

파서는 입력된 문자를 사용하여 왼쪽에서 오른쪽으로 검색의 긴 토큰 수를 만들어서 입력 스트림에서 토큰을 구분합니다. 이 코드 조각을 고려하세요.

```cpp
a = i+++j;
```

코드를 작성하는 프로그래머는 다음 두 명령문을 사용하려고 했을 수 있습니다.

```cpp
a = i + (++j)

a = (i++) + j
```

파서는 입력 스트림에서 가장 긴 토큰을 만들기 때문에 두 번째 해석을 선택하여 `i++`, `+`및 `j`토큰을 만듭니다.

## <a name="see-also"></a>참고자료

[어휘 규칙](../cpp/lexical-conventions.md)