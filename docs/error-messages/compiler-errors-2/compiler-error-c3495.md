---
title: 컴파일러 오류 C3495
ms.date: 11/04/2016
f1_keywords:
- C3495
helpviewer_keywords:
- C3495
ms.assetid: 1fd40cb8-8373-403d-b8a8-f08424a50807
ms.openlocfilehash: 1a61d4f2472ef6da8aedcf8a8ef90b70de47d8af
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74738273"
---
# <a name="compiler-error-c3495"></a>컴파일러 오류 C3495

'var': 람다 캡처에는 자동 스토리지 기간이 있어야 합니다.

`static` 또는 `extern`으로 표시된 변수와 같이 자동 스토리지 기간이 없는 변수를 캡처할 수 없습니다.

### <a name="to-correct-this-error"></a>이 오류를 해결하려면

- 람다 식의 캡처 목록에 `static` 또는 `extern` 변수를 전달하지 마세요.

## <a name="example"></a>예제

다음 예제에서는 `static` 변수 `n` 이 람다 식의 캡처 목록에 나타나므로 C3495를 생성합니다.

```cpp
// C3495.cpp

int main()
{
   static int n = 66;
   [&n]() { return n; }(); // C3495
}
```

## <a name="see-also"></a>참조

[람다 식](../../cpp/lambda-expressions-in-cpp.md)

