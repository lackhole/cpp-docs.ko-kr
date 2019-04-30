---
title: 컴파일러 오류 C3418
ms.date: 11/04/2016
f1_keywords:
- C3418
helpviewer_keywords:
- C3418
ms.assetid: 54042c04-3c45-41c1-bad7-90f9ee05a21b
ms.openlocfilehash: 8456e9b17b72cd4ac98349d2f2871a1c59f56911
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62311497"
---
# <a name="compiler-error-c3418"></a>컴파일러 오류 C3418

액세스 지정자 'specifier'는 지원되지 않습니다.

CLR 액세스 지정자를 잘못 지정했습니다.  자세한 내용은 형식 표시 유형 및 멤버 표시 여부를 참조 하세요. [방법: 클래스 및 구조체 정의 및 사용 (C++/CLI)](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md)합니다.

## <a name="example"></a>예제

다음 샘플에서는 C3418을 생성합니다.

```cpp
// C3418.cpp
// compile with: /clr /c
ref struct m {
internal public:   // C3418
   void test(){}
};

ref struct n {
internal:   // OK
   void test(){}
};
```