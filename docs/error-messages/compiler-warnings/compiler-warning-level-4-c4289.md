---
title: 컴파일러 경고(수준 4) C4289
ms.date: 11/04/2016
f1_keywords:
- C4289
helpviewer_keywords:
- C4289
ms.assetid: 0dbd2863-4cde-4e16-894b-104a2d5fa724
ms.openlocfilehash: cc1a22065be6d5f7f49d6c32f6bc9b6479399e29
ms.sourcegitcommit: 3ee06ec53153cf21910fc8cfef78a4f25f9633f3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2019
ms.locfileid: "74541964"
---
# <a name="compiler-warning-level-4-c4289"></a>컴파일러 경고(수준 4) C4289

비표준 확장이 사용됨 : 'var' : for 루프에서 선언된 루프 제어 변수가 for 루프 범위 외부에서 사용되었습니다.

[/Ze](../../build/reference/za-ze-disable-language-extensions.md) 및 **/zc: forScope-** 를 사용 하 여 컴파일하는 경우 [for 루프에서](../../cpp/for-statement-cpp.md) 선언 된 변수 **는 for 루프**범위 다음에 사용 되었습니다.

**/Ze**를 사용 하는 **for** 루프에서 표준 동작을 지정 하는 방법에 대 한 자세한 내용은 [/zc: forScope](../../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) 를 참조 하세요.

기본적으로 이 경고는 해제되어 있습니다. 자세한 내용은 [기본적으로 해제되어 있는 컴파일러 경고](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 를 참조하세요.

다음 샘플에서는 C4289를 생성 합니다.

```cpp
// C4289.cpp
// compile with: /W4 /Zc:forScope-
#pragma warning(default:4289)
int main() {
   for (int i = 0 ; ; )   // C4289
      break;
   i++;
}
```