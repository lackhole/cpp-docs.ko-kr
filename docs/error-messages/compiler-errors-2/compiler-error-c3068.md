---
title: 컴파일러 오류 C3068
ms.date: 11/04/2016
f1_keywords:
- C3068
helpviewer_keywords:
- C3068
ms.assetid: 613e3447-b4a8-4268-a661-297bed63ccdf
ms.openlocfilehash: 4790c9caafd28722f3631104cfe5cfc762cf6426
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62406888"
---
# <a name="compiler-error-c3068"></a>컴파일러 오류 C3068

'function': 'naked' 함수는 해제가 필요한 개체를 포함할 수 없습니다는 C++ 예외가 발생 했습니다.

컴파일러에서 스택 해제를 수행할 수 없습니다.는 [naked](../../cpp/naked-cpp.md) 함수에서 임시 개체 생성 되었기 때문에 예외가 발생 하는 함수 및 C++ 예외 처리 ([/EHsc](../../build/reference/eh-exception-handling-model.md))가 지정 합니다.

이 오류를 해결 하려면 다음 중 적어도 하나를 수행 합니다.

- /EHsc를 사용 하 여 컴파일되지 않습니다.

- 이 함수를 표시 하지 마십시오. `naked`합니다.

- 함수에서 임시 개체를 만들지 마십시오.

경우는 예외를 throw 하는 경우 함수 스택에 임시 개체를 만듭니다 C++ 예외 처리를 사용 하면 예외가 throw 되 면 컴파일러는 스택 정리 됩니다.

예외가 throw 됩니다, 컴파일러에서 생성 한 코드를 프롤로그 호출을 에필로그와 naked 함수에 존재 하지 않는 함수에 대 한 실행 됩니다.

## <a name="example"></a>예제

다음 샘플에서는 C3068 오류가 생성 됩니다.

```
// C3068.cpp
// compile with: /EHsc
// processor: x86
class A {
public:
   A(){}
   ~A(){}
};

void b(A){}

__declspec(naked) void c() {
   b(A());   // C3068
};
```