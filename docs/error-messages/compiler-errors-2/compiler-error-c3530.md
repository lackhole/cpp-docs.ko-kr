---
title: 컴파일러 오류 C3530
ms.date: 11/04/2016
f1_keywords:
- C3530
helpviewer_keywords:
- C3530
ms.assetid: 21be81ce-b699-4c74-81bc-80a0c34d2d5a
ms.openlocfilehash: dd4368faaf323a75116128ec3a47666260436fce
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59029121"
---
# <a name="compiler-error-c3530"></a>컴파일러 오류 C3530

'auto' 다른 형식 지정자를 사용 하 여 결합할 수 없습니다.

형식 지정자와 함께 사용 됩니다는 `auto` 키워드입니다.

### <a name="to-correct-this-error"></a>이 오류를 해결하려면

1. 사용 하는 변수 선언에 형식 지정자를 사용 하지 마십시오는 `auto` 키워드입니다.

## <a name="example"></a>예제

때문에 다음 예제에서는 생성 C3530 변수 `x` 둘 다를 사용 하 여 선언 되는 `auto` 키워드 및 형식 `int`, 이므로 예제로 컴파일됩니다 **/zc: auto**.

```
// C3530.cpp
// Compile with /Zc:auto
int main()
{
   auto int x;   // C3530
   return 0;
}
```

## <a name="see-also"></a>참고자료

[auto 키워드](../../cpp/auto-keyword.md)