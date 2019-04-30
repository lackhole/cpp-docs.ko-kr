---
title: 컴파일러 경고 (수준 1) C4190
ms.date: 11/04/2016
f1_keywords:
- C4190
helpviewer_keywords:
- C4190
ms.assetid: a4d0ad93-a19a-4063-addd-36d605831567
ms.openlocfilehash: 05984594a57878aad8037861a15ac9284ff65192
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386501"
---
# <a name="compiler-warning-level-1-c4190"></a>컴파일러 경고 (수준 1) C4190

'identifier1' C 링크를 지정 했지만 'identifier2' C와 호환 되지 않는 UDT를 반환 합니다.

반환 형식으로 함수 또는 함수에 대 한 포인터에 UDT (사용자 정의 형식, 클래스, 구조체, 열거형 또는 공용 구조체) 및 `extern` "C" 링크가 있습니다. 이 유효 하는 경우:

- 이 함수에 대 한 모든 호출이 발생에서 C++입니다.

- 함수 정의 C++입니다.

## <a name="example"></a>예제

```cpp
// C4190.cpp
// compile with: /W1 /LD
struct X
{
   int i;
   X ();
   virtual ~X ();
};

extern "C" X func ();   // C4190
```