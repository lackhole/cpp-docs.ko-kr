---
title: strict_gs_check
ms.date: 11/04/2016
f1_keywords:
- strict_gs_check
- strict_gs_check_CPP
helpviewer_keywords:
- strict_gs_check pragma
ms.assetid: decfec81-c916-42e0-a07f-8cc26df6a7ce
ms.openlocfilehash: b62e1be466e65c0de6fb4eaa33ac6e99915529e6
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59037807"
---
# <a name="strictgscheck"></a>strict_gs_check

이 pragma는 향상된 보안 검사를 제공합니다.

## <a name="syntax"></a>구문

```
#pragma strict_gs_check([push,] on )
#pragma strict_gs_check([push,] off )
#pragma strict_gs_check(pop)
```

## <a name="remarks"></a>설명

스택 기반 버퍼 오버런의 일부 범주를 감지하는 데 도움이 되는 임의의 쿠키를 함수 스택에 삽입하도록 컴파일러에 지시합니다. 기본적으로 `/GS` 컴파일러 옵션 (버퍼 보안 검사) 모든 함수에 대 한 쿠키를 삽입 하지 않습니다. 자세한 내용은 [/GS(버퍼 보안 검사)](../build/reference/gs-buffer-security-check.md)를 참조하세요.

사용 하 여 컴파일해야 `/GS` (버퍼 보안 검사) 사용 하도록 설정 하려면 **strict_gs_check**합니다.

잠재적으로 유해한 데이터에 노출되는 코드 모듈에서 이 pragma를 사용합니다. 이 pragma는 매우 공격적이며 이 방어가 필요하지 않을 수도 있는 함수에 적용되지만, 결과 응용 프로그램의 성능에 미치는 영향을 최소화하기 위해 최적화됩니다.

이 pragma를 사용하는 경우에도 안전한 코드를 작성하기 위해 노력해야 합니다. 즉, 코드에 버퍼 오버런이 발생 하지는 확인 합니다. **strict_gs_check** 코드에 남아 있는 버퍼 오버런 으로부터 응용 프로그램을 보호할 수 있습니다.

## <a name="example"></a>예제

다음 코드에서는 배열을 로컬 배열에 복사할 때 버퍼 오버런이 발생합니다. 이 코드를 컴파일할 때 `/GS`, 배열 데이터 형식이 포인터 이기 때문에 쿠키가 없는 스택에서 삽입 됩니다. 추가 된 **strict_gs_check** pragma 하면 스택 쿠키가 함수 스택에 삽입 합니다.

```cpp
// pragma_strict_gs_check.cpp
// compile with: /c

#pragma strict_gs_check(on)

void ** ReverseArray(void **pData,
                     size_t cData)
{
    // *** This buffer is subject to being overrun!! ***
    void *pReversed[20];

    // Reverse the array into a temporary buffer
    for (size_t j = 0, i = cData; i ; --i, ++j)
        // *** Possible buffer overrun!! ***
            pReversed[j] = pData[i];

    // Copy temporary buffer back into input/output buffer
    for (size_t i = 0; i < cData ; ++i)
        pData[i] = pReversed[i];

    return pData;
}
```

## <a name="see-also"></a>참고자료

[Pragma 지시문 및 __Pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)<br/>
[/GS(버퍼 보안 검사)](../build/reference/gs-buffer-security-check.md)