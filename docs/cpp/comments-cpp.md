---
title: 주석 (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- code comments, C++
- comments, documenting code
- comments, C++ code
- white space, C++ comments
ms.assetid: 6fcb906c-c264-4083-84bc-373800b2e514
ms.openlocfilehash: a90d9d37e69cb2e8be4ab18f77026fdce1221307
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62399176"
---
# <a name="comments-c"></a>주석 (C++)

주석이란 컴파일 시에는 무시되지만 프로그래머에게 해설을 제공하고 이해를 돕는 유용한 문장입니다. 주석은 향후 참조를 위해 일반적으로 코드에 설명을 덧붙이는 데 사용됩니다. 컴파일러에서는 주석을 공백으로 취급합니다. 특정 코드 줄을 비활성으로 만들면 테스트 시 메모를 사용할 수 있습니다. 그러나 주석이 포함된 코드를 묶을 수는 있지만 주석은 중첩될 수 없기 때문에 `#if`/`#endif` 전처리기 지시문이 더 잘 작동합니다.

C++ 주석은 다음 방법 중 하나로 기록됩니다.

- `/*`(슬래시, 별표) 문자 뒤에 임의의 문자들(새로운 줄 포함)이 나오고 `*/`가 나옵니다. 이 구문은 ANSI C와 같습니다.

- `//`(슬래시 두 개) 다음에 임의의 문자들이 나옵니다. 백슬래시가 바로 앞에 오지 않는 새 줄은 이러한 형식의 주석을 종료합니다. 따라서 일반적으로 "한 줄 주석"이라고 합니다.

주석 문자(`/*`, `*/`, 및 `//`)는 문자 상수, 문자열 리터럴 또는 주석 안에서 특별한 의미가 없습니다. 따라서 첫 번째 구문을 사용하는 주석은 중첩할 수 없습니다.

## <a name="see-also"></a>참고 항목

[어휘 규칙](../cpp/lexical-conventions.md)