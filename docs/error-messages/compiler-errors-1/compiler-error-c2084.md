---
title: 컴파일러 오류 C2084
ms.date: 11/04/2016
f1_keywords:
- C2084
helpviewer_keywords:
- C2084
ms.assetid: 990b107f-3721-4851-ae8b-4b69a8c149ed
ms.openlocfilehash: 9aaf3a88e63234dfb842e4b48afd6e55595e96ca
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62391922"
---
# <a name="compiler-error-c2084"></a>컴파일러 오류 C2084

함수 '*함수*' 이미 본문이 있습니다.

함수가 이미 정의 되었습니다.

시각적 개체의 버전에서 C++ Visual Studio 2002 년 이전

- 추가 정의 사용할 수 없는 있지만 컴파일러에서 동일한 실제 형식으로 확인 하는 여러 템플릿 특수화를 수락 했습니다. 컴파일러는 이제 이러한 여러 정의 검색합니다.

- `__int32` 및 `int` 별도 형식으로 간주 되었습니다. 이제는 컴파일러에서 간주 `__int32` 의 동의어로 `int`합니다. 즉, 둘 다에서 함수는 오버 로드 하는 경우 컴파일러 여러 정의 검색 하는지 `__int32` 및 `int` 및 오류가 발생 합니다.

## <a name="example"></a>예제

다음 샘플에서는 C2084 오류가 생성 됩니다.

```cpp
// C2084.cpp
void Func(int);
void Func(int) {}   // define function
void Func(int) {}   // C2084 second definition
```

이 오류를 해결 하려면 중복 정의 제거 합니다.

```
// C2084b.cpp
// compile with: /c
void Func(int);
void Func(int) {}
```