---
title: 컴파일러 오류 C2017
ms.date: 11/04/2016
f1_keywords:
- C2017
helpviewer_keywords:
- C2017
ms.assetid: 1083eed9-9906-4a97-883c-54e52d7e82cd
ms.openlocfilehash: 3911ef9af2eb0fab7d0f9296ddce8a0f9b32ae0d
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74751055"
---
# <a name="compiler-error-c2017"></a>컴파일러 오류 C2017

이스케이프 시퀀스가 잘못 되었습니다.

이스케이프 시퀀스 (예: \t)는 문자 또는 문자열 상수 외부에 표시 됩니다.

다음 샘플에서는 C2017를 생성 합니다.

```cpp
// C2017.cpp
int main() {
   char test1='a'\n;   // C2017
   char test2='a\n';   // ok
}
```

문자열 화 연산자가 이스케이프 시퀀스를 포함 하는 문자열과 함께 사용 되는 경우에 발생할 수 있습니다.

다음 샘플에서는 C2017를 생성 합니다.

```cpp
// C2017b.cpp
#define TestDfn(x) AfxMessageBox(#x)
TestDfn(CString("\\") + CString(".h\"\n\n"));   // C2017
```
