---
title: 컴파일러 오류 C3087
ms.date: 11/04/2016
f1_keywords:
- C3087
helpviewer_keywords:
- C3087
ms.assetid: 4f5bdd52-a853-4f02-b160-6868e9190b9d
ms.openlocfilehash: 6b9ae71ebfbcfcd5936a2fc3ca666aa51e59bfb5
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74751419"
---
# <a name="compiler-error-c3087"></a>컴파일러 오류 C3087

'named_argument': 'attribute'에 대한 호출에서 이미 이 멤버를 초기화했습니다.

명명된 인수가 동일한 값에 대한 명명되지 않은 인수와 동일한 특성 블록에서 지정되었습니다. 명명된 인수나 명명되지 않은 인수만 지정합니다.

## <a name="example"></a>예제

다음 샘플에서는 C3087을 생성합니다.

```cpp
// C3087.cpp
// compile with: /c
[idl_quote("quote1", text="quote2")];   // C3087
[idl_quote(text="quote3")];   // OK
[idl_quote("quote4")];   // OK
```
