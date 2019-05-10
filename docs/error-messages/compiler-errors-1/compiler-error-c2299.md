---
title: 컴파일러 오류 C2299
ms.date: 11/04/2016
f1_keywords:
- C2299
helpviewer_keywords:
- C2299
ms.assetid: d001c2bc-f6fd-47aa-8e42-0eb824d6441d
ms.openlocfilehash: 39659baebf7dc1859a69021f60ed452964ae61af
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2019
ms.locfileid: "65447950"
---
# <a name="compiler-error-c2299"></a>컴파일러 오류 C2299

'function': 동작 변경: 명시적 특수화는 복사 생성자 또는 복사 할당 연산자 수

이 오류는 Visual Studio 2005에 대해 수행한 컴파일러 규칙 작업의 결과로 생성 될 수 있습니다: 시각적 개체의 이전 버전 C++ 복사 생성자 또는 복사 할당 연산자에 대 한 명시적 특수화를 허용 합니다.

C2299를 해결 하려면 복사 생성자 또는 대입 연산자는 템플릿 함수 있지만 클래스 형식을 사용 하는 템플릿이 아닌 함수 대신 수행 하지 마세요. 템플릿 인수를 명시적으로 지정 하 여 복사 생성자 또는 대입 연산자를 호출 하는 모든 코드는 템플릿 인수를 제거 해야 합니다.

다음 샘플에서는 C2299 오류가 생성 됩니다.

```
// C2299.cpp
// compile with: /c
class C {
   template <class T>
   C (T t);

   template <> C (const C&);   // C2299
   C (const C&);   // OK
};
```