---
title: 문자 할당
ms.date: 11/04/2016
helpviewer_keywords:
- characters [C++], assignments
- MBCS [C++], character assignments
ms.assetid: dcc329cd-92df-4e20-817d-364be62ff28f
ms.openlocfilehash: 88c42435d336ba78e87c9acfe3ada5fddbd18fb8
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57750704"
---
# <a name="character-assignment"></a>문자 할당

문자열을 복사하는 다음의 예제를 살펴봅시다. **while** 루프가 문자열을 순회하면서 'X'를 제외한 모든 문자를 다른 문자열로 복사하고 있습니다.

```cpp
while( *sz2 )
{
    if( *sz2 != 'X' )
        *sz1++ = *sz2++;
    else
        sz2++;
}
```

이 코드는 `sz2`에 있는 바이트를 `sz1`이 가리키는 위치로 복사한 다음 `sz1`을 증가시켜 다음 바이트를 가져옵니다. 그러나 `sz2`의 다음 문자가 더블바이트 문자인 경우 `sz1`에 대한 할당은 첫 번째 바이트만 복사가 이루어집니다. 다음 코드는 문자를 안전하게 복사하고 `sz1`과 `sz2`를 올바르게 증가시킵니다.

```cpp
while( *sz2 )
{
    if( *sz2 != 'X' )
    {
        _mbscpy_s( sz1, 1, sz2 );
        sz1 = _mbsinc( sz1 );
        sz2 = _mbsinc( sz2 );
    }
    else
        sz2 = _mbsinc( sz2 );
}
```

## <a name="see-also"></a>참고자료

[멀티바이트 문자 집합(MBCS) 프로그래밍 팁](../text/mbcs-programming-tips.md)<br/>
[문자 비교](../text/character-comparison.md)
