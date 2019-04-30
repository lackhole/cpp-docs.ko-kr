---
title: 컴파일러 경고 C4368
ms.date: 11/04/2016
f1_keywords:
- C4368
helpviewer_keywords:
- C4368
ms.assetid: cb85bcee-fd3d-4aa5-b626-2324f07a4f1b
ms.openlocfilehash: b2af1166738d867c84ff4ebae832f831af7940ff
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62311500"
---
# <a name="compiler-warning-c4368"></a>컴파일러 경고 C4368

'member' 관리 되는 'type'의 멤버로 정의할 수 없습니다: 혼합된 형식은 지원 되지 않습니다

CLR 형식에서 네이티브 데이터 멤버를 포함할 수 없습니다.

하지만 네이티브 형식에 대한 포인터를 선언하고, 관리 클래스의 생성자 및 소멸자와 종료자에서 해당 수명을 제어할 수 있습니다. 자세한 내용은 참조 [소멸자 및 종료자](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers)합니다.

항상이 경고는 오류로 발생 됩니다. 사용 된 [경고](../../preprocessor/warning.md) pragma C4368를 사용 하지 않도록 설정 합니다.

## <a name="example"></a>예제

다음 샘플 C4368를 생성합니다.

```
// C4368.cpp
// compile with: /clr /c
struct N {};
ref struct O {};
ref struct R {
    R() : m_p( new N ) {}
    ~R() { delete m_p; }

   property N prop;   // C4368
   int i[10];   // C4368

   property O ^ prop2;   // OK
   N * m_p;   // OK
};
```