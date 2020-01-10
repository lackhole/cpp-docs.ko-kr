---
title: C++프로그램 종료
ms.date: 12/10/2019
helpviewer_keywords:
- terminating execution
- quitting applications
- exiting applications
- programs [C++], terminating
ms.assetid: fa0ba9de-b5f1-4e7b-aa65-e7932068b48c
ms.openlocfilehash: a0e86cacd951327d39296a183be5ee4fbc36fd15
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75301342"
---
# <a name="c-program-termination"></a>C++프로그램 종료

C++에서는 다음과 같은 방법으로 프로그램을 종료할 수 있습니다.

- [exit](exit-function.md) 함수를 호출합니다.
- [abort](abort-function.md) 함수를 호출합니다.
- `main`에서 [return](return-statement-cpp.md) 문을 실행합니다.

## <a name="exit-function"></a>exit 함수

Stdlib.h > \<에 선언 된 [exit](../c-runtime-library/reference/exit-exit-exit.md) 함수는 C++ 프로그램을 종료 합니다. `exit` 인수로 제공 된 값은 프로그램의 반환 코드 또는 종료 코드로 운영 체제에 반환 됩니다. 규칙에 따라 반환 코드 0은 프로그램이 성공적으로 완료되었음을 의미합니다. \<stdlib.h >에 정의 된 상수 EXIT_FAILURE 및 EXIT_SUCCESS를 사용 하 여 프로그램의 성공 또는 실패를 나타낼 수 있습니다.

`main` 함수에서 **return** 문을 실행 하는 것은 반환 값을 인수로 사용 하 여 `exit` 함수를 호출 하는 것과 같습니다.

## <a name="abort-function"></a>abort 함수

표준 포함 파일 STDLIB.H에서 선언된 [abort](../c-runtime-library/reference/abort.md) 함수는 C++ 프로그램을 종료합니다. `exit`와 `abort`의 차이점은 `exit` C++ 런타임 종료 처리를 수행할 수 있도록 하는 것입니다 (전역 개체 소멸자가 호출 됨). 반면 `abort`는 프로그램을 즉시 종료 합니다. `abort` 함수는 초기화 된 전역 정적 개체에 대 한 일반적인 소멸 프로세스를 무시 합니다. [Atexit](../c-runtime-library/reference/atexit.md) 함수를 사용 하 여 지정 된 특별 한 처리도 무시 합니다.

## <a name="atexit-function"></a>atexit 함수

[Atexit](../c-runtime-library/reference/atexit.md) 함수를 사용 하 여 프로그램 종료 전에 실행 되는 작업을 지정 합니다. **atexit**를 호출하기 전에 초기화된 전역 정적 개체는 종료 처리 함수의 실행 전에 소멸되지 않습니다.

## <a name="return-statement-in-main"></a>main의 return 문

`main`에서 [return](return-statement-cpp.md) 문을 실행하는 것은 `exit` 함수를 호출하는 것과 기능적으로 동일합니다. 다음 예제를 참조하세요.

```cpp
// return_statement.cpp
#include <stdlib.h>
int main()
{
    exit( 3 );
    return 3;
}
```

위의 예제에서 `exit` 및 **return** 문은 기능적으로 동일합니다. 그러나 C++에서는 **void**가 아닌 반환 형식을 가지는 함수가 값을 반환해야 합니다. **return** 문을 사용하면 `main`에서 값을 반환할 수 있습니다.

## <a name="destruction-of-static-objects"></a>정적 개체 소멸

`exit`를 호출 하거나 `main`에서 **return** 문을 실행 하는 경우 정적 개체는 초기화 순서의 역순으로 소멸 됩니다 (있는 경우 `atexit`를 호출한 후). 다음 예제에서는 이러한 초기화 및 정리가 작동하는 방법을 보여 줍니다.

### <a name="example"></a>예

다음 예에서는 `sd1` 및 `sd2` 정적 개체를 `main`항목 앞으로 만들고 초기화 합니다. **return** 문을 사용하여 이 프로그램이 종료된 후, 먼저 `sd2`가 소멸된 다음 `sd1`이 소멸됩니다. `ShowData` 클래스에 대한 소멸자가 이 정적 개체와 연결된 파일을 닫습니다.

```cpp
// using_exit_or_return1.cpp
#include <stdio.h>
class ShowData {
public:
   // Constructor opens a file.
   ShowData( const char *szDev ) {
   errno_t err;
      err = fopen_s(&OutputDev, szDev, "w" );
   }

   // Destructor closes the file.
   ~ShowData() { fclose( OutputDev ); }

   // Disp function shows a string on the output device.
   void Disp( char *szData ) {
      fputs( szData, OutputDev );
   }
private:
   FILE *OutputDev;
};

//  Define a static object of type ShowData. The output device
//   selected is "CON" -- the standard output device.
ShowData sd1 = "CON";

//  Define another static object of type ShowData. The output
//   is directed to a file called "HELLO.DAT"
ShowData sd2 = "hello.dat";

int main() {
   sd1.Disp( "hello to default device\n" );
   sd2.Disp( "hello to file hello.dat\n" );
}
```

범위를 벗어나면 소멸되도록 블록 범위를 사용해 `ShowData` 개체를 선언하여 이 코드를 작성할 수도 있습니다.

```cpp
int main() {
   ShowData sd1, sd2( "hello.dat" );

   sd1.Disp( "hello to default device\n" );
   sd2.Disp( "hello to file hello.dat\n" );
}
```


## <a name="see-also"></a>참조

[main: 프로그램 시작](main-program-startup.md)