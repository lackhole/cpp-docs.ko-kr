---
title: 컴파일러 오류 C2429
ms.date: 11/16/2017
f1_keywords:
- C2429
helpviewer_keywords:
- C2429
ms.assetid: 57ff6df9-5cf1-49f3-8bd8-4e550dfd65a0
ms.openlocfilehash: 972ec6591132443ef4d1297598d6de7216f59663
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62165686"
---
# <a name="compiler-error-c2429"></a>컴파일러 오류 C2429

> '*언어 기능*'컴파일러 플래그 필요'*컴파일러 옵션*'

언어 기능 지원에 대 한 특정 컴파일러 옵션을 필요합니다.

오류 **C2429: 언어 기능 ' 중첩 된 네임 스페이스-정의 ' 컴파일러 플래그를 사용 하려면 ' / /std: c + + 17'** 정의 하려는 경우에 생성 되는 *복합 네임 스페이스*를 하나 이상 포함 하는 네임 스페이스 Visual Studio 2015 업데이트 5에 시작 되는 범위를 중첩 된 네임 스페이스 이름입니다. (Visual Studio 2017 버전 15.3에서에서 합니다 **/std: c + + 최신** 스위치가 필요 합니다.) 복합 네임 스페이스 정의에서 허용 되지 않습니다 C++ c++17 이전 합니다. 컴파일러가 복합 네임 스페이스 정의 지 원하는 경우는 [/std: c + + 17](../../build/reference/std-specify-language-standard-version.md) 컴파일러 옵션을 지정:

```cpp
// C2429a.cpp
namespace a::b { int i; } // C2429 starting in Visual C++ 2015 Update 3.
                          // Use /std:c++17 to fix, or do this:
// namespace a { namespace b { int i; }}

int main() {
   a::b::i = 2;
}
```
