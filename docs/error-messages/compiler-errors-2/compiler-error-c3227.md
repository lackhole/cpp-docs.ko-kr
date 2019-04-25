---
title: 컴파일러 오류 C3227
ms.date: 11/04/2016
f1_keywords:
- C3227
helpviewer_keywords:
- C3227
ms.assetid: 7939c23a-96c8-43c2-89e9-f217d132d155
ms.openlocfilehash: b175b14af55a9a462e040f064cc6e38d13fffb94
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62173992"
---
# <a name="compiler-error-c3227"></a>컴파일러 오류 C3227

'parameter': 'keyword'를 사용 하 여 제네릭 형식에 할당할 수 없습니다.

형식을 인스턴스화할는 적절 한 생성자가 필요 합니다. 그러나 컴파일러는 적절 한 생성자를 사용할 수 있는지 확인할 수 없습니다.

이 오류를 해결 하려면 템플릿을 제네릭 대신 사용할 수 있습니다 또는 형식의 인스턴스를 만드는 여러 방법 중 하나를 사용할 수 있습니다.

## <a name="example"></a>예제

다음 샘플 C3227를 생성합니다.

```
// C3227.cpp
// compile with: /clr /c
generic<class T> interface class ICreate {
   static T Create();
};

generic <class T>
where T : ICreate<T>
ref class C {
   void f() {
      T t = new T;   // C3227

      // OK
      T t2 = ICreate<T>::Create();
      T t3 = safe_cast<T>( System::Activator::CreateInstance(T::typeid) );
   }
};
```