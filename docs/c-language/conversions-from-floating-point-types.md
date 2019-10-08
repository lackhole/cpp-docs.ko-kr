---
title: 부동 소수점 형식에서 변환
ms.date: 10/02/2019
helpviewer_keywords:
- converting floating point
- floating-point conversion
ms.assetid: 96804c8e-fa3b-4742-9006-0082ed9e57f2
ms.openlocfilehash: c2f7c25015b36545f969796a1f85d355d715427a
ms.sourcegitcommit: c51b2c665849479fa995bc3323a22ebe79d9d7ce
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/07/2019
ms.locfileid: "71998696"
---
# <a name="conversions-from-floating-point-types"></a>부동 소수점 형식에서 변환

다른 부동 소수점 형식으로 변환 된 부동 소수점 값은 원래 값을 결과 형식에서 정확 하 게 표현할 수 있는 경우 값이 변경 되지 않습니다. 원래 값이 numeric 이지만 정확 하 게 표현할 수 없는 경우 결과는 다음으로 크거나 그 다음으로 표현할 수 있는 값 중 하나입니다. 부동 소수점 형식의 범위에 대해서는 [부동 소수점 상수에](../c-language/limits-on-floating-point-constants.md) 대 한 제한을 참조 하세요.

정수 계열 형식으로 변환 된 부동 소수점 값은 먼저 소수 값을 삭제 하 여 잘립니다. 이 잘린 값을 결과 형식에서 표현할 수 있는 경우 결과는 해당 값 이어야 합니다. 표현할 수 없는 경우 결과 값은 정의 되지 않습니다.

**Microsoft 전용**

Microsoft 컴파일러는 **부동 소수점** 값에는 IEEE-754 binary32 표현을 사용 하 고 **long double** 및 **double**에는 binary64 표현을 사용 합니다. **Long double** 과 **double** 은 같은 표현을 사용 하므로 범위와 전체 자릿수가 동일 합니다.

컴파일러가 **double** 또는 **long double** 부동 소수점 숫자를 **float**로 변환 하는 경우 부동 소수점 환경 컨트롤에 따라 결과를 반올림 합니다 .이 컨트롤의 기본값은 "가장 가까운 수로 반올림, 균등 하 게 연결"입니다. 숫자 값이 너무 크거나 너무 커서 숫자 **float** 값으로 나타낼 수 없는 경우, 변환 결과는 원래 값의 부호에 따라 양수 또는 음의 무한대가 되 고, 사용 하도록 설정 된 경우 오버플로 예외가 발생 합니다.

정수 형식으로 변환할 때 **long** 보다 작은 형식으로 변환 하는 결과는 값을 **long**으로 변환한 다음 결과 형식으로 변환 하는 결과입니다.

**Long**이상으로 정수 형식으로 변환 하는 경우 결과 형식에서 나타낼 수 없는 너무 크거나 너무 낮은 값을 변환 하면 다음과 같은 값을 반환할 수 있습니다.

- 결과는 0부터 가장 먼 표현할 수 있는 값인 *센티널 값일*수 있습니다. 부호 있는 형식의 경우 가장 낮은 표현 가능한 값 (0x800 ... 0). 부호 없는 형식의 경우 표현할 수 있는 가장 높은 값입니다 (0xFF ... F).

- 결과는 *포화*상태일 수 있습니다. 값이 너무 높으면 표현할 수 있는 가장 높은 값으로 변환 되 고, 값이 너무 낮으면 표현할 수 있는 가장 낮은 값으로 변환 됩니다. 이러한 두 값 중 하나가 센티널 값으로도 사용 됩니다.

- **Unsigned long** 또는 **unsigned long long**으로 변환 하는 경우 범위를 벗어난 값을 변환 하는 결과는 가장 높거나 가장 낮은 값이 아닌 값이 될 수 있습니다. 결과가 센티널 또는 포화 값 인지 여부는 컴파일러 옵션 및 대상 아키텍처에 따라 달라 집니다. 이후 컴파일러 릴리스에서는 대신 포화 또는 센티널 값을 반환할 수 있습니다.

**Microsoft 전용 종료**

다음 표에서는 부동 형식의 변환을 요약합니다.

## <a name="table-of-conversions-from-floating-point-types"></a>부동 소수점 형식에서의 변환 표

|보낸 사람|수행할 작업|메서드|
|----------|--------|------------|
|**float**|**char**|**long**으로 변환, **long**을 **char**로 변환|
|**float**|**short**|**long**으로 변환, **long**을 **short**로 변환|
|**float**|**int**|소수점에서 자릅니다. 결과가 너무 커서 **int**로 나타낼 수 없는 경우 결과가 정의 되지 않습니다.|
|**float**|**long**|소수점에서 자릅니다. 결과가 커서 **long**으로 나타낼 수 없는 경우 결과가 정의되지 않습니다.|
|**float**|**long long**|소수점에서 자릅니다. 결과가 너무 커서 **long long**으로 표현할 수 없는 경우 결과가 정의 되지 않습니다.|
|**float**|**unsigned char**|**Long**으로 변환 **long** 을 **unsigned 문자로** 변환|
|**float**|**unsigned short**|**long**으로 변환, **long**을 **unsigned short**로 변환|
|**float**|**unsigned**|소수점에서 자릅니다. 결과가 너무 커서 **unsigned**로 나타낼 수 없는 경우 결과가 정의 되지 않습니다.|
|**float**|**unsigned long**|소수점에서 자릅니다. 결과가 너무 커서 **unsigned long**으로 표현할 수 없는 경우 결과가 정의 되지 않습니다.|
|**float**|**부호 없는 long long**|소수점에서 자릅니다. 결과가 너무 커서 **부호 없는 long long**으로 표현할 수 없는 경우 결과가 정의 되지 않습니다.|
|**float**|**double**|**Double**로 나타냅니다.|
|**float**|**long double**|**Long double**로 나타냅니다.|
|**double**|**char**|**float**로 변환, **float**를 **char**로 변환|
|**double**|**short**|**float**로 변환, **float**를 **short**로 변환|
|**double**|**int**|소수점에서 자릅니다. 결과가 너무 커서 **int**로 나타낼 수 없는 경우 결과가 정의 되지 않습니다.|
|**double**|**long**|소수점에서 자릅니다. 결과가 커서 **long**으로 나타낼 수 없는 경우 결과가 정의되지 않습니다.|
|**double**|**unsigned char**|**Long**으로 변환 **long** 을 **unsigned 문자로** 변환|
|**double**|**unsigned short**|**long**으로 변환, **long**을 **unsigned short**로 변환|
|**double**|**unsigned**|소수점에서 자릅니다. 결과가 너무 커서 **unsigned**로 나타낼 수 없는 경우 결과가 정의 되지 않습니다.|
|**double**|**unsigned long**|소수점에서 자릅니다. 결과가 너무 커서 **unsigned long**으로 표현할 수 없는 경우 결과가 정의 되지 않습니다.|
|**double**|**부호 없는 long long**|소수점에서 자릅니다. 결과가 너무 커서 **부호 없는 long long**으로 표현할 수 없는 경우 결과가 정의 되지 않습니다.|
|**double**|**float**|**float**로 나타냅니다. **Double** 값을 **float**로 정확 하 게 표현할 수 없는 경우 정밀도가 손실 됩니다. 갓이 커서 **float**로 나타낼 수 없으면 결과가 정의되지 않습니다.|
|**double**|**long double**|**long double** 값은 **double**로 처리됩니다.|

**Long double** 에서의 변환은 **double**으로부터의 변환과 동일한 메서드를 따릅니다.

## <a name="see-also"></a>참조

[할당 변환](../c-language/assignment-conversions.md)
