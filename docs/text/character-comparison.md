---
title: 문자 비교
ms.date: 11/04/2016
helpviewer_keywords:
- comparing characters
- MBCS [C++], character comparison
- characters [C++], comparing
ms.assetid: 18846e44-3e6e-40c4-9b42-3153fb15db20
ms.openlocfilehash: 075a22634f254c2ea634a1171ee157971fe5918e
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57749336"
---
# <a name="character-comparison"></a>문자 비교

다음 팁을 사용하십시오.

- 알려진 선행 바이트와 ASCII 문자 비교는 제대로 수행됩니다.

    ```cpp
    if( *sz1 == 'A' )
    ```

- 두 개의 알 수 없는 문자를 비교하려면 Mbstring.h에 정의된 매크로 중 하나를 사용해야 합니다.

    ```cpp
    if( !_mbccmp( sz1, sz2) )
    ```

   이렇게 하면 더블바이트 문자의 바이트 두 개가 모두 비교됩니다.

## <a name="see-also"></a>참고자료

[멀티바이트 문자 집합(MBCS) 프로그래밍 팁](../text/mbcs-programming-tips.md)<br/>
[버퍼 오버플로](../text/buffer-overflow.md)
