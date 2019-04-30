---
title: 컴파일러 경고(수준 1 및 3) C4793
ms.date: 11/04/2016
f1_keywords:
- C4793
helpviewer_keywords:
- C6634
- C6635
- C6640
- C6630
- C6639
- C6636
- C6638
- C6631
- C6637
- C4793
ms.assetid: 819ada53-1d9c-49b8-a629-baf8c12314e6
ms.openlocfilehash: e7ca3b10e09b0d6818fbc7f5607ebc9c95c7f15c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62280544"
---
# <a name="compiler-warning-level-1-and-3-c4793"></a>컴파일러 경고(수준 1 및 3) C4793

> '*함수*': 함수가 네이티브 코드로 컴파일 되었습니다. '*이유*'

## <a name="remarks"></a>설명

컴파일러가 컴파일할 수 없습니다 *함수* 관리 코드로 합니다 [/clr](../../build/reference/clr-common-language-runtime-compilation.md) 컴파일러 옵션을 지정 합니다. 대신 컴파일러가 경고 C4793 및 설명 메시지를 내보냅니다 하 고 컴파일합니다 *함수* 네이티브 코드로 합니다. 후속 메시지를 포함 합니다 *이유* 이유를 설명 하는 텍스트 *함수* 로 컴파일할 수 없는 `MSIL`합니다.

지정 하는 경우 수준 1 경고는이 **/clr: pure** 컴파일러 옵션.  **/clr: pure** 컴파일러 옵션은 Visual Studio 2015에서 사용 되지 않으며 Visual Studio 2017에서 지원 되지 않습니다.

다음 표에서 가능한 모든 후속 메시지를 나열합니다.

|따라서 메시지|설명|
|--------------------|-------------|
|정렬 된 데이터 형식은 관리 코드에서 지원 되지 않습니다.|CLR 수 있어야 필요에 따라 데이터를 할당 되지 않을 수도 있는 데이터와 같은 선언을 사용 하 여 정렬 된 경우에 가능한 [__m128](../../cpp/m128.md) 하거나 [맞춤](../../cpp/align-cpp.md)합니다.|
|관리 코드에서 '__ImageBase'를 사용 하는 함수를 사용할 수 없습니다.|`__ImageBase` 일반적으로 DLL을 로드 하는 하위 수준 네이티브 코드 에서만 사용 되는 특수 링커에서 기호입니다.|
|varargs에서 지원 되지 않습니다는 ' / clr' 컴파일러 옵션|네이티브 함수에는 관리 되는 함수를 호출할 수 없습니다 [가변 인수 목록을](../../cpp/functions-with-variable-argument-lists-cpp.md) (varargs) 함수를 다른 스택 레이아웃 요구 사항이 없으므로 합니다. 그러나 지정 하는 경우는 **/clr: pure** 컴파일러 옵션을 어셈블리에는 관리 되는 함수에만 포함 될 수 있으므로 지원 되는 나열 하는 가변 인수입니다. 자세한 내용은 [순수형 및 안정형 코드 (C++/CLI)](../../dotnet/pure-and-verifiable-code-cpp-cli.md)합니다.|
|64 비트 CLR에서는 __ptr32 한정자로 선언 된 데이터를 지원 하지 않습니다.|포인터 크기가 현재 플랫폼에서 네이티브 포인터와 동일 해야 합니다. 자세한 내용은 [__ptr32 합니다 \__ptr64](../../cpp/ptr32-ptr64.md)합니다.|
|32 비트 CLR __ptr64 한정자로 선언 된 데이터를 지원 하지 않습니다.|포인터 크기가 현재 플랫폼에서 네이티브 포인터와 동일 해야 합니다. 자세한 내용은 [__ptr32 합니다 \__ptr64](../../cpp/ptr32-ptr64.md)합니다.|
|관리 코드에서 하나 이상의 내장 함수를 사용할 수 없습니다.|메시지가 생성 되는 시간 이름을 내장 함수를 사용할 수 없습니다. 그러나 하위 수준 컴퓨터 명령을 내장 함수는 일반적으로 인해이 메시지가 나타냅니다.|
|관리 코드에서는 인라인 네이티브 어셈블리 ('__asm')를 사용할 수 없습니다.|[인라인 어셈블리 코드](../../assembler/inline/asm.md) 관리할 수 없는 임의 네이티브 코드를 포함할 수 있습니다.|
|__Clrcall이 아닌 가상 함수 썽크는 네이티브로 컴파일해야 합니다.|이외[__clrcall](../../cpp/clrcall.md) 가상 함수 썽크가 관리 되지 않는 주소를 사용 해야 합니다.|
|'J를 사용 하는 함수는 네이티브로 컴파일해야 합니다.|CLR은 프로그램 실행을 제어할 수 있어야 합니다. 그러나 합니다 [setjmp](../../cpp/using-setjmp-longjmp.md) 함수는 저장 및 등록 및 실행 상태와 같은 하위 수준 정보를 복원 하 여 일반 프로그램 실행을 건너뜁니다.|

## <a name="example"></a>예제

다음 샘플 C4793를 생성합니다.

```cpp
// C4793.cpp
// compile with: /c /clr /W3
// processor: x86
int asmfunc(void) {   // C4793, compiled as unmanaged, native code
   __asm {
      mov eax, 0
   }
}
```

```Output
warning C4793: 'asmfunc' : function is compiled as native code:
        Inline native assembly ('__asm') is not supported in managed code
```

다음 샘플 C4793를 생성합니다.

```cpp
// C4793_b.cpp
// compile with: /c /clr /W3
#include <setjmp.h>
jmp_buf test_buf;

void f() {
   setjmp(test_buf);   // C4793 warning
}
```

```Output
warning C4793: 'f' : function is compiled as native code:
        A function using '_setjmp' must be compiled as native
```