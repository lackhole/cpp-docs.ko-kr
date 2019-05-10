---
title: 심각한 오류 C1191
ms.date: 11/04/2016
f1_keywords:
- C1191
helpviewer_keywords:
- C1191
ms.assetid: 2888c6c4-b4e6-449e-8ee0-7917f31086df
ms.openlocfilehash: 89af73699120ee4d8af3cda746727d758ef6d22c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62228886"
---
# <a name="fatal-error-c1191"></a>심각한 오류 C1191

'dll' 전역 범위 에서만 가져올 수 있습니다.

/Clr 프로그래밍을 사용 하는 프로그램에 mscorlib.dll을 가져오는 명령 수 없습니다. 네임 스페이스 또는 함수에 나타나지만 전역 범위에 표시 되어야 합니다.

다음 샘플에서는 C1191 오류가 생성 됩니다.

```
// C1191.cpp
// compile with: /clr
namespace sample {
   #using <mscorlib.dll>   // C1191 not at global scope
}
```

해결 방법:

```
// C1191b.cpp
// compile with: /clr /c
#using <mscorlib.dll>
namespace sample {}
```