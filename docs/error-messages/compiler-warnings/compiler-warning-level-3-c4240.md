---
title: 컴파일러 경고 (수준 3) C4240
ms.date: 11/04/2016
f1_keywords:
- C4240
helpviewer_keywords:
- C4240
ms.assetid: a2657cdb-18e1-493f-882b-4e10c0bca71d
ms.openlocfilehash: 3636e902e8d6ecd34cdc3e1135761c8595dc5998
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/13/2019
ms.locfileid: "74051751"
---
# <a name="compiler-warning-level-3-c4240"></a>컴파일러 경고 (수준 3) C4240

비표준 확장이 사용 됨: ' classname '에 대 한 액세스가 이제 ' 액세스 지정자 '로 정의 되었습니다. 이전에 ' access 지정자 '로 정의 되었습니다.

ANSI 호환성 ([/za](../../build/reference/za-ze-disable-language-extensions.md))에서 중첩 된 클래스에 대 한 액세스를 변경할 수 없습니다. 기본 Microsoft 확장 (/Ze)에서이 경고를 사용할 수 있습니다.

## <a name="example"></a>예제

```cpp
// C4240.cpp
// compile with: /W3
class X
{
private:
   class N;
public:
   class N
   {   // C4240
   };
};

int main()
{
}
```