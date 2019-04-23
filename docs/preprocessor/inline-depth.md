---
title: inline_depth
ms.date: 11/04/2016
f1_keywords:
- inline_depth_CPP
- vc-pragma.inline_depth
helpviewer_keywords:
- pragmas, inline_depth
- inline_depth pragma
ms.assetid: 2bba60fe-43ea-4d09-90f7-aafaba3bad07
ms.openlocfilehash: 18d772c8a9f6218ed3afaa385f214445bd0fe8e6
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59039022"
---
# <a name="inlinedepth"></a>inline_depth
인라인 추론 검색 수준을, 지정 된 수준 (의 호출 그래프) 보다 큰 경우 함수가 인라인 될가 되도록 *n*합니다.

## <a name="syntax"></a>구문

```
#pragma inline_depth( [n] )
```

## <a name="remarks"></a>설명

이 pragma 제어는 표시 된 함수의 인라이닝을 [인라인](../cpp/inline-functions-cpp.md) 및 [__inline](../cpp/inline-functions-cpp.md) 으로 인라인 처리 된 또는 `/Ob2` 옵션입니다.

*n* 0과 255, 255는 호출 그래프의 수준이 무제한을 의미 하 고 0 인라인 확장을 금지 있는 사이의 값일 수 있습니다.  때 *n* 지정 하지 않으면 기본값 (254)이 사용 됩니다.

합니다 **inline_depth** pragma는 일련의 함수 호출을 확장할 수 있습니다 하는 횟수를 제어 합니다. 예를 들어, 인라인 깊이가 4개이고 A가 B를 호출한 후 B가 C를 호출할 경우 3개의 호출이 모두 인라인 확장됩니다. 그러나 최대 인라인 확장이 2개일 경우 A와 B만 확장되고 C는 함수 호출로 남게 됩니다.

이 pragma를 사용 하려면 설정 해야 합니다 `/Ob` 컴파일러 옵션 1 또는 2로 합니다. 이 pragma를 사용하여 설정한 깊이는 pragma 뒤에 오는 첫 번째 함수 호출에 적용됩니다.

인라인 깊이는 확장하는 동안 감소할 수 있지만 증가하지 않습니다. 인라인 깊이가 6이 고 전처리기 확장 하는 동안 발생 하는 경우는 **inline_depth** pragma 값이 8 깊이를 6으로 유지 됩니다.

합니다 **inline_depth** pragma로 표시 된 함수에 영향을 주지 `__forceinline`합니다.

> [!NOTE]
> 재귀 함수는 최대 16 깊이의 호출까지 인라인을 대체할 수 있습니다.

## <a name="see-also"></a>참고자료

[Pragma 지시문 및 __Pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)<br/>
[inline_recursion](../preprocessor/inline-recursion.md)