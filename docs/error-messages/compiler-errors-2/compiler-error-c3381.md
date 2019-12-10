---
title: 컴파일러 오류 C3381
ms.date: 11/04/2016
f1_keywords:
- C3381
helpviewer_keywords:
- C3381
ms.assetid: d276c89f-8377-4cb6-a8d4-7770885f06c4
ms.openlocfilehash: eadc9b45b4cd4f2d9b533f387dadd66be8acc963
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74749570"
---
# <a name="compiler-error-c3381"></a>컴파일러 오류 C3381

' assembly ': 어셈블리 액세스 지정자는/clr 옵션으로 컴파일한 코드 에서만 사용할 수 있습니다.

네이티브 형식은 어셈블리 외부에서 볼 수 있지만 **/clr** 컴파일에서 네이티브 형식에 대 한 어셈블리 액세스만 지정할 수 있습니다.

자세한 내용은 [형식 표시](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility) 유형 및 [/Clr (공용 언어 런타임 컴파일)](../../build/reference/clr-common-language-runtime-compilation.md)를 참조 하세요.

## <a name="example"></a>예제

다음 샘플에서는 C3381를 생성 합니다.

```cpp
// C3381.cpp
// compile with: /c
public class A {};   // C3381
```
