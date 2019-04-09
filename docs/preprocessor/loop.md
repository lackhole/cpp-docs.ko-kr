---
title: 루프
ms.date: 10/18/2018
f1_keywords:
- loop_CPP
- vc-pragma.loop
ms.assetid: 6d5bb428-cead-47e7-941d-7513bbb162c7
ms.openlocfilehash: a1640881d98073381a941478f4b78177a95698d7
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59023168"
---
# <a name="loop"></a>루프

자동 평행화 도우미에서 루프 코드를 고려하는 방법을 제어하고 자동 벡터화 도우미에서 루프를 고려 대상에서 제외합니다.

## <a name="syntax"></a>구문

```
#pragma loop( hint_parallel(n) )
#pragma loop( no_vector )
#pragma loop( ivdep )
```

### <a name="parameters"></a>매개 변수

*hint_parallel(n)*<br/>
이 루프가 평행 화 되어야 하는 컴파일러에는 힌트 *n* 스레드, 여기서 *n* 양의 정수 리터럴 또는 0입니다. 하는 경우 *n* 가 0 이면 런타임에 최대 스레드 수가 사용 됩니다. 이는 명령이 아니라 컴파일러에 대한 힌트이며 루프가 평행화된다는 보장은 없습니다. 루프에 데이터 종속성 또는 구조적 문제(예: 루프 본문을 벗어나 사용되는 스칼라에 루프가 저장함)가 있는 경우에는 루프가 평행화되지 않습니다.

컴파일러는 경우가 아니면이 옵션을 무시 합니다 [/Qpar](../build/reference/qpar-auto-parallelizer.md) 컴파일러 스위치를 지정 합니다.

*no_vector*<br/>
기본적으로 자동 벡터화 도우미는 설정되어 있으며 혜택이 있는 것으로 평가되는 모든 루프를 벡터화하려고 합니다. 다음 루프에 대해 자동 벡터화 도우미를 사용하지 않으려면 이 pragma를 지정하십시오.

*ivdep*<br/>
이 루프에 대한 벡터 종속성을 무시할 것을 알리는 컴파일러에 대한 힌트입니다. 이 사용 하 여 함께에서 *hint_parallel*합니다.

## <a name="remarks"></a>설명

사용 하는 **루프** pragma를 바로 앞에 배치-아니라-루프 정의 합니다. 그러면 pragma가 뒤에 오는 루프의 범위에 적용됩니다. 순서에 상관없이 루프에 여러 pragma를 적용할 수 있지만 각 pragma를 별도의 pragma 문에 지정해야 합니다.

## <a name="see-also"></a>참고자료

[자동 병렬화 및 자동 벡터화](../parallel/auto-parallelization-and-auto-vectorization.md)<br/>
[Pragma 지시문 및 __Pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)