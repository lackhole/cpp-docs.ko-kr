---
title: 컴파일러 오류 C3484
ms.date: 11/04/2016
f1_keywords:
- C3484
helpviewer_keywords:
- C3484
ms.assetid: 2fe847fa-f6ee-4978-bc1d-b6dc6ae906ac
ms.openlocfilehash: c4405eb81911b1081d19d25ba779d24bee8f6d37
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59039980"
---
# <a name="compiler-error-c3484"></a>컴파일러 오류 C3484

반환 형식 앞에 '->'가 필요합니다.

람다 식의 반환 형식 앞에 `->` 를 제공해야 합니다.

### <a name="to-correct-this-error"></a>이 오류를 해결하려면

- 반환 형식 앞에 `->` 를 제공합니다.

## <a name="example"></a>예제

다음 예제에서는 C3484를 생성합니다.

```
// C3484a.cpp

int main()
{
   return []() . int { return 42; }(); // C3484
}
```

## <a name="example"></a>예제

다음 예제에서는 람다 식의 반환 형식 앞에 `->` 를 제공하여 C3484를 해결합니다.

```
// C3484b.cpp

int main()
{
   return []() -> int { return 42; }();
}
```

## <a name="see-also"></a>참고자료

[람다 식](../../cpp/lambda-expressions-in-cpp.md)