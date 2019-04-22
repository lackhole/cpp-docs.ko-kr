---
title: 컴파일러 오류 C3537
ms.date: 11/04/2016
f1_keywords:
- C3537
helpviewer_keywords:
- C3537
ms.assetid: f537ebd1-4fb0-4e09-a453-4f38db2c6881
ms.openlocfilehash: 50a06180dabfa192292fae7ba1962b6b7455bb89
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59024026"
---
# <a name="compiler-error-c3537"></a>컴파일러 오류 C3537

'type': 'auto'를 포함 하는 형식으로 캐스팅할 수 없습니다

형식을 포함 하기 때문에 변수 표시 된 형식으로 캐스팅할 수 없습니다는 `auto` 키워드 및 기본 [/zc: auto](../../build/reference/zc-auto-deduce-variable-type.md) 컴파일러 옵션이 적용 됩니다.

## <a name="example"></a>예제

다음 코드에서는 C3537 포함 하는 형식으로 캐스팅 하는 변수는 `auto` 키워드입니다.

```
// C3537.cpp
// Compile with /Zc:auto
int main()
{
   int value = 123;
   auto(value);                        // C3537
   (auto)value;                        // C3537
   auto x1 = auto(value);              // C3537
   auto x2 = (auto)value;              // C3537
   auto x3 = static_cast<auto>(value); // C3537
   return 0;
}
```

## <a name="see-also"></a>참고자료

[auto 키워드](../../cpp/auto-keyword.md)