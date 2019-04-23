---
title: '#undef 지시문 (C /C++)'
ms.date: 11/04/2016
f1_keywords:
- '#undef'
helpviewer_keywords:
- '#undef directive'
- undef directive (#undef)
- preprocessor, directives
ms.assetid: 88900e0e-2c19-4a63-b681-f3d3133c24ca
ms.openlocfilehash: 4f4f5ce244be6d7f4e13d7a2abc5d21232c08d9d
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59039009"
---
# <a name="undef-directive-cc"></a>#undef 지시문 (C/C++)
전에 `#define`으로 만든 이름을 제거(정의 해제)합니다.

## <a name="syntax"></a>구문

```
#undef
identifier
```

## <a name="remarks"></a>설명

합니다 **#undef** 의 현재 정의 제거 하는 지시문 *식별자*합니다. 따라서 다음에 나타나는 *식별자* 전처리기에서 무시 됩니다. 사용 하 여 매크로 정의 제거할 **#undef**, 지정는 매크로만 *식별자* ; 매개 변수 목록을 제공 하지 마십시오.

적용할 수도 있습니다는 **#undef** 지시문을 이전 정의가 없는 식별자입니다. 그러면 식별자가 정의되지 않습니다. 매크로 대체 내에서 수행 되지 않습니다 **#undef** 문입니다.

합니다 **#undef** 지시문은 일반적으로 연결 되는 `#define` 식별자는 특별 한 의미 있는 소스 프로그램에서 영역을 만들기 위한 지시문을 합니다. 예를 들어, 소스 프로그램의 특정한 함수가 매니페스트 상수를 사용하여 프로그램의 나머지 부분에 영향을 주지 않는 환경 관련 값을 정의할 수 있습니다. **#undef** 지시문도 협력 합니다 `#if` 지시문을 소스 프로그램의 조건부 컴파일을 제어 합니다. 참조 [#if, #elif, #else 및 #endif 지시문](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md) 자세한 내용은 합니다.

다음 예제에서는 **#undef** 지시문이 기호 상수 및 매크로의 정의 제거 합니다. 매크로의 식별자만 제공됩니다.

```
#define WIDTH 80
#define ADD( X, Y ) ((X) + (Y))
.
.
.
#undef WIDTH
#undef ADD
```

**Microsoft 전용**

매크로 사용 하 여 명령줄에서 정의 되지 않은 상태일 수는 `/U` 옵션에 정의 되지 않은 매크로 이름 뒤에 있습니다. 이 명령을 실행의 결과의 시퀀스와 동일 `#undef` *매크로 이름을* 파일 시작 부분에서 설명 합니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[전처리기 지시문](../preprocessor/preprocessor-directives.md)