---
title: 컴파일러 오류 C3080
ms.date: 11/04/2016
f1_keywords:
- C3080
helpviewer_keywords:
- C3080
ms.assetid: ff62a3f7-9b3b-44bd-b8d9-f3a8e5354560
ms.openlocfilehash: 5b610d54331349c53ff01f5c09bb53ff52216c26
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62406667"
---
# <a name="compiler-error-c3080"></a>컴파일러 오류 C3080

'finalizer_function': 종료자에는 스토리지 클래스 지정자를 사용할 수 없습니다.

자세한 내용은 참조 하세요. [소멸자 및 종료자 방법에서: 클래스 및 구조체 정의 및 사용 (C++/CLI)](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers)합니다.

## <a name="example"></a>예제

다음 샘플에서는 C3080을 생성합니다.

```
// C3080.cpp
// compile with: /clr /c
ref struct rs {
protected:
   static !rs(){}   // C3080
   !rs(){}   // OK
};
```