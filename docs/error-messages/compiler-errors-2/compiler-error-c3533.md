---
title: 컴파일러 오류 C3533
ms.date: 11/04/2016
f1_keywords:
- C3533
helpviewer_keywords:
- C3533
ms.assetid: a68b1ba5-466e-4190-a1a4-505ccfe548b7
ms.openlocfilehash: 7a567e4396999f98d9e9740db0acf951c443d525
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59026307"
---
# <a name="compiler-error-c3533"></a>컴파일러 오류 C3533

'type': 매개 변수 'auto'를 포함 하는 형식을 사용할 수 없습니다

메서드 또는 템플릿 매개 변수를 선언할 수 없습니다는 `auto` 키워드 경우 기본값 [/zc: auto](../../build/reference/zc-auto-deduce-variable-type.md) 컴파일러 옵션이 적용 됩니다.

### <a name="to-correct-this-error"></a>이 오류를 해결하려면

1. 제거 된 `auto` 매개 변수 선언에서 키워드입니다.

## <a name="example"></a>예제

다음 예제에서는 사용 하 여 함수 매개 변수를 선언 하므로 C3533를 생성 합니다 `auto` 키워드 하며 사용 하 여 컴파일된 **/zc: auto**합니다.

```
// C3533a.cpp
// Compile with /Zc:auto
void f(auto j) {} // C3533
```

## <a name="example"></a>예제

다음 예제에서는 사용 하 여 템플릿 매개 변수를 선언 하므로 c++14 모드에서 C3533을 생성 합니다 `auto` 키워드 하며 사용 하 여 컴파일된 **/zc: auto**합니다. (C + + 17,이 유효한 형식이 추론 되는 단일 비형식 템플릿 매개 변수를 사용 하 여 클래스 템플릿 정의 합니다.)

```
// C3533b.cpp
// Compile with /Zc:auto
template<auto T> class C {}; // C3533
```

## <a name="see-also"></a>참고자료

[auto 키워드](../../cpp/auto-keyword.md)<br/>
[/Zc:auto(변수 형식 추론)](../../build/reference/zc-auto-deduce-variable-type.md)
