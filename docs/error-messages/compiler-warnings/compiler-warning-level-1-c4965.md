---
title: 컴파일러 경고 (수준 1) C4965
ms.date: 11/04/2016
f1_keywords:
- C4965
helpviewer_keywords:
- C4965
ms.assetid: 47f3f6dc-459b-4a25-9947-f394c8966cb5
ms.openlocfilehash: ac1ffc1626a8b72fd7c9026afb6c6a54bace3750
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/13/2019
ms.locfileid: "74052228"
---
# <a name="compiler-warning-level-1-c4965"></a>컴파일러 경고 (수준 1) C4965

정수 0의 암시적 상자 nullptr 또는 명시적 캐스트 사용

시각적 C++ 기능은 값 형식의 암시적 boxing을 제공 합니다. 이제 관리 되는 확장을 C++ 사용 하 여 null 할당을 발생 시킨 명령은 boxed int에 할당 됩니다.

자세한 내용은 [boxing](../../extensions/boxing-cpp-component-extensions.md)에 정의된 인터페이스의 private C++ 관련 구현입니다.

## <a name="example"></a>예제

다음 샘플에서는 C4965를 생성 합니다.

```cpp
// C4965.cpp
// compile with: /clr /W1
int main() {
   System::Object ^o = 0;   // C4965

   // the previous line is the same as the following line
   // using Managed Extensions for C++
   // System::Object *o = __box(0);

   // OK
   System::Object ^o2 = nullptr;
   System::Object ^o3 = safe_cast<System::Object^>(0);
}
```