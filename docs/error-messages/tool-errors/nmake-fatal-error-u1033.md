---
title: NMAKE 심각한 오류 U1033
ms.date: 11/04/2016
f1_keywords:
- U1033
helpviewer_keywords:
- U1033
ms.assetid: c146f7b5-7d5c-4329-a522-28a648546016
ms.openlocfilehash: 3b1df28e3cd7b27a9e7a130d9d71c1af68db9aec
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62324365"
---
# <a name="nmake-fatal-error-u1033"></a>NMAKE 심각한 오류 U1033

구문 오류: 예기치 않은 ' string'

문자열은 메이크파일 올바른 구문의 일부가 아닙니다.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>다음과 같은 가능한 원인을 확인하여 수정하려면

1. 닫는 꺾쇠 괄호의 짝이 없으면 (**<<**) 인라인 파일 줄의 시작 부분에 다음 오류가 발생 합니다.

    ```
    syntax error : 'EOF' unexpected
    ```

1. 등호 메이크파일의 매크로 정의 포함 된 경우 (**=**) 앞 이름 또는 이름을 정의 하는 경우는 확장 되지 않는 매크로 없이 다음과 같은 오류가 나타납니다.

    ```
    syntax error : '=' unexpected
    ```

1. 경우 세미콜론 (**;**) 도구에서 주석 줄에 있습니다. INI 아닙니다 줄의 시작 부분에 다음 오류가 발생 합니다.

    ```
    syntax error : ';' unexpected
    ```

1. 메이크파일 워드 프로세서에서 서식이 지정 된, 다음과 같은 오류가 발생할 수 있습니다.

    ```
    syntax error : ':' unexpected
    ```