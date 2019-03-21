---
title: SBCS 및 MBCS 데이터 형식
ms.date: 04/11/2018
f1_keywords:
- MBCS
- SBCS
helpviewer_keywords:
- SBCS and MBCS data types
- data types [C], MBCS and SBCS
ms.assetid: 4c3ef9da-e397-48d4-800e-49dba36db171
ms.openlocfilehash: 2d73155e36909efb1a7261f9fe45c2431525437a
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57742913"
---
# <a name="sbcs-and-mbcs-data-types"></a>SBCS 및 MBCS 데이터 형식

하나의 멀티바이트 문자 또는 1바이트의 멀티바이트 문자만 처리하는 Microsoft MBCS 런타임 라이브러리 루틴에는 `unsigned int` 인수가 필요합니다. 여기서 0x00 <= 문자 값은 <= 0xFFFF이고, 0x00 <= 바이트 값은 <= 0xFF입니다. 문자열 컨텍스트에서 멀티바이트 바이트 또는 문자를 처리하는 MBCS 루틴에서는 멀티바이트 문자열을 `unsigned char` 포인터로 표현해야 합니다.

> [!CAUTION]
> 멀티바이트 문자의 각 바이트는 8비트 **char**로 표현될 수 있습니다. 그러나 값이 0x7F보다 큰 **char** 형식의 SBCS 또는 MBCS 싱글바이트 문자는 음수입니다. 이러한 문자가 **int** 또는 **long**으로 직접 변환되면, 결과는 컴파일러에서 부호 확장되므로 예기치 않은 결과가 발생할 수 있습니다.

따라서 멀티바이트 문자의 바이트를 8비트 `unsigned char`로 표현하는 것이 가장 좋습니다. 또는 음수 결과를 방지하기 위해 **char** 형식의 싱글바이트 문자를 먼저 `unsigned char`로 변환한 다음, **int** 또는 **long**으로 변환합니다.

일부 SBCS 문자열 처리 함수는 (signed) **char**<strong>\*</strong> 매개 변수를 사용하기 때문에 **_MBCS**가 정의되면 형식 불일치 컴파일러 경고가 발생합니다. 이 경고를 피하기 위한 세 가지 방법이 유용성 순서대로 나열됩니다.

1. TCHAR.H에 형식이 안전한 인라인 함수를 사용합니다. 이것은 기본적인 동작입니다.

1. 명령줄에서 **_MB_MAP_DIRECT**를 정의하여 TCHAR.H에 직접 매크로를 사용합니다. 이렇게 하는 경우 형식을 수동으로 일치시켜야 합니다. 이는 속도가 가장 빠른 방법이지만 형식이 안전하지 않습니다.

1. TCHAR.H에 형식이 안전한 정적 링크 라이브러리 함수를 사용합니다. 이렇게 하려면 명령줄에서 **_NO_INLINING** 상수를 정의합니다. 이는 속도가 가장 느린 방법이지만 형식은 가장 안전합니다.

## <a name="see-also"></a>참고 항목

[국제화](../c-runtime-library/internationalization.md)<br/>
[범주별 유버니설 C 런타임 루틴](../c-runtime-library/run-time-routines-by-category.md)<br/>
