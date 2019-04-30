---
title: 버퍼 오버플로
ms.date: 11/04/2016
helpviewer_keywords:
- buffers [C++], character sizes
- buffer overflows [C++]
- MBCS [C++], buffer overflow
ms.assetid: f2b7e40a-f02b-46d8-a449-51d26fc0c663
ms.openlocfilehash: 7f9864e6b49446ea68d82e76e877ce9c677b893d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62410761"
---
# <a name="buffer-overflow"></a>버퍼 오버플로

다양한 문자 크기를 갖는 문자를 버퍼에 넣을 때 문제가 발생할 수 있습니다. 문자열 `sz`의 문자를 `rgch`버퍼에 복사하는 다음 코드를 살펴봅시다.

```cpp
cb = 0;
while( cb < sizeof( rgch ) )
    rgch[ cb++ ] = *sz++;
```

여기서 문제는 마지막 바이트는 선행 바이트를 복사 했습니다. 다음 예는 버퍼 오버플로가 발생할 수 있으므로 문제가 해결된 것은 아닙니다.

```cpp
cb = 0;
while( cb < sizeof( rgch ) )
{
    _mbccpy( rgch + cb, sz );
    cb += _mbclen( sz );
    sz = _mbsinc( sz );
}
```

`_mbccpy`를 사용하면 올바른 작업을 할 수 있습니다. 문자가 싱글 또는 더블 바이트인지 관계없이 문자 전체를 복사합니다. 하지만 이 예제에서도 문자가 두 바이트로 구성되어 있다면 복사할 마지막 문자가 버퍼에 들어가지 않을 수 있다는 것을 고려하지 않습니다. 올바른 예제는 다음과 같습니다.

```cpp
cb = 0;
while( (cb + _mbclen( sz )) <= sizeof( rgch ) )
{
    _mbccpy( rgch + cb, sz );
    cb += _mbclen( sz );
    sz = _mbsinc( sz );
}
```

이 코드는 `_mbclen`을 사용하여 `sz`가 가리키는 현재 문자의 크기를 점검하여 루프에서의 버퍼 오버플로우를 방지합니다. `_mbsnbcpy` 함수를 사용하면 **while** 루프 코드를 다음과 같이 한 줄로 바꿀 수 있습니다. 예를 들어:

```cpp
_mbsnbcpy( rgch, sz, sizeof( rgch ) );
```

## <a name="see-also"></a>참고자료

[멀티바이트 문자 집합(MBCS) 프로그래밍 팁](../text/mbcs-programming-tips.md)
