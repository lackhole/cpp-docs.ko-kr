---
title: '#line 지시문(C/C++)'
ms.date: 08/29/2019
f1_keywords:
- '#line'
helpviewer_keywords:
- preprocessor, directives
- line directive (#line)
- '#line directive'
ms.assetid: 585c1dc4-5184-4f01-98f4-80c1909744d7
ms.openlocfilehash: 35bee779ebf059c20d4a46e27b5ad4cbfb3ce5f3
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70220230"
---
# <a name="line-directive-cc"></a>#line 지시문 (C/C++)

**#Line** 지시문은 컴파일러의 내부적으로 저장 된 줄 번호와 파일 이름을 지정 된 줄 번호와 파일 이름으로 변경 하도록 전처리기에 지시 합니다.

## <a name="syntax"></a>구문

> **#line** *digit-sequence* ["*filename*"]

## <a name="remarks"></a>설명

컴파일러는 줄 번호와 선택적 파일 이름을 사용 하 여 컴파일하는 동안 발견 된 오류를 참조 합니다. 줄 번호는 일반적으로 현재 입력 줄을 참조 하 고, 파일 이름은 현재 입력 파일을 참조 합니다. 줄 번호는 각 줄이 처리 된 후에 증가 합니다.

*숫자 시퀀스* 값은 임의의 정수 상수일 수 있습니다. 전처리 토큰에 대해 매크로 대체가 수행 될 수 있지만 결과는 올바른 구문으로 계산 되어야 합니다. *파일 이름은* 모든 문자를 조합 하 여 사용할 수 있으며 큰따옴표 (`" "`)로 묶어야 합니다. *Filename* 을 생략 하면 이전 파일 이름이 변경 되지 않은 상태로 유지 됩니다.

**#Line** 지시어를 작성 하 여 소스 줄 번호와 파일 이름을 변경할 수 있습니다. 변환기는 줄 번호와 파일 이름을 사용 하 여 미리 정의 된 매크로 `__FILE__` 및 `__LINE__`의 값을 확인 합니다. 이러한 매크로를 사용 하 여 자체 설명 오류 메시지를 프로그램 텍스트에 삽입할 수 있습니다. 이러한 미리 정의 된 매크로에 대 한 자세한 내용은 [미리 정의 된 매크로](../preprocessor/predefined-macros.md)를 참조 하세요.

매크로 `__FILE__` 는 해당 내용이 파일 이름인 문자열로 확장 되며 큰따옴표 (`" "`)로 둘러싸여 있습니다.

줄 번호와 파일 이름을 변경 하는 경우 컴파일러는 이전 값을 무시 하 고 새 값을 사용 하 여 처리를 계속 합니다. **#Line** 지시문은 일반적으로 프로그램 생성기에서 생성 된 프로그램이 아닌 원래 원본 파일을 참조 하는 데 사용 됩니다.

다음 예에서는 **#line** 와 `__LINE__` 및 `__FILE__` 매크로를 보여 줍니다.

이 문에서 내부적으로 저장 된 줄 번호는 151으로 설정 되 고 filename은 copy. c로 변경 됩니다.

```C
#line 151 "copy.c"
```

이 예제에서 매크로 `ASSERT` 는 미리 정의 된 매크로 `__LINE__` 를 사용 `__FILE__` 하 고 지정 된 어설션이 true가 아니면 소스 파일에 대 한 오류 메시지를 인쇄 합니다.

```C
#define ASSERT(cond) if( !(cond) )\
{printf( "assertion error line %d, file(%s)\n", \
__LINE__, __FILE__ );}
```

## <a name="see-also"></a>참고자료

[전처리기 지시문](../preprocessor/preprocessor-directives.md)
