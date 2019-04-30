---
title: 컴파일러 오류 C2833
ms.date: 11/04/2016
f1_keywords:
- C2833
helpviewer_keywords:
- C2833
ms.assetid: b9418ce1-e2ee-4599-8959-6fde89c27569
ms.openlocfilehash: dad6a64f145c3d49d3b43044ea76a11d35827943
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62408370"
---
# <a name="compiler-error-c2833"></a>컴파일러 오류 C2833

'operator o'를 인식할 수 있는 연산자 또는 형식이 아닙니다.

단어 `operator` 재정의 하려는 연산자나 변환 하려는 형식을 따라야 합니다.

관리 되는 형식에서 정의할 수 있는 연산자 목록을 참조 하세요 [사용자 정의 연산자](../../dotnet/user-defined-operators-cpp-cli.md)합니다.

다음 샘플에서는 C2833 오류가 생성 됩니다.

```
// C2833.cpp
// compile with: /c
class A {};

void operator ::* ();   // C2833
void operator :: ();   // OK
```