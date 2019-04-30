---
title: 컴파일러 오류 C3539
ms.date: 11/04/2016
f1_keywords:
- C3539
helpviewer_keywords:
- C3539
ms.assetid: 34a33a0f-d1b6-498f-b312-ffad2d4799b3
ms.openlocfilehash: be1051859ebbcbdc22a9b71f8c5adba2e75c4e92
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64344655"
---
# <a name="compiler-error-c3539"></a>컴파일러 오류 C3539

'type': 템플릿 인수는 'auto'를 포함 하는 형식일 수 없습니다.

지정 된 템플릿 인수 형식을 사용 하는 포함할 수 없습니다는 `auto` 키워드입니다.

### <a name="to-correct-this-error"></a>이 오류를 해결하려면

1. 템플릿 인수를 지정 하지 않으면는 `auto` 키워드입니다.

## <a name="example"></a>예제

다음 예제에서는 C3539를 생성합니다.

```
// C3539.cpp
// Compile with /Zc:auto
template<class T> class C{};
int main()
{
   C<auto> c;   // C3539
   return 0;
}
```

## <a name="see-also"></a>참고자료

[auto 키워드](../../cpp/auto-keyword.md)