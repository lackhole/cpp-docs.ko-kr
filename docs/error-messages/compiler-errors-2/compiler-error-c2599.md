---
title: 컴파일러 오류 C2599
ms.date: 11/04/2016
f1_keywords:
- C2599
helpviewer_keywords:
- C2599
ms.assetid: 88515f36-7589-47e2-862e-0de8b18d6668
ms.openlocfilehash: 872c3a66d4738c1a69990dffdbbc59cee9e90002
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62395471"
---
# <a name="compiler-error-c2599"></a>컴파일러 오류 C2599

'enum': 열거형의 정방향 선언은 허용 되지 않습니다

컴파일러는 더 이상 관리 되는 열거형의 정방향 선언을 지원합니다.

열거형의 정방향 선언은 허용 되지 않습니다 [/Za](../../build/reference/za-ze-disable-language-extensions.md)합니다.

다음 샘플에서는 C2599를 생성합니다.

```
// C2599.cpp
// compile with: /clr /c
enum class Status;   // C2599

enum class Status2 { stop2, hold2, go2};

ref struct MyStruct {
   // Delete the following line to resolve.
   Status m_status;

   Status2 m_status2;   // OK
};

enum class Status { stop, hold, go };
```