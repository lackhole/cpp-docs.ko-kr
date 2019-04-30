---
title: 컴파일러 오류 C2714
ms.date: 11/04/2016
f1_keywords:
- C2714
helpviewer_keywords:
- C2714
ms.assetid: 401a5a42-660c-4bad-9d63-1a2d092bc489
ms.openlocfilehash: feba363a7cd15d92bf850e8cba457ff310d15490
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386800"
---
# <a name="compiler-error-c2714"></a>컴파일러 오류 C2714

__alignof(void) 허용 되지 않습니다.

잘못 된 값은 운영자에 게 전달 되었습니다.

참조 [__alignof 연산자](../../cpp/alignof-operator.md) 자세한 내용은 합니다.

## <a name="example"></a>예제

다음 샘플에서는 C2714 오류가 발생 합니다.

```
// C2714.cpp
int main() {
   return __alignof(void);   // C2714
   return __alignof(char);   // OK
}
```