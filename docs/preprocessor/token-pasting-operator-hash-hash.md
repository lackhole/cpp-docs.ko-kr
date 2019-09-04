---
title: '토큰 붙여넣기 연산자 (# #)'
ms.date: 08/29/2019
f1_keywords:
- '##'
helpviewer_keywords:
- preprocessor, operators
- '## preprocessor operator'
ms.assetid: 4f173503-990f-4bff-aef3-ec4d1f1458ef
ms.openlocfilehash: 4bf1b8c8f56ab9375503c9e8fb6a906706fc70bb
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70218109"
---
# <a name="token-pasting-operator-"></a>토큰 붙여넣기 연산자 (# #)

*병합* 또는 *결합* 연산자 라고도 하는 이중 숫자 기호 또는 *토큰 붙여넣기* 연산자 ( **##** )는 개체 형식 및 함수 유사 매크로 모두에서 사용 됩니다. 별도의 토큰이 단일 토큰에 조인 될 수 있으므로 매크로 정의의 첫 번째 또는 마지막 토큰이 될 수 없습니다.

매크로 정의의 정식 매개 변수 앞이나 뒤에 토큰 붙여넣기 연산자가 오는 경우 정식 매개 변수가 즉시 확장되지 않은 실제 인수로 바뀝니다. 이러한 교체 이전에 해당 인수에서 매크로 확장이 수행되지 않습니다.

그런 다음 *토큰 문자열* 에서 각 토큰 붙여넣기 연산자가 제거 되 고 앞과 뒤에 오는 토큰이 연결 됩니다. 결과 토큰은 올바른 토큰이어야 합니다. 올바른 토큰인 경우 해당 토큰은 매크로 이름을 나타낼 때 가능한 교체에 대해 검색됩니다. 식별자는 교체하기 전에 연결된 토큰이 프로그램에서 인식될 이름을 나타냅니다. 각 토큰은 프로그램 내 또는 컴파일러 명령줄 등 다른 곳에서 정의된 토큰을 나타냅니다. 연산자 앞이나 뒤의 공백은 선택 사항입니다.

이 예제에서는 문자열화 연산자와 토큰 붙여넣기 연산자를 모두 사용하여 프로그램 출력을 지정하는 방법을 보여 줍니다.

```cpp
#define paster( n ) printf_s( "token" #n " = %d", token##n )
int token9 = 9;
```

매크로가 다음과 같은 숫자 인수로 호출되는 경우

```cpp
paster( 9 );
```

매크로에서 다음을 생성하고

```cpp
printf_s( "token" "9" " = %d", token9 );
```

위는 다음이 됩니다.

```cpp
printf_s( "token9 = %d", token9 );
```

## <a name="example"></a>예제

```cpp
// preprocessor_token_pasting.cpp
#include <stdio.h>
#define paster( n ) printf_s( "token" #n " = %d", token##n )
int token9 = 9;

int main()
{
   paster(9);
}
```

```Output
token9 = 9
```

## <a name="see-also"></a>참고자료

[전처리기 연산자](../preprocessor/preprocessor-operators.md)
