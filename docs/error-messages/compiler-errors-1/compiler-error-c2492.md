---
title: 컴파일러 오류 C2492
ms.date: 11/04/2016
f1_keywords:
- C2492
helpviewer_keywords:
- C2492
ms.assetid: 8c44c9bb-c366-4fe5-a0ab-882e38608aaa
ms.openlocfilehash: e2b08ef3e46681147c4efd77cbffadb096bbfc16
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62360712"
---
# <a name="compiler-error-c2492"></a>컴파일러 오류 C2492

'*변수*': 스레드 저장 기간이 있는 데이터는 dll 인터페이스 있을 수 없습니다

사용 하 여 선언 된 변수를 [스레드](../../cpp/thread.md) 특성 및 DLL을 사용 하 여 인터페이스입니다. 주소는 `thread` 변수 까지는 알 수 없는 런타임 DLL 가져오기 또는 내보내기에 연결할 수 없습니다 있도록 합니다.

다음 샘플에서는 C2492 오류가 생성 됩니다.

```
// C2492.cpp
// compile with: /c
class C {
public:
   char   ch;
};

__declspec(dllexport) __declspec(thread) C c_1;   // C2492
__declspec(thread) C c_1;   // OK
```