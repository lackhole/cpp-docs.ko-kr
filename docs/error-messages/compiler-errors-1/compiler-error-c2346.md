---
title: 컴파일러 오류 C2346
ms.date: 11/04/2016
f1_keywords:
- C2346
helpviewer_keywords:
- C2346
ms.assetid: 246145be-5645-4cd6-867c-e3bc39e33dca
ms.openlocfilehash: a6d75ca671e22203cb40ca18de21606834eeefa8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62188093"
---
# <a name="compiler-error-c2346"></a>컴파일러 오류 C2346

'function' 네이티브로 컴파일할 수 없습니다: 이유

컴파일러는 함수를 MSIL로 컴파일할 수 없습니다.

자세한 내용은 [관리 되는, 관리 되지 않는](../../preprocessor/managed-unmanaged.md) 하 고 [/clr (공용 언어 런타임 컴파일)](../../build/reference/clr-common-language-runtime-compilation.md)합니다.

### <a name="to-correct-this-error"></a>이 오류를 해결하려면

1. MSIL로 컴파일할 수 없는 함수에서 코드를 제거 합니다.

1. 사용 하 여 모듈을 컴파일되지 않습니다 하나 **/clr**, 또는 관리 되지 않는 pragma를 사용 하 여 관리 되지 않는 함수로 표시 합니다.

## <a name="example"></a>예제

다음 샘플 C2346를 생성합니다.

```
// C2346.cpp
// processor: x86
// compile with: /clr
// C2346 expected
struct S
{
   S()
   {
      { __asm { nop } }
   }
   virtual __clrcall ~S() { }
};

void main()
{
   S s;
}
```