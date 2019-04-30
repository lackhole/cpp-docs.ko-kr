---
title: 컴파일러 오류 C2017
ms.date: 11/04/2016
f1_keywords:
- C2017
helpviewer_keywords:
- C2017
ms.assetid: 1083eed9-9906-4a97-883c-54e52d7e82cd
ms.openlocfilehash: f4a17557e5e4ca1eb3f69561c964c9bbe24bb70d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62303785"
---
# <a name="compiler-error-c2017"></a>컴파일러 오류 C2017

잘못 된 이스케이프 시퀀스

예: \t 이스케이프 시퀀스를 문자 또는 문자열 외부에서 나타난 상수입니다.

다음 샘플에서는 C2017 오류가 생성 됩니다.

```
// C2017.cpp
int main() {
   char test1='a'\n;   // C2017
   char test2='a\n';   // ok
}
```

C2017은 이스케이프 시퀀스가 포함 된 문자열을 사용 하 여 문자열 화 연산자를 사용 하는 경우에 발생할 수 있습니다.

다음 샘플에서는 C2017 오류가 생성 됩니다.

```
// C2017b.cpp
#define TestDfn(x) AfxMessageBox(#x)
TestDfn(CString("\\") + CString(".h\"\n\n"));   // C2017
```