---
title: 컴파일러 경고(수준 3) C4240
ms.date: 11/04/2016
f1_keywords:
- C4240
helpviewer_keywords:
- C4240
ms.assetid: a2657cdb-18e1-493f-882b-4e10c0bca71d
ms.openlocfilehash: fe5306cc7909138fea0159553b53c2adc6a46dc0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62402218"
---
# <a name="compiler-warning-level-3-c4240"></a>컴파일러 경고(수준 3) C4240

비표준 확장이 사용 됨: 이제 정의 이전에 ' 액세스 지정자', 'classname'에 대 한 액세스 '액세스 지정자'로 정의 된

ANSI 호환성 ([/Za](../../build/reference/za-ze-disable-language-extensions.md)), 중첩 된 클래스에 대 한 액세스를 변경할 수 없습니다. 기본 Microsoft 확장 (/Ze)에서는 수를이 경고를 사용 하 여.

## <a name="example"></a>예제

```
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