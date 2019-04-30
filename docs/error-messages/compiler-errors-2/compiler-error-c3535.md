---
title: 컴파일러 오류 C3535
ms.date: 11/04/2016
f1_keywords:
- C3535
helpviewer_keywords:
- C3535
ms.assetid: 24449c98-f681-484d-a00b-32533dca3a88
ms.openlocfilehash: e80fa62db9795838980c63e113300a554afabef3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62376239"
---
# <a name="compiler-error-c3535"></a>컴파일러 오류 C3535

'type2'에서 'type1' 형식을 추론할 수 없습니다.

형식에서 선언 된 변수는 `auto` 키워드는 초기화 식의 형식에서 추론할 수 없습니다. 초기화 식이 계산 되는 경우이 오류가 발생 하는 예를 들어 `void`에 형식이 아닙니다.

### <a name="to-correct-this-error"></a>이 오류를 해결하려면

1. 초기화 식의 형식이 아닌지 확인 `void`합니다.

1. 선언 기본 형식에 대 한 포인터 인지 확인 합니다. 자세한 내용은 [기본 형식](../../cpp/fundamental-types-cpp.md)합니다.

1. 선언 형식에 대 한 포인터 이면 초기화 식이 포인터 형식 인지 확인 합니다.

## <a name="example"></a>예제

초기화 식이로 계산 되므로 다음 예제에서는 생성 C3535 `void`합니다.

```
// C3535a.cpp
// Compile with /Zc:auto
void f(){}
int main()
{
   auto x = f();   //C3535
   return 0;
}
```

## <a name="example"></a>예제

문은 변수를 선언 하므로 다음 예제에서는 생성 C3535 `x` 이니셜라이저 인데 추론된 된 형식에 대 한 포인터 식이 double입니다. 따라서 컴파일러는 변수의 형식을 추론할 수 없습니다.

```
// C3535b.cpp
// Compile with /Zc:auto
int main()
{
   auto* x = 123.0;   // C3535
   return 0;
}
```

## <a name="example"></a>예제

다음 예제에서는 생성 C3535 때문에 변수 `p` 추론된 된 형식에 대 한 포인터를 선언 하지만 초기화 식이 포인터 형식이 아닙니다.

```
// C3535c.cpp
// Compile with /Zc:auto
class A { };
A x;
auto *p = x;  // C3535
```

## <a name="see-also"></a>참고자료

[auto 키워드](../../cpp/auto-keyword.md)<br/>
[기본 형식](../../cpp/fundamental-types-cpp.md)