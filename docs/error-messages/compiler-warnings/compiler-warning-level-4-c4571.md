---
title: 컴파일러 경고(수준 4) C4571
ms.date: 11/04/2016
f1_keywords:
- C4571
helpviewer_keywords:
- C4571
ms.assetid: 07aa17bd-b15c-4266-824c-57cc445e8edd
ms.openlocfilehash: 92164bf297a44871897b6c6150eb54f8c5ccf3cc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62220457"
---
# <a name="compiler-warning-level-4-c4571"></a>컴파일러 경고(수준 4) C4571

정보: 시각적 개체의 catch (...) 의미 체계가 변경 C++ 7.1; 구조적된 예외 (SEH) 변경 되었습니다.

로 컴파일하는 경우 모든부터 블록에 대해 생성 되는 C4571 **/EHs**합니다.

사용 하 여 컴파일하면 **/EHs**부터 블록 (예: null 포인터를 0으로 나누기); 구조화 된 예외를 catch 하지부터 블록을 명시적으로-발생 된 catch 됩니다 C++ 예외입니다.  자세한 내용은 [Visual C++에서 예외 처리](../../cpp/exception-handling-in-visual-cpp.md)를 참조하세요.

기본적으로 이 경고는 해제되어 있습니다.  이 경고가 표시 되도록 사용 하 여 컴파일하면 **/EHs** 구조적된 예외를 catch 하지 않으려는 사용자 (...) catch 블록입니다.  자세한 내용은 [기본적으로 해제되어 있는 컴파일러 경고](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 를 참조하세요.

다음 방법 중 하나를 C4571를 해결할 수 있습니다.

- 사용 하 여 컴파일하면 **/EHa** 구조화 된 예외를 catch 하 여 catch (...) 블록을 계속 하려는 경우.

- 구조화 된 예외를 catch 하 여부터 블록을 원하지 않는 하지만 블록을 사용 하려는 경우에 C4571를 사용 하지 마십시오.  여전히 구조적된 예외 처리 키워드를 사용 하 여 구조화 된 예외를 catch 할 수 있습니다 (**__try**하십시오 **__except**, 및 **__finally**).  하지만 기억를 컴파일하면 **/EHs** 소멸자 에서만 호출 되는 경우는 C++ SEH 예외가 발생할 때가 아니라 예외가 throw 됩니다.

- 특정 catch 블록으로 catch (...) 블록을으로 바꿉니다. C++ 예외를 필요에 따라 구조적된 예외 처리를 추가 하 고는 C++ 예외 처리 (**__try**, **__except**, 및 **__finally**).  참조 [구조적 예외 처리 (C /C++)](../../cpp/structured-exception-handling-c-cpp.md) 에 대 한 자세한 내용은 합니다.

참조 [/EH (예외 처리 모델)](../../build/reference/eh-exception-handling-model.md) 자세한 내용은 합니다.

## <a name="example"></a>예제

다음 샘플 C4571를 생성합니다.

```
// C4571.cpp
// compile with: /EHs /W4 /c
#pragma warning(default : 4571)
int main() {
   try {
      int i = 0, j = 1;
      j /= i;   // this will throw a SE (divide by zero)
   }
   catch(...) {}   // C4571 warning
}
```