---
title: 컴파일러 경고 (수준 1) C4042
ms.date: 11/04/2016
f1_keywords:
- C4042
helpviewer_keywords:
- C4042
ms.assetid: e4bd861b-1194-426b-bf79-68c5b021eb0a
ms.openlocfilehash: db7f0425c3752c20ca8c5d4b6c95845ff64475c5
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2019
ms.locfileid: "73627030"
---
# <a name="compiler-warning-level-1-c4042"></a>컴파일러 경고 (수준 1) C4042

' identifier ': 저장소 클래스가 잘못 되었습니다.

이 컨텍스트에서는 지정 된 저장소 클래스를이 식별자와 함께 사용할 수 없습니다. 컴파일러는 기본 저장소 클래스를 대신 사용 합니다.

- *식별자* 가 함수인 경우 `extern`합니다.

- **auto**, *식별자* 가 정식 매개 변수 또는 지역 변수입니다.

- *식별자* 가 전역 변수인 경우 저장소 클래스가 없습니다.

이 경고는 매개 변수 선언에 **register** 이외의 저장소 클래스를 지정 하 여 발생할 수 있습니다.

다음 샘플에서는 C4042를 생성 합니다.

```cpp
// C4042.cpp
// compile with: /W1 /LD
int func2( __declspec( thread ) int tls_i )    // C4042
// try the following line instead
// int func2( int tls_i )
{
   return tls_i;
}
```