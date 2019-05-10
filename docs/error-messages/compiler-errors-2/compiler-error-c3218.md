---
title: 컴파일러 오류 C3218
ms.date: 11/04/2016
f1_keywords:
- C3218
helpviewer_keywords:
- C3218
ms.assetid: 0eea19e0-503e-4e07-ae8b-2cb2e95922cd
ms.openlocfilehash: 87084f9751b1593ec93a3062f23714bba403da9a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62182524"
---
# <a name="compiler-error-c3218"></a>컴파일러 오류 C3218

'type': 형식은 제약 조건으로 사용할 수 없습니다

제약 조건에 형식에 대 한 관리 되는 클래스 또는 인터페이스에 대 한 참조 또는 값 형식 이어야 합니다.

## <a name="example"></a>예제

다음 샘플 C3218를 생성합니다.

```
// C3218.cpp
// compile with: /clr /c
class A {};
ref class B {};

// Delete the following 3 lines to resolve.
generic <class T>
where T : A   // C3218
ref class C {};

// OK
generic <class T>
where  T : B
ref class D {};
```