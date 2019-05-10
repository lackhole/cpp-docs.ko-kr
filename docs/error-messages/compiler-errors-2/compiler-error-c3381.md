---
title: 컴파일러 오류 C3381
ms.date: 11/04/2016
f1_keywords:
- C3381
helpviewer_keywords:
- C3381
ms.assetid: d276c89f-8377-4cb6-a8d4-7770885f06c4
ms.openlocfilehash: ae416d68831d1964c89d938dfcddd364e521195c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62328866"
---
# <a name="compiler-error-c3381"></a>컴파일러 오류 C3381

'assembly': 어셈블리 액세스 지정자는 /clr 옵션으로 컴파일된 코드에서 사용할 수 있습니다만

네이티브 형식을 어셈블리 외부에서 볼 수 있지만 네이티브 형식에 대 한 어셈블리 액세스를 하나만 지정할 수 있습니다는 **/clr** 컴파일.

자세한 내용은 참조 하세요. [표시 유형 입력](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility) 하 고 [/clr (공용 언어 런타임 컴파일)](../../build/reference/clr-common-language-runtime-compilation.md)합니다.

## <a name="example"></a>예제

다음 샘플 C3381를 생성합니다.

```
// C3381.cpp
// compile with: /c
public class A {};   // C3381
```