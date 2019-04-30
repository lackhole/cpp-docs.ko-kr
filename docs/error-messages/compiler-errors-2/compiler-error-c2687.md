---
title: 컴파일러 오류 C2687
ms.date: 11/04/2016
f1_keywords:
- C2687
helpviewer_keywords:
- C2687
ms.assetid: 1d24b24a-cd0f-41cc-975c-b08dcfb7f402
ms.openlocfilehash: a30efa264a4e7be387c3c2363940bd5ceca1bcc4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62266194"
---
# <a name="compiler-error-c2687"></a>컴파일러 오류 C2687

'type': 예외 선언은 'void' 수 없거나는 불완전 한 형식 또는 포인터 또는 불완전 한 형식에 대 한 참조를 나타냅니다

예외 선언의 일부로 형식에 대해 정의 되 고 void가 아니라 이어야 합니다.

다음 샘플에서는 C2687를 생성합니다.

```
// C2687.cpp
class C;

int main() {
   try {}
   catch (C) {}   // C2687 error
}
```

해결 방법:

```
// C2687b.cpp
// compile with: /EHsc
class C {};

int main() {
   try {}
   catch (C) {}
}
```