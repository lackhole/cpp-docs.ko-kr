---
title: 컴파일러 오류 C2946
ms.date: 11/04/2016
f1_keywords:
- C2946
helpviewer_keywords:
- C2946
ms.assetid: c86dfbfc-7702-4f09-8a53-d205710e99c2
ms.openlocfilehash: 0f61d047fcd070f3deea662cd3bd193f8e133659
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62187629"
---
# <a name="compiler-error-c2946"></a>컴파일러 오류 C2946

명시적 인스턴스화. 'class'는 템플릿-클래스 특수화가 아닙니다.

템플릿이 아닌 클래스를 명시적으로 인스턴스화할 수 없습니다.

## <a name="example"></a>예제

다음 샘플에서는 C2946을 생성합니다.

```
// C2946.cpp
class C {};
template C;  // C2946
int main() {}
```