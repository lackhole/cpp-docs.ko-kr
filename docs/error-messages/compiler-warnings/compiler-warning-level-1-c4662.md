---
title: 컴파일러 경고(수준 1) C4662
ms.date: 11/04/2016
f1_keywords:
- C4662
helpviewer_keywords:
- C4662
ms.assetid: 7efda273-d04a-47b7-ad65-ff1ff94b5ffc
ms.openlocfilehash: ecd8e757e1724fcd4c08540559eab75f1e4bed46
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62374614"
---
# <a name="compiler-warning-level-1-c4662"></a>컴파일러 경고(수준 1) C4662

명시적 인스턴스화. 템플릿-클래스 'identifier1'에 'identifier2'를 특수화하는 데 사용된 정의가 없습니다.

지정된 템플릿-클래스가 선언되었지만 정의되지 않았습니다.

## <a name="example"></a>예제

```
// C4662.cpp
// compile with: /W1 /LD
template<class T, int i> class MyClass; // no definition
template MyClass< int, 1>;              // C4662
```