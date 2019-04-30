---
title: 컴파일러 오류 C2577
ms.date: 11/04/2016
f1_keywords:
- C2577
helpviewer_keywords:
- C2577
ms.assetid: fc79ef83-8362-40a2-9257-8037c3195ce4
ms.openlocfilehash: 4406aa90b26bc517308132ae9cccd003d44a9aad
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62408461"
---
# <a name="compiler-error-c2577"></a>컴파일러 오류 C2577

'member': 소멸자/종료자는 반환 형식을 가질 수 없습니다.

소멸자 또는 종료자의 값을 반환할 수 `void` 또는 다른 형식입니다. 제거 된 `return` 소멸자 정의에서 문입니다.

## <a name="example"></a>예제

다음 샘플 C2577를 생성합니다.

```
// C2577.cpp
// compile with: /c
class A {
public:
   A() {}
   ~A(){
      return 0;   // C2577
   }
};
```