---
title: 문자열의 마지막 문자
ms.date: 11/04/2016
helpviewer_keywords:
- last character in string
- MBCS [C++], last character in string
ms.assetid: 0a180376-4e55-41e8-9c64-539c7b6d8047
ms.openlocfilehash: 4c99628cd12738fabb877a94cfd04a4033ee45aa
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57740293"
---
# <a name="last-character-in-a-string"></a>문자열의 마지막 문자

멀티바이트 문자 집합의 문자를 판단하기 위해 이 내용을 참고하세요.

- 후행 바이트는 대부분 ASCII 문자 집합의 범위와 겹칩니다. ASCII 문자 중 값이 32보다 작은 경우 제어 문자에 해당하는데, 바이트 스캔을 할 경우 안전하게 사용할 수 있는 방법이 있습니다.

- 문자열의 마지막이 백슬래시 문자인지 확인하는 코드를 한번 생각해 보세요.

    ```cpp
    if ( sz[ strlen( sz ) - 1 ] == '\\' )    // Is last character a '\'?
        // . . .
    ```

   `strlen`은 MBCS를 고려해 인식하지 않고 무조건 바이트 수를 반환합니다. 일부 코드 페이지(예: 932)의 경우, '\\'(0x5c)는 유효한 후행 바이트입니다(`sz`는 C문자열).

   해결책 중 하나는 코드를 다음과 같이 다시 작성하는 것입니다.

    ```cpp
    char *pLast;
    pLast = _mbsrchr( sz, '\\' );    // find last occurrence of '\' in sz
    if ( pLast && ( *_mbsinc( pLast ) == '\0' ) )
        // . . .
    ```

   이 코드에서는 멀티바이트 문자 집합용 함수 `_mbsrchr`과 `_mbsinc`를 사용합니다. 이 함수군은 멀티바이트 문자 집합(MBCS)을 인식하기 때문에 문자 역슬래시('\\')와 후행 바이트에서의 '\\'(0x5c)를 구분할 수 있습니다. 위 코드에서 문자열의 마지막 문자가 null('\0')이면 지정된 작업을 수행합니다.

## <a name="see-also"></a>참고자료

[멀티바이트 문자 집합(MBCS) 프로그래밍 팁](../text/mbcs-programming-tips.md)<br/>
[문자 할당](../text/character-assignment.md)
