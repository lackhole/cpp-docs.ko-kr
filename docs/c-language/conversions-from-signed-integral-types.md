---
title: 부호 있는 정수 계열 형식에서 변환
ms.date: 10/02/2019
helpviewer_keywords:
- integral conversions, from signed
- integers, converting
- conversions [C++], integral
- data type conversion [C++], signed and unsigned integers
- type conversion [C++], signed and unsigned integers
ms.assetid: 5eea32f8-8b14-413d-acac-c063b3d118d7
ms.openlocfilehash: 79608b5ca4335ee3c30bdab27e7efade5b7e2f54
ms.sourcegitcommit: c51b2c665849479fa995bc3323a22ebe79d9d7ce
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/07/2019
ms.locfileid: "71998728"
---
# <a name="conversions-from-signed-integral-types"></a>부호 있는 정수 계열 형식에서 변환

부호 있는 정수가 정수 또는 부동 소수점 형식으로 변환 될 때 결과 형식에서 원래 값을 표현할 수 있으면 값이 변경 되지 않습니다.

부호 있는 정수를 더 큰 크기의 정수로 변환 하는 경우 값은 부호 확장입니다. 더 작은 크기의 정수로 변환할 경우 상위 비트가 잘립니다. 결과는 다음 예제와 같이 결과 형식을 사용 하 여 해석 됩니다.

```C
int i = -3;
unsigned short u;

u = i;
printf_s( "%hu\n", u );  // Prints 65533
```

부호 있는 정수를 부동 소수점 형식으로 변환할 때 원래 값이 결과 형식에서 정확 하 게 표현할 수 없는 경우 결과는 다음으로 높거나 낮은 표현 가능한 값입니다.

정수 계열 및 부동 소수점 형식의 크기에 대 한 자세한 내용은 [기본 형식의 저장소](../c-language/storage-of-basic-types.md)를 참조 하세요.

다음 표에서는 부호 있는 정수 계열 형식으로부터의 변환을 요약하여 보여 줍니다. 기본적으로 **char** 형식에 서명 된 것으로 가정 합니다. 컴파일 시간 옵션을 사용 하 여 **char** 형식의 기본값을 unsigned로 변경 하면이 테이블의 변환 대신 부호 없는 **문자** 형식에 대 한 [부호 없는 정수 형식](../c-language/conversions-from-unsigned-integral-types.md) 테이블의 변환에서 지정 된 변환이 적용 됩니다.

**Microsoft 전용**

Microsoft 컴파일러에서 **int** 와 **long** 은 고유 하지만 동일한 형식입니다. **Int** 값의 변환은 **long**의 변환과 같은 방식으로 진행 됩니다.

**Microsoft 전용 종료**

## <a name="table-of-conversions-from-signed-integral-types"></a>부호 있는 정수 계열 형식에서 변환 테이블

|보낸 사람|수행할 작업|메서드|
|----------|--------|------------|
|**문자**<sup>1</sup>|**short**|부호 확장|
|**char**|**long**|부호 확장|
|**char**|**long long**|부호 확장|
|**char**|**unsigned char**|패턴 유지(상위 비트가 부호 비트로의 기능을 잃음)|
|**char**|**unsigned short**|**short**로 부호 확장(**short**를 **unsigned short**로 변환)|
|**char**|**unsigned long**|**short**로 부호 확장(**long**을 **unsigned long**으로 변환)|
|**char**|**부호 없는 long long**|**Long long**으로 부호 확장 **long long** 을 **unsigned long long** 으로 변환 합니다.|
|**char**|**float**|**long**으로 부호 확장(**long**을 **float**로 변환)|
|**char**|**double**|**long**으로 부호 확장(**long**을 **double**로 변환)|
|**char**|**long double**|**long**으로 부호 확장(**long**을 **double**로 변환)|
|**short**|**char**|하위 바이트 유지|
|**short**|**long**|부호 확장|
|**short**|**long long**|부호 확장|
|**short**|**unsigned char**|하위 바이트 유지|
|**short**|**unsigned short**|비트 패턴 유지(상위 비트가 부호 비트로의 기능을 잃음)|
|**short**|**unsigned long**|**short**로 부호 확장(**long**을 **unsigned long**으로 변환)|
|**short**|**부호 없는 long long**|**Long long**으로 부호 확장 **long long** 을 **unsigned long long** 으로 변환 합니다.|
|**short**|**float**|**long**으로 부호 확장(**long**을 **float**로 변환)|
|**short**|**double**|**long**으로 부호 확장(**long**을 **double**로 변환)|
|**short**|**long double**|**long**으로 부호 확장(**long**을 **double**로 변환)|
|**long**|**char**|하위 바이트 유지|
|**long**|**short**|하위 단어 유지|
|**long**|**long long**|부호 확장|
|**long**|**unsigned char**|하위 바이트 유지|
|**long**|**unsigned short**|하위 단어 유지|
|**long**|**unsigned long**|비트 패턴 유지(상위 비트가 부호 비트로의 기능을 잃음)|
|**long**|**부호 없는 long long**|**Long long**으로 부호 확장 **long long** 을 **unsigned long long** 으로 변환 합니다.|
|**long**|**float**|**float**로 표시. **Long** 을 정확히 나타낼 수 없는 경우 일부 정밀도가 손실 됩니다.|
|**long**|**double**|**double**로 표시. **Long** 을 **double**로 정확히 나타낼 수 없는 경우 일부 정밀도가 손실 됩니다.|
|**long**|**long double**|**double**로 표시. **Long** 을 **double**로 정확히 나타낼 수 없는 경우 일부 정밀도가 손실 됩니다.|
|**long long**|**char**|하위 바이트 유지|
|**long long**|**short**|하위 단어 유지|
|**long long**|**long**|낮은 순서 dword 유지|
|**long long**|**unsigned char**|하위 바이트 유지|
|**long long**|**unsigned short**|하위 단어 유지|
|**long long**|**unsigned long**|낮은 순서 dword 유지|
|**long long**|**부호 없는 long long**|비트 패턴 유지(상위 비트가 부호 비트로의 기능을 잃음)|
|**long long**|**float**|**float**로 표시. **Long long** 을 정확 하 게 나타낼 수 없는 경우 일부 정밀도가 손실 됩니다.|
|**long long**|**double**|**double**로 표시. **Long long** 을 **double**로 정확히 나타낼 수 없는 경우 일부 정밀도가 손실 됩니다.|
|**long long**|**long double**|**double**로 표시. **Long long** 을 **double**로 정확히 나타낼 수 없는 경우 일부 정밀도가 손실 됩니다.|

<sup>1</sup> 모든 **문자** 항목은 **char** 형식이 기본적으로 서명 되어 있다고 가정 합니다.

## <a name="see-also"></a>참조

[할당 변환](../c-language/assignment-conversions.md)
