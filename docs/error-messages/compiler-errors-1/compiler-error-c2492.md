---
title: 컴파일러 오류 C2492
ms.date: 11/04/2016
f1_keywords:
- C2492
helpviewer_keywords:
- C2492
ms.assetid: 8c44c9bb-c366-4fe5-a0ab-882e38608aaa
ms.openlocfilehash: fd52b434f86bdc93124c6005bbf7fadad3cb56b2
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757061"
---
# <a name="compiler-error-c2492"></a>컴파일러 오류 C2492

'*variable*': 스레드 저장 기간이 있는 데이터에는 dll 인터페이스를 사용할 수 없습니다.

변수는 [thread](../../cpp/thread.md) 특성과 DLL 인터페이스를 사용 하 여 선언 됩니다. `thread` 변수의 주소는 런타임까지 알려지지 않으므로 DLL 가져오기 또는 내보내기에 연결할 수 없습니다.

다음 샘플에서는 C2492를 생성 합니다.

```cpp
// C2492.cpp
// compile with: /c
class C {
public:
   char   ch;
};

__declspec(dllexport) __declspec(thread) C c_1;   // C2492
__declspec(thread) C c_1;   // OK
```
