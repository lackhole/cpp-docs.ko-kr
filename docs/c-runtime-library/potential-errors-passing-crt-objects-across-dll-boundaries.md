---
title: DLL 경계를 넘어 CRT 개체를 전달할 때 발생할 수 있는 오류
ms.date: 11/04/2016
helpviewer_keywords:
- DLL conflicts [C++]
ms.assetid: c217ffd2-5d9a-4678-a1df-62a637a96460
ms.openlocfilehash: 31f9d9aceba167b516c9d37724e240f1bc4586e1
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57749904"
---
# <a name="potential-errors-passing-crt-objects-across-dll-boundaries"></a>DLL 경계를 넘어 CRT 개체를 전달할 때 발생할 수 있는 오류

파일 핸들, 로캘 및 환경 변수와 같은 CRT(C 런타임) 개체를 DLL 내외로 전달하면(DLL 경계를 넘어선 함수 호출) DLL과 DLL로 호출되는 파일에 다른 CRT 라이브러리 복사본이 사용될 경우 예기치 않은 동작이 발생할 수 있습니다.

메모리를 할당(`new` 또는 `malloc`를 사용하여 명시적으로나 `strdup`, `strstreambuf::str` 등을 사용하여 암시적으로)한 다음 해제되도록 DLL 경계를 넘어 포인터를 전달하면 관련 문제가 발생할 수 있습니다. DLL 및 해당 사용자가 다른 CRT 라이브러리 복사본을 사용할 경우 이로 인해 메모리 액세스 위반 또는 힙 손상이 발생할 수 있습니다.

또한 이 문제로 인해 디버깅 중 출력 창에 다음과 같은 오류가 발생할 수 있습니다.

HEAP[]: RtlValidateHeap(#,#)에 잘못된 주소가 지정되었습니다.

## <a name="causes"></a>원인

CRT 라이브러리 복사본마다 별도의 고유한 상태가 앱 또는 DLL에 의해 스레드 로컬 스토리지에 유지됩니다. 따라서 파일 핸들, 환경 변수 및 로캘과 같은 CRT 개체가 이러한 개체가 할당 또는 설정된 앱 또는 DLL의 CRT 복사본에 대해서만 유효합니다. DLL 및 해당 앱 클라이언트가 다른 CRT 라이브러리 복사본을 사용하면 이러한 CRT 개체를 DLL 경계를 넘어 전달할 때 해당 개체가 반대쪽에서 올바르게 수신되지 않을 수 있습니다. Visual Studio 2015 이상의 유니버설 CRT 이전 버전에서 이러한 현상이 특히 두드러집니다. Visual C++ 2013 또는 이전 버전으로 빌드된 모든 버전의 Visual Studio에 대해 버전별 CRT 라이브러리가 있습니다. 해당 데이터 구조 및 명명 규칙과 같은 CRT의 내부 구현 세부 사항은 버전마다 다릅니다. 한 버전의 CRT에 대해 컴파일된 코드를 다른 버전의 CRT DLL로 동적으로 연결하는 방식은 절대 지원되지 않았습니다. 가끔씩 이러한 경우가 있더라도 우연에 의한 것이엇습니다.

또한 CRT 라이브러리 복사본마다 자체 힙 관리자가 있기 때문에 한 CRT 라이브러리에서 메모리를 할당한 다음 다른 CRT 라이브러리 복사본에 의해 해제되도록 DLL 경계를 넘어 포인터를 전달하는 것은 힙 손상의 잠재적 원인이 될 수 있습니다. DLL이 경계를 넘어 CRT 개체를 전달하거나 메모리를 할당한 다음 DLL 외부에서 해제되도록 DLL을 디자인하면 DLL과 동일한 CRT 라이브러리 복사본을 사용하도록 DLL의 앱 클라이언트를 제한하게 됩니다. DLL 및 해당 클라이언트는 일반적으로 로드 타임에 둘 다 동일한 버전의 CRT DLL에 연결된 경우에만 동일한 CRT 라이브러리 복사본을 사용합니다. Windows 10의 Visual Studio 2015 이상에서 사용되는 유니버설 CRT 라이브러리의 DLL 버전은 이제 중앙에서 배포된 Windows 구성 요소인 ucrtbase.dll이므로 Visual Studio 2015 및 이상 버전으로 빌드한 앱에 대해 동일합니다. 그러나 CRT 코드가 동일하더라도 한 힙에 할당된 메모리를 다른 힙을 사용하는 구성 요소로 전달할 수 없습니다.

## <a name="example"></a>예제

### <a name="description"></a>설명

이 예제에서는 DLL 경계를 넘어 파일 핸들을 전달합니다.

DLL 및 .exe 파일은 /MD를 사용하여 빌드되므로 단일 CRT 복사본을 공유합니다.

서로 다른 CRT 복사본을 사용하도록 /MT를 사용하여 다시 빌드할 경우 초래되는 test1Main.exe 결과를 실행하면 액세스 위반이 발생합니다.

```cpp
// test1Dll.cpp
// compile with: cl /EHsc /W4 /MD /LD test1Dll.cpp
#include <stdio.h>
__declspec(dllexport) void writeFile(FILE *stream)
{
   char   s[] = "this is a string\n";
   fprintf( stream, "%s", s );
   fclose( stream );
}
```

```cpp
// test1Main.cpp
// compile with: cl /EHsc /W4 /MD test1Main.cpp test1Dll.lib
#include <stdio.h>
#include <process.h>
void writeFile(FILE *stream);

int main(void)
{
   FILE  * stream;
   errno_t err = fopen_s( &stream, "fprintf.out", "w" );
   writeFile(stream);
   system( "type fprintf.out" );
}
```

```Output
this is a string
```

## <a name="example"></a>예제

### <a name="description"></a>설명

이 예제에서는 DLL 경계를 넘어 환경 변수를 전달합니다.

```cpp
// test2Dll.cpp
// compile with: cl /EHsc /W4 /MT /LD test2Dll.cpp
#include <stdio.h>
#include <stdlib.h>

__declspec(dllexport) void readEnv()
{
   char *libvar;
   size_t libvarsize;

   /* Get the value of the MYLIB environment variable. */
   _dupenv_s( &libvar, &libvarsize, "MYLIB" );

   if( libvar != NULL )
      printf( "New MYLIB variable is: %s\n", libvar);
   else
      printf( "MYLIB has not been set.\n");
   free( libvar );
}
```

```cpp
// test2Main.cpp
// compile with: cl /EHsc /W4 /MT test2Main.cpp test2dll.lib
#include <stdlib.h>
#include <stdio.h>

void readEnv();

int main( void )
{
   _putenv( "MYLIB=c:\\mylib;c:\\yourlib" );
   readEnv();
}
```

```Output
MYLIB has not been set.
```

CRT 복사본이 하나만 사용되도록 /MD를 사용하여 DLL과 .exe 파일을 모두 빌드하면 프로그램이 실행되고 다음과 같은 출력이 생성됩니다.

```
New MYLIB variable is: c:\mylib;c:\yourlib
```

## <a name="see-also"></a>참고 항목

[CRT 라이브러리 기능](../c-runtime-library/crt-library-features.md)
