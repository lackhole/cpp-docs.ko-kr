---
title: 컴파일러 오류 C2714
ms.date: 11/04/2016
f1_keywords:
- C2714
helpviewer_keywords:
- C2714
ms.assetid: 401a5a42-660c-4bad-9d63-1a2d092bc489
ms.openlocfilehash: b5bfa56ca95cc93680c7eab227d658134b248976
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760558"
---
# <a name="compiler-error-c2714"></a>컴파일러 오류 C2714

__alignof (void)를 사용할 수 없습니다.

잘못 된 값이 연산자에 전달 되었습니다.

자세한 내용은 [__Alignof 연산자](../../cpp/alignof-operator.md) 를 참조 하세요.

## <a name="example"></a>예제

다음 샘플에서는 C2714를 생성 합니다.

```cpp
// C2714.cpp
int main() {
   return __alignof(void);   // C2714
   return __alignof(char);   // OK
}
```
