---
title: 컴파일러 오류 C3836
ms.date: 11/04/2016
f1_keywords:
- C3836
helpviewer_keywords:
- C3836
ms.assetid: 254f851b-7b7d-4c34-a740-fcf72f6a636a
ms.openlocfilehash: 33860273db07894a9a4d15ba6d578598a18819ee
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62208059"
---
# <a name="compiler-error-c3836"></a>컴파일러 오류 C3836

정적 생성자는 멤버 이니셜라이저 목록을 사용할 수 없습니다.

관리 되는 클래스 멤버 초기화 목록도 포함 하는 정적 생성자를 사용할 수 없습니다. 정적 클래스 생성자는 클래스 초기화, 정적 데이터 멤버 초기화를 수행 하려면 공용 언어 런타임에 의해 호출 됩니다.

## <a name="example"></a>예제

다음 샘플에서는 C3836 오류가 생성 됩니다.

```
// C3836a.cpp
// compile with: /clr
ref class M
{
   static int s_i;

public:
   static M() :  s_i(1234)   // C3836, delete initializer to resolve
   {
   }
};

int main()
{
}
```
