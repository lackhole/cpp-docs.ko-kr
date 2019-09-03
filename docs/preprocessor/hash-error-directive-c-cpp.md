---
title: '#error 지시문(C/C++)'
ms.date: 08/29/2019
f1_keywords:
- '#error'
helpviewer_keywords:
- '#error directive'
- preprocessor, directives
- error directive (#error directive)
ms.assetid: d550a802-ff19-4347-9597-688935d23b2b
ms.openlocfilehash: bfb5c18f20319e6e6d345f28d3e1850714334b71
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70216114"
---
# <a name="error-directive-cc"></a>#error 지시문 (C/C++)

**#Error** 지시문은 컴파일 시간에 사용자 지정 오류 메시지를 내보낸 다음 컴파일을 종료 합니다.

## <a name="syntax"></a>구문

> **#error** *토큰 문자열*

## <a name="remarks"></a>설명

이 지시문이 생성하는 오류 메시지에는 *token-string* 매개 변수가 포함되어 있습니다. *token-string* 매개 변수는 매크로 확장이 되지 않습니다. 이 지시어는 프로그램 불일치 또는 제약 조건 위반을 개발자에 게 알리기 위해 전처리 중에 가장 유용 합니다. 다음 예제에서는 전처리하는 동안의 오류 처리를 보여 줍니다.

```cpp
#if !defined(__cplusplus)
#error C++ compiler required.
#endif
```

## <a name="see-also"></a>참고자료

[전처리기 지시문](../preprocessor/preprocessor-directives.md)
