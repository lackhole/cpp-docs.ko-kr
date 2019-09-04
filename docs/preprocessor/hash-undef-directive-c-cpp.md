---
title: '#undef 지시문(C/C++)'
ms.date: 08/29/2019
f1_keywords:
- '#undef'
helpviewer_keywords:
- '#undef directive'
- undef directive (#undef)
- preprocessor, directives
ms.assetid: 88900e0e-2c19-4a63-b681-f3d3133c24ca
ms.openlocfilehash: 1a69bc568579e7da7c7e3816cb67c8153b8f1a27
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70220210"
---
# <a name="undef-directive-cc"></a>#undef 지시문 (C/C++)

전에 `#define`으로 만든 이름을 제거(정의 해제)합니다.

## <a name="syntax"></a>구문

> **#undef** *식별자*

## <a name="remarks"></a>설명

**#Undef** 지시문은 *식별자*의 현재 정의를 제거 합니다. 따라서 이후에 발생 하는 *식별자* 는 전처리기에서 무시 됩니다. **#Undef**를 사용 하 여 매크로 정의를 제거 하려면 매개 변수 목록이 아니라 매크로 *식별자*만 제공 합니다.

이전 정의가 없는 식별자에 **#undef** 지시어를 적용할 수도 있습니다. 그러면 식별자가 정의되지 않습니다. **#Undef** 문 내에서는 매크로 대체가 수행 되지 않습니다.

일반적으로 **#undef** 지시문은 식별자가 특별 `#define` 한 의미를 갖는 소스 프로그램에서 영역을 만들기 위해 지시문과 쌍을 이룹니다. 예를 들어, 소스 프로그램의 특정한 함수가 매니페스트 상수를 사용하여 프로그램의 나머지 부분에 영향을 주지 않는 환경 관련 값을 정의할 수 있습니다. 또한 **#undef** 지시문은 `#if` 지시문과 함께 작동 하 여 소스 프로그램의 조건부 컴파일을 제어 합니다. 자세한 내용은 [#if, #elif, #else 및 #endif 지시문](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)을 참조 하세요.

다음 예제에서 **#undef** 지시문은 기호화 된 상수 및 매크로의 정의를 제거 합니다. 매크로의 식별자만 제공됩니다.

```C
#define WIDTH 80
#define ADD( X, Y ) ((X) + (Y))
.
.
.
#undef WIDTH
#undef ADD
```

**Microsoft 전용**

명령줄에서 `/U` 옵션을 사용 하 여 매크로 이름을 정의 하지 않고 매크로 이름을 정의 하지 않을 수 있습니다. 이 명령을 실행 하는 영향은 파일의 시작 부분에 있는 `#undef` *매크로 이름* 문의 시퀀스와 동일 합니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[전처리기 지시문](../preprocessor/preprocessor-directives.md)
