---
title: 컴파일러 오류 C3481
ms.date: 11/04/2016
f1_keywords:
- C3481
helpviewer_keywords:
- C3481
ms.assetid: 5d09375a-5ed3-4b61-86ed-45e91fd734c7
ms.openlocfilehash: eff7c7a4f39524aa1d894b7b4590aa809714aae6
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59041204"
---
# <a name="compiler-error-c3481"></a>컴파일러 오류 C3481

'var': 람다 캡처 변수가 없습니다.

컴파일러가 람다 식의 캡처 목록에 전달된 변수 정의를 찾을 수 없습니다.

### <a name="to-correct-this-error"></a>이 오류를 해결하려면

- 람다 식의 캡처 목록에서 변수를 제거합니다.

## <a name="example"></a>예제

다음 예제에서는 `n` 변수가 정의되지 않았기 때문에 C3481을 생성합니다.

```
// C3481.cpp

int main()
{
   [n] {}(); // C3481
}
```

## <a name="see-also"></a>참고자료

[람다 식](../../cpp/lambda-expressions-in-cpp.md)