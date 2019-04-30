---
title: 컴파일러 오류 C2897
ms.date: 11/04/2016
f1_keywords:
- C2897
helpviewer_keywords:
- C2897
ms.assetid: a88349e2-823f-42a0-8660-0653b677afa4
ms.openlocfilehash: 264ad52a10c6cf19d1105561f1140cf2d3e2f8e6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62378845"
---
# <a name="compiler-error-c2897"></a>컴파일러 오류 C2897

소멸자/종료자는 함수 템플릿일 수 없습니다.

소멸자 또는 종료자 오버 로드할 수 없습니다, 소멸자 (있는 소멸자의 집합을 정의)를 템플릿으로 선언 허용 되지 않습니다.

다음 샘플에서는 C2897를 생성합니다.

## <a name="example"></a>예제

다음 샘플 C2897를 생성합니다.

```
// C2897.cpp
// compile with: /c
class X {
public:
   template<typename T> ~X() {}   // C2897
};
```

## <a name="example"></a>예제

다음 샘플 C2897를 생성합니다.

```
// C2897_b.cpp
// compile with: /c /clr
ref struct R2 {
protected:
   template<typename T> !R2(){}   // C2897 error
};
```