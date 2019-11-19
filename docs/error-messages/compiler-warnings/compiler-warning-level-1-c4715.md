---
title: 컴파일러 경고 (수준 1) C4715
ms.date: 11/04/2016
f1_keywords:
- C4715
helpviewer_keywords:
- C4715
ms.assetid: 1c819bf7-0d8b-4f5e-b338-9cc292870439
ms.openlocfilehash: 268a26f5de1bb7f757a8e7cba6d3f5e6ddff882e
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/13/2019
ms.locfileid: "74052472"
---
# <a name="compiler-warning-level-1-c4715"></a>컴파일러 경고 (수준 1) C4715

' function ': 모든 제어 경로에서 값을 반환 하는 것은 아닙니다.

지정 된 함수는 잠재적으로 값을 반환할 수 없습니다.

## <a name="example"></a>예제

```cpp
// C4715a.cpp
// compile with: /W1 /LD
int func1( int i )
{
   if( i )
   return 3;  // C4715 warning, nothing returned if i == 0
}
```

이 경고를 방지 하려면 모든 경로가 반환 값을 함수에 할당 하도록 코드를 수정 합니다.

```cpp
// C4715b.cpp
// compile with: /LD
int func1( int i )
{
   if( i ) return 3;
   else return 0;     // OK, always returns a value
}
```

다음 예제와 같이 코드가 반환 하지 않는 함수에 대 한 호출을 포함할 수 있습니다.

```cpp
// C4715c.cpp
// compile with: /W1 /LD
void fatal()
{
}
int glue()
{
   if(0)
      return 1;
   else if(0)
      return 0;
   else
      fatal();   // C4715
}
```

컴파일러는 `fatal` 반환 되지 않는다는 것을 인식 하지 못하기 때문에이 코드는 경고를 생성 합니다. 이 코드가 오류 메시지를 생성 하지 않도록 하려면 [__declspec (noreturn)](../../cpp/noreturn.md)를 사용 하 여 `fatal`를 선언 합니다.