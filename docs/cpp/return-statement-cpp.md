---
title: return 문 (C++)
ms.date: 11/04/2016
f1_keywords:
- return_cpp
helpviewer_keywords:
- return keyword [C++], syntax
- return keyword [C++]
ms.assetid: a498903a-056a-4df0-a6cf-72f633a62210
ms.openlocfilehash: 47bf9c50a2da039b0ffa074796a768290b732bb3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62268540"
---
# <a name="return-statement-c"></a>return 문 (C++)

함수 실행을 종료하고 컨트롤을 호출 함수(또는 `main` 함수에서 컨트롤을 이전하는 경우 운영 체제로)로 반환합니다. 호출 바로 다음 지점의 호출 함수에서 실행을 다시 시작합니다.

## <a name="syntax"></a>구문

```
return [expression];
```

## <a name="remarks"></a>설명

`expression` 절(있는 경우)은 초기화가 수행되고 있었던 것처럼 함수 선언에 지정된 형식으로 변환됩니다. 식의 형식에서 변환 된 **반환** 함수 형식의 임시 개체를 만들 수 있습니다. 임시 개체를 만드는 방법 및 시기에 대 한 자세한 내용은 참조 하십시오 [임시 개체](../cpp/temporary-objects.md)합니다.

`expression` 절 값이 호출 함수에 반환됩니다. 식을 생략하면 함수의 반환 값이 정의되지 않습니다. 생성자와 소멸자 및 형식의 함수 **void**에서 식을 지정할 수 없습니다는 **반환** 문입니다. 다른 모든 종류의 함수에서 식을 지정 해야 합니다 **반환** 문입니다.

제어 흐름에 함수 정의 바깥쪽 블록 종료 되 면 결과 동일한 것 경우는 **반환** 식 없이 문을 실행 했습니다. 값을 반환할 때 선언되는 함수에는 올바르지 않습니다.

함수는 임의 개수의 있을 수 있습니다 **반환** 문입니다.

다음 예제에서는 식을 사용 하 여는 **반환** 문을 두 정수의 가장 큰 가져오려고 합니다.

## <a name="example"></a>예제

```cpp
// return_statement2.cpp
#include <stdio.h>

int max ( int a, int b )
{
   return ( a > b ? a : b );
}

int main()
{
    int nOne = 5;
    int nTwo = 7;

    printf_s("\n%d is bigger\n", max( nOne, nTwo ));
}
```

## <a name="see-also"></a>참고자료

[점프 문](../cpp/jump-statements-cpp.md)<br/>
[C++ 키워드](../cpp/keywords-cpp.md)