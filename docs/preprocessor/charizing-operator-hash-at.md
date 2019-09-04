---
title: Charizing 연산자(#@)
ms.date: 08/29/2019
f1_keywords:
- '#@'
helpviewer_keywords:
- preprocessor, operators
- charizing operator
- '#@ preprocessor operator'
ms.assetid: dee03314-d27c-4063-965c-64756efbef22
ms.openlocfilehash: cb2a4e07287edf5ed2d0850ec7d870c8ef307879
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70218539"
---
# <a name="charizing-operator-"></a>Charizing 연산자(#@)

**Microsoft 전용**

charizing 연산자는 매크로의 인수에만 사용할 수 있습니다. 가 매크로 정의의 정식 매개 변수 앞에오면실제인수는작은따옴표로묶이고매크로가확장될때문자로처리됩니다.`#@` 예:

```cpp
#define makechar(x)  #@x
```

위의 정의는 다음 문이

```cpp
a = makechar(b);
```

다음과 같이 확장되게 합니다.

```cpp
a = 'b';
```

작은따옴표 문자 (`'`)는 charizing 연산자와 함께 사용할 수 없습니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[전처리기 연산자](../preprocessor/preprocessor-operators.md)
