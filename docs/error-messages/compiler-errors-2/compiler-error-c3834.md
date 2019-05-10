---
title: 컴파일러 오류 C3834
ms.date: 11/04/2016
f1_keywords:
- C3834
helpviewer_keywords:
- C3834
ms.assetid: 059e0dc4-300b-4e74-b6c2-41a57831fe2a
ms.openlocfilehash: 9f2bb96beaac8ede75863084c8ebf8345c940f53
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62327511"
---
# <a name="compiler-error-c3834"></a>컴파일러 오류 C3834

잘못 된 명시적 고정 포인터로 캐스팅 고정된 된 지역 변수를 대신 사용

고정 포인터로 명시적 캐스트는 허용 되지 않습니다.

## <a name="example"></a>예제

다음 샘플 C3834를 생성합니다.

```
// C3834.cpp
// compile with: /clr
int main() {
   int x = 33;

   pin_ptr<int> p = safe_cast<pin_ptr<int> >(&x);   // C3834
   pin_ptr<int> p2 = &x;   // OK
}
```
