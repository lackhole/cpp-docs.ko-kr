---
title: for 문 (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- for keyword [C++]
ms.assetid: 6c7d01b3-c4c1-4c6a-aa58-e2d198f33d4a
ms.openlocfilehash: a6b1823fe93c45abd8dabbd22116924e0a64f19a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62154219"
---
# <a name="for-statement-c"></a>for 문 (C++)

조건이 거짓이 될 때까지 명령문을 반복적으로 실행합니다. 범위 기반 for 문에 대한 내용은 [범위 기반 for 문(C++)](../cpp/range-based-for-statement-cpp.md)을 참조하세요.

## <a name="syntax"></a>구문

```
for ( init-expression ; cond-expression ; loop-expression )
    statement;
```

## <a name="remarks"></a>설명

**for** 문을 사용하면 지정된 횟수만큼 실행해야 하는 루프를 만들 수 있습니다.

**for** 문은 다음 표와 같이 세개의 선택적 부분으로 구성됩니다.

### <a name="for-loop-elements"></a>for 루프 요소

|구문 이름|실행 시기|설명|
|-----------------|-------------------|-----------------|
|`init-expression`|**for** 문의 다른 요소가 나오기 전에 `init-expression`은 한 번만 실행됩니다. 그런 다음 `cond-expression`으로 제어가 전달됩니다.|루프 인덱스를 초기화하는 데 종종 사용됩니다. 표현식이나 선언을 포함할 수 있습니다.|
|`cond-expression`|첫 번째 반복을 포함하여 `statement`의 각 반복을 실행하기 전에 `cond-expression`이 참(0이 아님)으로 평가될 때만 `statement`가 실행됩니다.|정수 형식이나 정수 형식으로 명확히 변환되는 클래스 형식으로 평가되는 식입니다. 일반적으로 루프 종료 기준을 판단하는 데 사용됩니다.|
|`loop-expression`|`statement`이 반복될 때마다 `loop-expression`이 실행된 후 `cond-expression`이 평가됩니다.|일반적으로 루프 인덱스 증가에 사용됩니다.|

다음 예제에서는 **for** 문을 사용하는 다양한 방법을 보여줍니다.

```cpp
#include <iostream>
using namespace std;

int main() {
    // The counter variable can be declared in the init-expression.
    for (int i = 0; i < 2; i++ ){
       cout << i;
    }
    // Output: 01
    // The counter variable can be declared outside the for loop.
    int i;
    for (i = 0; i < 2; i++){
        cout << i;
    }
    // Output: 01
    // These for loops are the equivalent of a while loop.
    i = 0;
    while (i < 2){
        cout << i++;
    }
}
    // Output: 012
```

`init-expression` 및 `loop-expression`은 쉼표로 구분된 여러 개의 문을 포함할 수 있습니다. 예를 들어:

```cpp
#include <iostream>
using namespace std;

int main(){
    int i, j;
    for ( i = 5, j = 10 ; i + j < 20; i++, j++ ) {
        cout << "i + j = " << (i + j) << '\n';
    }
}
    // Output:
    i + j = 15
    i + j = 17
    i + j = 19
```

`loop-expression`은 증가 또는 감소하거나 다른 방식으로 수정될 수 있습니다.

```cpp
#include <iostream>
using namespace std;

int main(){
for (int i = 10; i > 0; i--) {
        cout << i << ' ';
    }
    // Output: 10 9 8 7 6 5 4 3 2 1
    for (int i = 10; i < 20; i = i+2) {
        cout << i << ' ';
    }
    // Output: 10 12 14 16 18
```

**for** 루프는 `statement` 내에서 [break](../cpp/break-statement-cpp.md), [return](../cpp/return-statement-cpp.md) 또는 [goto](../cpp/goto-statement-cpp.md)(**for** 루프 외부의 레이블이 있는 명령문)가 실행될 때 종료됩니다. **for** 루프의 [continue](../cpp/continue-statement-cpp.md) 문은 현재 반복만 종료합니다.

`cond-expression`이 생략되면 참으로 간주되고, **for** 루프는 `statement` 내에서 **break**, **return** 또는 **goto** 없이 종료되지 않습니다.

**for** 문의 세 필드는 일반적으로 초기화, 종료 테스트 및 증가에 사용되지만 이러한 용도로만 제한되지 않습니다. 예를 들어, 다음 코드는 0에서 4까지의 숫자를 출력합니다. 이 경우 `statement`는 null 문입니다.

**for** 문의 세 필드는 일반적으로 초기화, 종료 테스트 및 증가에 사용되지만 이러한 용도로만 제한되지 않습니다. 예를 들어, 다음 코드는 0에서 4까지의 숫자를 출력합니다. 이 경우 `statement`는 null 문입니다.

```cpp
#include <iostream>
using namespace std;

int main()
{
    int i;
    for( i = 0; i < 5; cout << i << '\n', i++){
        ;
    }
}
```

## <a name="for-loops-and-the-c-standard"></a>for 루프와 C++ 표준

C++ 표준에 따르면 **for** 루프에서 선언된 변수는 **for** 루프가 끝난 후에 범위를 벗어나야 합니다. 예를 들어:

```cpp
for (int i = 0 ; i < 5 ; i++) {
   // do something
}
// i is now out of scope under /Za or /Zc:forScope
```

[/Ze](../build/reference/za-ze-disable-language-extensions.md) 컴파일 옵션과 함께 빌드되었다면, 기본적으로 **for** 루프에서 선언된 변수는 **for** 루프의 범위를 끝내기 전까지 범위에 남아있습니다.

[/Zc: forscope](../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md)는 `/Za`를 지정할 필요 없이 **for** 루프에 선언된 변수의 표준 동작을 활성화합니다.
/ Zc : forScope는 `/Za`를 지정할 필요없이 for 루프에 선언된 변수의 표준 동작을 가능하게 합니다.

다음과 같이 **for** 루프의 범위 지정 차이를 사용하여 `/Ze`에서 변수를 다시 선언할 수도 있습니다.

```cpp
// for_statement5.cpp
int main(){
   int i = 0;   // hidden by var with same name declared in for loop
   for ( int i = 0 ; i < 3; i++ ) {}

   for ( int i = 0 ; i < 3; i++ ) {}
}
```

이것은 **for** 루프에서 선언된 변수 표준 동작을 더 가깝게 모방합니다. **for** 루프에서 선언된 변수는 루프가 완료된 후에 범위를 벗어나야 합니다. **for** 루프에서 변수를 선언하면 컴파일러는 동일한 이름의 로컬 변수가 이미 있더라도 **for** 루프의 범위를 포함하는 로컬 변수로 내부적으로 이를 승격합니다.

## <a name="see-also"></a>참고자료

[반복 문](../cpp/iteration-statements-cpp.md)<br/>
[키워드](../cpp/keywords-cpp.md)<br/>
[while 문(C++)](../cpp/while-statement-cpp.md)<br/>
[do-while 문(C++)](../cpp/do-while-statement-cpp.md)<br/>
[범위 기반 for 문(C++)](../cpp/range-based-for-statement-cpp.md)
