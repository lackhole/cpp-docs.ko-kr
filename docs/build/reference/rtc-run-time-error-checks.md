---
title: /RTC(런타임 오류 검사)
ms.date: 11/04/2016
f1_keywords:
- /rtc
- VC.Project.VCCLCompilerTool.SmallerTypeCheck
- VC.Project.VCCLCompilerTool.UninitializedVariableCheck
- VC.Project.VCCLCompilerTool.StackFrameCheck
- VC.Project.VCCLCompilerTool.BasicRuntimeChecks
helpviewer_keywords:
- /RTCs compiler option [C++]
- -RTC1 compiler option [C++]
- run-time errors, error checks
- -RTCu compiler option [C++]
- /RTC1 compiler option [C++]
- /RTCc compiler option [C++]
- /RTCu compiler option [C++]
- __MSVC_RUNTIME_CHECKS macro
- -RTCs compiler option [C++]
- RTCs compiler option
- RTC1 compiler option
- run-time errors, run-time checks
- run-time checks, /RTC option
- RTCu compiler option
- RTCc compiler option
- -RTCc compiler option [C++]
ms.assetid: 9702c558-412c-4004-acd5-80761f589368
ms.openlocfilehash: a830ff5b8ba4b7fcd95eb462f899f2eadce6de11
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62318552"
---
# <a name="rtc-run-time-error-checks"></a>/RTC(런타임 오류 검사)

사용 하도록 설정 하 여 런타임 오류 검사 기능을 함께에서 사용 하지 않도록 설정 하는 데 사용 합니다 [runtime_checks](../../preprocessor/runtime-checks.md) pragma입니다.

## <a name="syntax"></a>구문

```
/RTC1
/RTCc
/RTCs
/RTCu
```

## <a name="arguments"></a>인수

**1**<br/>
해당 **/RTC**`su`합니다.

**c**<br/>
값에 보고서는 더 작은 데이터 형식 및 데이터 손실의 결과에 할당 됩니다. 예를 들어, 값 형식 `short 0x101` 형식의 변수에 할당 된 `char`합니다.

이 옵션으로 경우 보고 있는 있습니다 예를 들어 truncate의 처음 8 비트를 하려는 경우는 `int` 로 반환 된 `char`합니다. 때문에 **/RTC** `c` 런타임 오류가 발생의 결과로 런타임 오류를 방지 하는 데 필요한 정보 가릴 수 정보가 할당으로 인해 손실 된 경우 **/RTC** `c`. 예를 들어:

```
#include <crtdbg.h>

char get8bits(int value, int position) {
   _ASSERT(position < 32);
   return (char)(value >> position);
   // Try the following line instead:
   // return (char)((value >> position) & 0xff);
}

int main() {
   get8bits(12341235,3);
}
```

**s**<br/>
스택 프레임 런타임 오류 검사, 다음과 같습니다.

- 로컬 변수를 0이 아닌 값으로 초기화 합니다. 이렇게 하면 디버그 모드에서 실행 하는 경우에 표시 되지 않는 버그를 식별 합니다. 스택 변수 컴파일러 최적화는 릴리스 빌드에서 스택 변수 때문에 릴리스 빌드에 비해 디버그 빌드에서 0 계속 되도록 레이아웃이 있습니다. 일단 프로그램에는 해당 스택 영역 사용 되었으면, 컴파일러에서 0으로 다시 설정 되지 않습니다. 따라서 동일한 스택 영역을 사용 하는 후속, 초기화 되지 않은 스택 변수 값이 스택 메모리 이전 사용에서 남은 반환할 수 있습니다.

- 배열과 같은 로컬 변수의 언더런 및 오버런 감지 합니다. **/RTC** `s` 컴파일러 패딩 구조체 내에서 발생 하는 메모리에 액세스할 때 오버런을 탐지 하지 못합니다. 안쪽 여백을 사용 하 여 발생할 수 있습니다 [맞춤](../../cpp/align-cpp.md)를 [/Zp (구조체 멤버 맞춤)](zp-struct-member-alignment.md), 또는 [팩](../../preprocessor/pack.md), 컴파일러에 안쪽 여백을 추가 하는 방식에서 구조 요소를 정렬 하는 경우.

- 스택 포인터 손상 감지 하는 스택 포인터 확인 합니다. 스택 포인터 손상 호출 규칙 불일치 때문일 수 있습니다. 예를 들어 함수 포인터를 사용 하면 함수 호출으로 내보낸 DLL에 [__stdcall](../../cpp/stdcall.md) 함수에 대 한 포인터를 선언 하지만 [__cdecl](../../cpp/cdecl.md)합니다.

**u**<br/>
초기화 되지 않은 변수를 사용 하는 시기를 보고 합니다. 예를 들어, 생성 하는 명령 `C4701` 에서 런타임 오류가 발생할 수도 있습니다 **/RTC**`u`합니다. 생성 하는 모든 명령 [컴파일러 경고 (수준 1 및 수준 4) C4700](../../error-messages/compiler-warnings/compiler-warning-level-1-and-level-4-c4700.md) 아래에서 런타임 오류가 생성 됩니다 **/RTC**`u`합니다.

그러나 다음 코드 조각은 고려 합니다.

```cpp
int a, *b, c;
if ( 1 )
b = &a;
c = a;  // No run-time error with /RTCu
```

변수 초기화 될 수 없습니다, 경우 하 여 런타임 시 보고 되지 것입니다 **/RTC**`u`합니다. 예를 들어 변수는 포인터를 통해 별칭이 지정 되 면 컴파일러는 추적 변수 및 초기화 되지 않은 사용을 보고 합니다. 실제로 해당 주소를 수행 하 여 변수를 초기화할 수 있습니다. & 연산자는 같은이 이런 경우에 할당 연산자입니다.

## <a name="remarks"></a>설명

런타임 오류 검사는 실행 중인 코드에서 문제를 발견 하는 방법 자세한 내용은 참조 하세요. [방법: 네이티브 런타임 검사 사용](/visualstudio/debugger/how-to-use-native-run-time-checks)을 참조하세요.

프로그램 중 하나를 사용 하 여 명령줄에서 컴파일하는 경우는 **/RTC** 컴파일러 옵션, pragma [최적화](../../preprocessor/optimize.md) 코드의 지침에 자동으로 실패 합니다. 즉, 런타임 오류 검사 (최적화) 릴리스 빌드에서 사용할 수 없습니다.

기능을 사용할지 **/RTC** 개발 빌드; **/RTC** 정품 빌드에 쓰일 수 없습니다. **/RTC** 컴파일러 최적화를 사용 하 여 사용할 수 없습니다 ([/O 옵션 (코드 최적화)](o-options-optimize-code.md)). 프로그램 이미지를 사용 하 여 빌드한 **/RTC** 약간 크고 사용 하 여 빌드된 이미지 보다 약간 느리지만 됩니다 **/Od** (최대 5% 보다 느림을 **/Od** 빌드).

__MSVC_RUNTIME_CHECKS 전처리기 지시문을 사용할 때 정의 됩니다 **/RTC** 옵션 또는 [/GZ](gz-enable-stack-frame-run-time-error-checking.md)합니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. **C/C++** 폴더를 클릭합니다.

1. 클릭 합니다 **코드 생성** 속성 페이지.

1. 다음 속성 중 하나 또는 모두를 수정 합니다. **기본 런타임 검사** 나 **검사를 더 작은 입력**합니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.BasicRuntimeChecks%2A> 및 <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.SmallerTypeCheck%2A> 속성을 참조하십시오.

## <a name="see-also"></a>참고자료

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)<br/>
[방법: 네이티브 런타임 검사 사용](/visualstudio/debugger/how-to-use-native-run-time-checks)
