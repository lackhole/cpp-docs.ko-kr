---
title: 컴파일러 경고 C4394
ms.date: 11/04/2016
f1_keywords:
- C4394
helpviewer_keywords:
- C4394
ms.assetid: 5de94de0-17e3-4e7c-92f4-5c3c1b825120
ms.openlocfilehash: 00c9e139e920473590389c05f076a7cd91a4fb8d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62311480"
---
# <a name="compiler-warning-c4394"></a>컴파일러 경고 C4394

'function': appdomain 별 기호는 __declspec (dllexport)로 표시할 수 없습니다

로 표시 한 함수를 [appdomain](../../cpp/appdomain.md) `__declspec` 한정자 (필요가 네이티브), MSIL 및 내보내기 테이블에 컴파일됩니다 ([내보내기](../../windows/export.md) `__declspec` 한정자) 관리 되는 함수에 대 한 지원 되지 않습니다.

공용 액세스 가능성을 갖도록 관리되는 함수를 선언할 수 있습니다. 자세한 내용은 참조 하세요. [표시 유형 입력](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility) 하 고 [멤버 표시 유형](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Member_visibility)합니다.

C4394은 항상 오류로 실행 됩니다.  사용 하 여이 경고를 해제할 수 있습니다 합니다 `#pragma warning` 나 **/wd**; 참조 [경고](../../preprocessor/warning.md) 또는 [/w, / w0, / w1, / w2, / w3, / w4, / w1, / w2, / w3, / w4, /Wall, /wd, / we, /wo, /Wv, /WX (경고 수준)](../../build/reference/compiler-option-warning-level.md)자세한 내용은 합니다.

## <a name="example"></a>예제

다음 샘플 C4394를 생성합니다.

```
// C4394.cpp
// compile with: /clr /c
__declspec(dllexport) __declspec(appdomain) int g1 = 0;   // C4394
__declspec(dllexport) int g2 = 0;   // OK
```