---
title: 컴파일러 오류 C2062
ms.date: 11/04/2016
f1_keywords:
- C2062
helpviewer_keywords:
- C2062
ms.assetid: 6cc98353-2ddf-43ab-88a2-9cc91cdd6033
ms.openlocfilehash: dcfac9629a90b82744f87ec105c30301b2102cdf
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62408747"
---
# <a name="compiler-error-c2062"></a>컴파일러 오류 C2062

'type' 예기치 않은 입력

컴파일러는 형식 이름을 예상 하지 않은 합니다.

다음 샘플에서는 C2062를 생성합니다.

```
// C2062.cpp
// compile with: /c
struct A {  : int l; };   // C2062
struct B { private: int l; };   // OK
```

C2062도 발생할 수 있습니다 컴파일러는 방식으로 인해 생성자의 매개 변수 목록에 정의 되지 않은 형식을 처리 합니다. 컴파일러는 정의 되지 않은 (철자 틀림된)? 형식을 발견 하는 경우 생성자는 식 및 c2062 가정 합니다. 를 해결 하려면만 생성자 매개 변수 목록에 정의 된 형식을 사용 합니다.