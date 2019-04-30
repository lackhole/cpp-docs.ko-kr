---
title: auto_inline
ms.date: 11/04/2016
f1_keywords:
- auto_inline_CPP
- vc-pragma.auto_inline
helpviewer_keywords:
- pragmas, auto_inline
- auto_inline pragma
ms.assetid: f7624cd1-be76-429a-881c-65c9040acf43
ms.openlocfilehash: c59dcc8ec7749a91565d5af043b1bd9e9eaa16ea
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62403566"
---
# <a name="autoinline"></a>auto_inline
**auto_inline** pragma가 **off**로 지정된 범위 내의 함수는 인라인 자동화가 이루어지지 않도록 인라인 확장의 후보에서 제외시킵니다.

## <a name="syntax"></a>구문

```
#pragma auto_inline( [{on | off}] )
```

## <a name="remarks"></a>설명

**auto_inline** pragma를 사용하려면 함수 정의 후에 사용합니다. 함수 정의 안쪽에는 사용하지 않습니다. pragma를 지정된 이후 코드부터 함수 정의에서 pragma가 적용됩니다.

## <a name="see-also"></a>참고자료

[Pragma 지시문 및 __Pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)