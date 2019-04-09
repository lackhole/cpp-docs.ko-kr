---
title: 컴파일러 경고 (수준 4) C4061
ms.date: 04/05/2019
f1_keywords:
- C4061
helpviewer_keywords:
- C4061
ms.assetid: a99cf88e-7941-4519-8b1b-f6889d914b2f
ms.openlocfilehash: 073e3e9cb1cb5bb6b0f66157c986072227960212
ms.sourcegitcommit: 35c4b3478f8cc310ebbd932a18963ad8ab846ed9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59237122"
---
# <a name="compiler-warning-level-4-c4061"></a>컴파일러 경고 (수준 4) C4061

> 열거자 '*식별자*'의 switch에 '*열거형*' case 레이블에 의해 명시적으로 처리 하지 않습니다

지정한 열거자 *식별자* 연결된 처리기에는 `switch` 문이 있는 `default` 사례입니다. 누락 된 사례를 감독 수 또는 문제가 아닐 수 있습니다. 열거자 default 문에서 처리는 여부에 따라 달라 집니다 수 있습니다. 사용 되지 않는 열거자에 관련된 경고에 대 한 `switch` 되지 않은 문을 `default` 사례를 참조 하십시오 [C4062](compiler-warning-level-4-c4062.md)합니다.

기본적으로 이 경고는 해제되어 있습니다. 기본적으로 해제 되어 있는 경고를 사용 하는 방법에 대 한 자세한 내용은 참조 하세요. [컴파일러 경고는 기본적으로 해제 되어](../../preprocessor/compiler-warnings-that-are-off-by-default.md)입니다.

## <a name="example"></a>예제

다음 샘플에서는 C4061; 문제를 해결 하려면 누락 된 열거자에 대 한 사례를 추가 합니다.

```cpp
// C4061.cpp
// compile with: /W4
#pragma warning(default : 4061)

enum E { a, b, c };
void func ( E e )
{
   switch(e)
   {
      case a:
      case b:
      default:
         break;
   }   // C4061 c' not handled
}

int main()
{
}
```

## <a name="see-also"></a>참고자료

[컴파일러 경고(수준 4) C4062](compiler-warning-level-4-c4062.md)
