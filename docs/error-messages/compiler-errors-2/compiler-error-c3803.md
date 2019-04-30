---
title: 컴파일러 오류 C3803
ms.date: 11/04/2016
f1_keywords:
- C3803
helpviewer_keywords:
- C3803
ms.assetid: bad5fb9a-ed9a-4c15-96e7-cf06e200a50d
ms.openlocfilehash: f6c255ec18d6dcf94f3ec022f09b173c2c66a1dd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62400099"
---
# <a name="compiler-error-c3803"></a>컴파일러 오류 C3803

'property': 속성이 해당 접근자 'accessor' 중 하나를 사용 하 여 호환 되지 않는 형식

정의 된 속성의 형식은 [속성](../../cpp/property-cpp.md) 해당 접근자 함수 중 하나에 대 한 반환 형식과 일치 하지 않습니다.

다음 샘플에서는 C3803 오류가 생성 됩니다.

```
// C3803.cpp
struct A
{
   __declspec(property(get=GetIt)) int i;
   char GetIt()
   {
      return 0;
   }

   /*
   // try the following definition instead
   int GetIt()
   {
      return 0;
   }
   */
}; // C3803

int main()
{
}
```