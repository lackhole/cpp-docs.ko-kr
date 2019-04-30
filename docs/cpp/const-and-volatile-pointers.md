---
title: const 및 volatile 포인터
ms.date: 11/04/2016
helpviewer_keywords:
- volatile keyword [C++], and pointers
- pointers, and const
- pointers, and volatile
- const keyword [C++], volatile pointers
ms.assetid: 0c92dc6c-400e-4342-b345-63ddfe649d7e
ms.openlocfilehash: c869adbbdc8a5a17d315e64e5ac15545e0c46e26
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62399124"
---
# <a name="const-and-volatile-pointers"></a>const 및 volatile 포인터

합니다 [상수](../cpp/const-cpp.md) 및 [volatile](../cpp/volatile-cpp.md) 키워드는 포인터 처리 방법을 변경 합니다. 합니다 **const** 키워드 포인터가 초기화 후 수정 될 수 없음을 지정 합니다. 즉 포인터 이후 수정 되지 않도록에서 보호 됩니다.

합니다 **volatile** 키워드 뒤에 오는 이름과 관련 된 값을 사용자 응용 프로그램에서 이외의 작업에 의해 수정 될 수 있음을 지정 합니다. 따라서 합니다 **volatile** 키워드 여러 프로세스 또는 인터럽트 서비스 루틴을 사용 하 여 통신에 사용 되는 전역 데이터 영역에서 액세스할 수 있는 공유 메모리에서 개체를 선언 하는 데 유용 합니다.

이름으로 선언 되는 경우 **volatile**, 컴파일러는 프로그램에 액세스할 때마다 메모리에서 값을 다시 로드 합니다. 개체의 최적화 횟수가 상당히 줄어들게 됩니다. 이 키워드는 개체 상태가 예기치 않게 변경되는 경우 예상 가능한 프로그램 성능을 보장하는 유일한 방법이기도 합니다.

으로 포인터에서 가리키는 개체를 선언 하 **상수** 또는 **volatile**, 폼의 선언을 사용:

```cpp
const char *cpch;
volatile char *vpch;
```

포인터의 값을 선언할-포인터에 저장 된 실제 주소 즉,-으로 **상수** 또는 **volatile**, 폼의 선언을 사용:

```cpp
char * const pchc;
char * volatile pchv;
```

C++ 개체의 수정을 허용 하는 할당을 금지 하는 언어 또는로 선언한 포인터 **const**합니다. 그와 같은 할당은 개체 또는 포인터가 선언된 정보를 제거하기 때문에 원래의 선언 의도에 위배됩니다. 다음의 선언을 살펴보세요.

```cpp
const char cch = 'A';
char ch = 'B';
```

앞의 선언에서 두 개체의 지정 된 (`cch`, 형식 **const char**, 및 `ch`, 형식의 **char)**, 다음의 선언/초기화 유효:

```cpp
const char *pch1 = &cch;
const char *const pch4 = &cch;
const char *pch5 = &ch;
char *pch6 = &ch;
char *const pch7 = &ch;
const char *const pch8 = &ch;
```

다음의 선언/초기화는 잘못되었습니다.

```cpp
char *pch2 = &cch;   // Error
char *const pch3 = &cch;   // Error
```

`pch2` 선언은 상수 개체가 수정될 수 있는 포인터를 선언하기 때문에 허용되지 않습니다. 선언의 `pch3` 포인터 상수를 지정 개체가 아닌 선언 마찬가지 이유로 허용 되지 않습니다는 `pch2` 선언은 허용 되지 않습니다.

다음 8개의 할당에서는 포인터를 통한 할당과 이전 선언에 대한 포인터 값의 변경을 표시합니다. 이제 `pch1`을 통해 `pch8`에 대한 초기화가 올바르다고 가정합니다.

```cpp
*pch1 = 'A';  // Error: object declared const
pch1 = &ch;   // OK: pointer not declared const
*pch2 = 'A';  // OK: normal pointer
pch2 = &ch;   // OK: normal pointer
*pch3 = 'A';  // OK: object not declared const
pch3 = &ch;   // Error: pointer declared const
*pch4 = 'A';  // Error: object declared const
pch4 = &ch;   // Error: pointer declared const
```

로 선언 된 포인터 **volatile**, 또는 혼합 된 형태로 **const** 하 고 **volatile**, 동일한 규칙을 따릅니다.

에 대 한 포인터 **const** 개체 종종 함수 선언에 다음과 같이 사용 됩니다.

```cpp
errno_t strcpy_s( char *strDestination, size_t numberOfElements, const char *strSource );
```

위의 문은 함수를 선언 [strcpy_s](../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md)형식의 포인터가 있는 두 개의 세 가지 인수를 **char**합니다. 하며 하기 때문에 참조로 인수 전달 하지 값으로 함수는 모두 자유롭게 수정할 `strDestination` 하 고 `strSource` 하는 경우 `strSource` 로 선언 되지 않은 **const**합니다. 선언의 `strSource` 으로 **const** 호출자에 게는 보장 `strSource` 호출된 함수에서 변경할 수 없습니다.

> [!NOTE]
> 표준 변환이 없으므로 *typename* <strong>\*</strong> 하 **const** *typename* <strong>\*</strong>, 형식의 인수를 전달 하는 것이 유효 `char *` 하 [strcpy_s](../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md)합니다. 그러나는 성립 되지; 제거 하는 암시적 변환이 존재 합니다 **const** 개체 또는 포인터의 특성입니다.

A **const** 동일한 형식의 포인터에 지정 된 형식의 대 한 포인터를 할당할 수 있습니다. 그러나 포인터 없는 **const** 할당할 수 없습니다는 **const** 포인터입니다. 다음 코드는 올바른 할당과 잘못된 할당을 보여 줍니다.

```cpp
// const_pointer.cpp
int *const cpObject = 0;
int *pObject;

int main() {
pObject = cpObject;
cpObject = pObject;   // C3892
}
```

다음 샘플에서는 개체에 포인터에 대한 포인터가 있는 경우 개체를 const로 선언하는 방법을 보여 줍니다.

```cpp
// const_pointer2.cpp
struct X {
   X(int i) : m_i(i) { }
   int m_i;
};

int main() {
   // correct
   const X cx(10);
   const X * pcx = &cx;
   const X ** ppcx = &pcx;

   // also correct
   X const cx2(20);
   X const * pcx2 = &cx2;
   X const ** ppcx2 = &pcx2;
}
```

## <a name="see-also"></a>참고자료

[포인터](../cpp/pointers-cpp.md)