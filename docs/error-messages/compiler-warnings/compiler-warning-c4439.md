---
title: 컴파일러 경고 C4439
ms.date: 11/04/2016
f1_keywords:
- C4439
helpviewer_keywords:
- C4439
ms.assetid: 9449958f-f407-4824-829b-9e092f2af97d
ms.openlocfilehash: d604c234b9445a7e5304118124620f0057f30975
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62311347"
---
# <a name="compiler-warning-c4439"></a>컴파일러 경고 C4439

'function': 시그니처에 관리 되는 형식 사용 하 여 함수 정의는 __clrcall 호출 규칙이 있어야 합니다.

컴파일러는 암시적으로 호출 규칙으로 대체 [__clrcall](../../cpp/clrcall.md)합니다. 이 경고를 해결 하려면 제거 합니다 `__cdecl` 또는 `__stdcall` 호출 규칙입니다.

C4439은 항상 오류로 실행 됩니다. 사용 하 여이 경고를 해제할 수 있습니다 합니다 `#pragma warning` 나 **/wd**; 참조 [경고](../../preprocessor/warning.md) 또는 [/w, / w0, / w1, / w2, / w3, / w4, / w1, / w2, / w3, / w4, /Wall, /wd, / we, /wo, /Wv, /WX (경고 수준)](../../build/reference/compiler-option-warning-level.md)자세한 내용은 합니다.

## <a name="example"></a>예제

다음 샘플 C4439를 생성합니다.

```
// C4439.cpp
// compile with: /clr
void __stdcall f( System::String^ arg ) {}   // C4439
void __clrcall f2( System::String^ arg ) {}   // OK
void f3( System::String^ arg ) {}   // OK
```