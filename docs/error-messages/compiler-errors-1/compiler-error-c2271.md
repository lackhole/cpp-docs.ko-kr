---
title: 컴파일러 오류 C2271
ms.date: 11/04/2016
f1_keywords:
- C2271
helpviewer_keywords:
- C2271
ms.assetid: ea47bf57-f55d-4171-8e98-95a71d62820e
ms.openlocfilehash: 68de819ca62e117036bb415a1708afc0ecd6028c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62388997"
---
# <a name="compiler-error-c2271"></a>컴파일러 오류 C2271

'operator': 삭제/새 형식 목록 한정자를 사용할 수 없습니다

연산자 (`new` 또는 `delete`)는 메모리 내 모델 지정자를 사용 하 여 선언 됩니다.

다음 샘플에서는 C2271 오류가 생성 됩니다.

```
// C2271.cpp
// compile with: /c
void* operator new(size_t) const {   // C2271
// try the following line instead
// void* operator new(size_t) {
   return 0;
}

struct X {
   static void* operator new(size_t) const;   // C2271
   // try the following line instead
   // void * X::operator new(size_t) const;   // static member operator new
};
```