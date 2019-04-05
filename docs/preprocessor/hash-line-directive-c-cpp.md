---
title: '#줄 지시문 (C/c + +)'
ms.date: 10/18/2017
f1_keywords:
- '#line'
helpviewer_keywords:
- preprocessor, directives
- line directive (#line)
- '#line directive'
ms.assetid: 585c1dc4-5184-4f01-98f4-80c1909744d7
ms.openlocfilehash: ad0fe1514e89b861bab046652b1768862cc8045b
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59023739"
---
# <a name="line-directive-cc"></a>#line 지시문 (C/C++)

합니다 **#line** 지시문에는 지정 된 줄 번호 및 파일 이름에는 컴파일러의 내부적으로 저장 된 줄 번호와 파일 이름을 변경 하도록 전처리기에 지시 합니다.

## <a name="syntax"></a>구문

> **#line** *digit-sequence* ["*filename*"]

## <a name="remarks"></a>설명

컴파일러의 줄 번호 및 선택적 파일 이름 사용 하 여 컴파일하는 동안 발견 된 오류를 참조 하세요. 줄 번호를 일반적으로 현재 입력된 줄을 나타내며 현재 입력된 파일에 파일 이름을 나타냅니다. 줄 번호는 각 행이 처리 되 면 증가 합니다.

합니다 *숫자 시퀀스* 모든 정수 상수 값일 수 있습니다. 전처리 토큰에서 매크로 대체를 수행할 수 있지만 결과 올바른 구문으로 계산 되어야 합니다. 합니다 *filename* 문자의 조합일 수 있습니다 하 고 큰따옴표로 묶어야 합니다 (**""**). 하는 경우 *filename* 는 생략 하면 이전 파일 이름은 변경 되지 않습니다.

소스 줄 번호와 파일 이름을 작성 하 여 변경할 수 있습니다는 **#line** 지시문입니다. 변환기의 줄 번호 및 파일 이름을 사용 하 여 미리 정의 된 매크로의 값을 확인 하려면 `__FILE__` 고 `__LINE__`입니다. 자체 설명적 오류 메시지의 프로그램 텍스트를 삽입할 이러한 매크로 사용할 수 있습니다. 이러한 미리 정의 된 매크로에 대 한 자세한 내용은 참조 하세요. [미리 정의 된 매크로](../preprocessor/predefined-macros.md)합니다.

합니다 `__FILE__` 매크로 내용이 큰따옴표로 묶은 파일 이름 문자열로 확장 됩니다 (**""**).

줄 번호와 파일 이름을 변경 하면 컴파일러 이전 값을 무시 하 고 새 값으로 처리를 계속 합니다. 합니다 **#line** 지시문은 일반적으로 생성 된 프로그램 대신 원래 원본 파일을 참조 하는 오류 메시지를 프로그램 생성기에서 사용 됩니다.

다음 예제에 나와 **#line** 하며 `__LINE__` 고 `__FILE__` 매크로입니다.

이 문을 151를 내부적으로 저장 된 줄 번호 설정 되 고 filename copy.c로 변경 됩니다.

```cpp
#line 151 "copy.c"
```

이 예제에서는 매크로 `ASSERT` 미리 정의 된 매크로 사용 하 여 `__LINE__` 및 `__FILE__` 지정된 어설션을 true가 아니면 소스 파일에 대 한 오류 메시지를 인쇄 합니다.

```cpp
#define ASSERT(cond) if( !(cond) )\
{printf( "assertion error line %d, file(%s)\n", \
__LINE__, __FILE__ );}
```

## <a name="see-also"></a>참고자료

[전처리기 지시문](../preprocessor/preprocessor-directives.md)