---
title: message
ms.date: 11/04/2016
f1_keywords:
- message_CPP
- vc-pragma.message
helpviewer_keywords:
- message pragma
- pragmas, message
ms.assetid: 67414f25-ed47-4079-a5dc-21d9d1a39754
ms.openlocfilehash: e9383238fd308ec59a9767f56af1c07fc3cfcf07
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59030208"
---
# <a name="message"></a>message
컴파일이 종료되지 않은 상태에서 문자열 리터럴을 표준 출력에 보냅니다.

## <a name="syntax"></a>구문

```
#pragma message( messagestring )
```

## <a name="remarks"></a>설명

일반적인 사용 합니다 **메시지** pragma는 컴파일 시간에 정보 메시지를 표시 합니다.

합니다 *messagestring* 매개 변수는 리터럴 문자열로 확장 될 수 있습니다 및 문자열 리터럴과 원하는 조합을 사용 하 여 이러한 매크로 연결할 수 있습니다.

미리 정의 된 매크로 사용 하는 경우는 **메시지** pragma 매크로 문자열을 반환 해야, 그렇지 않으면 매크로의 출력을 문자열로 변환 해야 합니다.

다음 코드 조각을 사용 하는 **메시지** pragma 컴파일하는 동안 메시지를 표시 하려면:

```cpp
// pragma_directives_message1.cpp
// compile with: /LD
#if _M_IX86 >= 500
#pragma message("_M_IX86 >= 500")
#endif

#pragma message("")

#pragma message( "Compiling " __FILE__ )
#pragma message( "Last modified on " __TIMESTAMP__ )

#pragma message("")

// with line number
#define STRING2(x) #x
#define STRING(x) STRING2(x)

#pragma message (__FILE__ "[" STRING(__LINE__) "]: test")

#pragma message("")
```

## <a name="see-also"></a>참고자료

[Pragma 지시문 및 __Pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)