---
title: 컴파일러 경고(수준 4) C4337
ms.date: 11/04/2016
f1_keywords:
- C4337
helpviewer_keywords:
- C4337
ms.assetid: 70bc72d9-aac5-45cd-abd3-ebe42a05897b
ms.openlocfilehash: f86d03e30e2776a8dae4cf56032c45d0022ca01d
ms.sourcegitcommit: d0504e2337bb671e78ec6dd1c7b05d89e7adf6a7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2019
ms.locfileid: "74683305"
---
# <a name="compiler-warning-level-4-c4337"></a>컴파일러 경고(수준 4) C4337

' typelib2 '의 상호 참조 된 형식 라이브러리 ' typelib1 '를 자동으로 가져옵니다.

[#Import 지시문](../../preprocessor/hash-import-directive-cpp.md) 의 auto_search 특성으로 인해 형식 라이브러리를 암시적으로 가져왔습니다.

다음 두 파일에서 만든 디스크에 두 개의 형식 라이브러리가 지정 됩니다 (midl로 컴파일).

```
// C4337a.idl
[
  uuid(F87070BA-C6D9-405C-A8E4-8CD9CA25C12B)
]
library C4337aLib
{
   [uuid(F87070BA-C6D9-405C-A8E4-8CD9CA25C12C)]
   enum E_C4337a
   {
      one = 0,
      two = 1,
      three = 2
    };
};
```

그런 다음 두 번째 .idl 파일

```
// C4337b.idl
[
   uuid(F87070BA-C6D9-405C-A8E4-8CD9CA25C12D)
]

library C4337bLib
{
   importlib("c4337a.tlb");

   [uuid(F87070BA-C6D9-405C-A8E4-8CD9CA25C12E)]
   struct S_C4337b
   {
      enum E_C4337a e;
   };
};
```

다음 샘플에서는 C4337를 생성 합니다.

```cpp
// C4337.cpp
// compile with: /W4 /LD
#import "c4337b.tlb" auto_search   // C4337
// explicitly #import all type libraries to resolve
// #import "C4337a.tlb"
// #import "C4337b.tlb"
```