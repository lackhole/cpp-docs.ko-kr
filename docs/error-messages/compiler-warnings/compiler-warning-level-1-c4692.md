---
title: 컴파일러 경고(수준 1) C4692
ms.date: 11/04/2016
f1_keywords:
- C4692
helpviewer_keywords:
- C4692
ms.assetid: f6fb3acc-8228-491a-9c30-ce302d8a9c75
ms.openlocfilehash: d013990d0d56c028f48928d1b48c2e0a66b393af
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62221268"
---
# <a name="compiler-warning-level-1-c4692"></a>컴파일러 경고(수준 1) C4692

'function': 전용이 아닌 멤버의 시그니처에 어셈블리 전용 네이티브 형식 'native_type'이(가) 있습니다.

어셈블리 외부에 표시 된 형식 어셈블리 외부에 표시 되지 않는 네이티브 형식이 포함 된 시그니처는 멤버 함수를 포함 합니다. 따라서 포함 하는 형식 어셈블리 외부에서 인스턴스화된 경우 멤버 함수가 호출 되지 해야 합니다.

자세한 내용은 [표시 유형 입력](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility)합니다.

기본적으로 이 경고는 해제되어 있습니다. 자세한 내용은 [Compiler Warnings That Are Off by Default](../../preprocessor/compiler-warnings-that-are-off-by-default.md)을 참조하세요.

## <a name="example"></a>예제

다음 샘플 C4692를 생성합니다.

```
// C4692.cpp
// compile with: /W1 /c /clr
#pragma warning(default:4692)
class Private_Native_Class {};
public class Public_Native_Class {};
public ref class Public_Ref_Class {
public:
   void Test(Private_Native_Class *) {}   // C4692
   void Test2(Public_Native_Class *) {}   // OK
};
```