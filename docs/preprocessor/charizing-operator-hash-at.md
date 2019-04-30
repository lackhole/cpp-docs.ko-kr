---
title: Charizing 연산자 (#@)
ms.date: 11/04/2016
f1_keywords:
- '#@'
helpviewer_keywords:
- preprocessor, operators
- charizing operator
- '#@ preprocessor operator'
ms.assetid: dee03314-d27c-4063-965c-64756efbef22
ms.openlocfilehash: c9acc9b9872e096cd441b950632c341e975fecb8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62403531"
---
# <a name="charizing-operator-"></a>Charizing 연산자 (#@)
**Microsoft 전용**

charizing 연산자는 매크로의 인수에만 사용할 수 있습니다. 경우 `#@` 정식 매개 변수 앞에 매크로의 정의에서 실제 인수는 작은따옴표로 묶인 및 매크로 확장 되 면 문자로 처리 합니다. 예를 들어:

```
#define makechar(x)  #@x
```

위의 정의는 다음 문이

```
a = makechar(b);
```

다음과 같이 확장되게 합니다.

```
a = 'b';
```

작은따옴표는 charizing 연산자와 함께 사용할 수 없습니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[전처리기 연산자](../preprocessor/preprocessor-operators.md)