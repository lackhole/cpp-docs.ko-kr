---
title: /clr 제한
ms.date: 11/04/2016
helpviewer_keywords:
- /clr compiler option [C++], restrictions
ms.assetid: 385f6462-2c68-46d6-810e-469553ead447
ms.openlocfilehash: 21b7ead553871854c73021756eb2086f9e6e7393
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62294462"
---
# <a name="clr-restrictions"></a>/clr 제한

사용 하 여 다음과 같은 제한 사항이 **/clr**:

- 구조적된 예외 처리기에서에 대 한 제한은 사용 하 여 `_alloca` 사용 하 여 컴파일하면 **/clr**합니다. 자세한 내용은 [_alloca](../../c-runtime-library/reference/alloca.md)합니다.

- 런타임 오류 검사를 사용 하 여 유효 하지 않은 **/clr**합니다. 자세한 내용은 [방법: 네이티브 런타임 검사 사용](/visualstudio/debugger/how-to-use-native-run-time-checks)을 참조하세요.

- 때 **/clr** 은 인라인 어셈블리의 사용에 적용 한 다음 지침만 표준 C++ 구문을 사용 하는 프로그램을 컴파일하는 데 사용 합니다.

  - 에서는 기본 스택 레이아웃 지식이 있다고 가정 하는 인라인 어셈블리 코드에 호출 규칙 현재 함수의 경우 또는 다른 하위 수준 정보는 컴퓨터에 대 한 외부에서 실패할 수 있습니다 기술 자료 관리 되는 함수의 스택 프레임에 적용 되는. 인라인 어셈블리 코드를 포함 하는 함수는 별도 하지 않고 컴파일된 모듈에 저장 된 것 처럼 관리 되지 않는 함수도 생성 됩니다 **/clr**합니다.

  - 인라인 어셈블리 코드를 복사 하 여 생성할 함수 매개 변수를 전달 하는 지원 되지 않습니다.

- 합니다 [vprintf 함수](../../c-runtime-library/vprintf-functions.md) 로 컴파일된 프로그램에서 호출할 수 없습니다 **/clr**합니다.

- 합니다 [naked](../../cpp/naked-cpp.md) [__declspec](../../cpp/declspec.md) /clr 한정자는 무시 됩니다.

- 변환기 함수에 설정한 [_set_se_translator](../../c-runtime-library/reference/set-se-translator.md) 비관리 코드에서 catch만 적용 됩니다. 참조 [예외 처리](../../extensions/exception-handling-cpp-component-extensions.md) 자세한 내용은 합니다.

- 함수 포인터의 비교를 사용할 수 없습니다 **/clr**합니다.

- 완전히 프로토타입화 되지 않은 함수를 사용할 수 없습니다 **/clr**합니다.

- 다음 컴파일러 옵션을 사용 하 여 지원 되지 않습니다 **/clr**:

  - **/ EHsc** 하 고 **/EHs** (**/clr** 의미 **/EHa** (참조 [/EH (예외 처리 모델)](eh-exception-handling-model.md))

  - **/fp: strict** 하 고 **/fp: 제외한** (참조 [/fp (부동 소수점 동작 지정)](fp-specify-floating-point-behavior.md))

  - [/Zd](z7-zi-zi-debug-information-format.md)

  - [/Gm](gm-enable-minimal-rebuild.md)

  - [/MT](md-mt-ld-use-run-time-library.md)

  - [/RTC](rtc-run-time-error-checks.md)

  - [/ZI](z7-zi-zi-debug-information-format.md)

- 조합 된 `_STATIC_CPPLIB` 전처리기 정의 (`/D_STATIC_CPPLIB`) 및 **/clr** 컴파일러 옵션이 지원 되지 않습니다. 왜냐하면이 정의 인해 정적 다중 스레드 C++ 표준 라이브러리에서 지원 되지 않는 사용 하 여 연결 하려면 응용 프로그램입니다. 자세한 내용은 참조는 [/MD, /MT, /LD (런타임 라이브러리 사용)](md-mt-ld-use-run-time-library.md) 항목입니다.

- 사용 하는 경우 **/Zi** 사용 하 여 **/clr**에 성능 문제. 자세한 내용은 [/Zi](z7-zi-zi-debug-information-format.md)합니다.

- 도 지정 하지 않고 루틴을 출력 하는.NET Framework를 와이드 문자를 전달 [/zc: wchar_t](zc-wchar-t-wchar-t-is-native-type.md) 또는 문자를 캐스팅 하지 않고도 `__wchar_t` 로 표시 되도록 출력 하면는 `unsigned short int`합니다. 예를 들어:

    ```cpp
    Console::WriteLine(L' ')              // Will output 32.
    Console::WriteLine((__wchar_t)L' ')   // Will output a space.
    ```

- [/GS](gs-buffer-security-check.md) 로 컴파일하는 경우 무시 됩니다 **/clr**함수에서가 아닌 경우 `#pragma` [관리 되지 않는](../../preprocessor/managed-unmanaged.md) 함수는 네이티브로 컴파일해야 합니다.이 경우에 컴파일러에서 생성 또는 경고 C4793 기본적으로 해제 되어 있습니다.

- 참조 [/ENTRY](entry-entry-point-symbol.md) 관리 되는 응용 프로그램의 함수 서명 요구 사항에 대 한 합니다.

- 응용 프로그램을 컴파일하면 **/openmp** 하 고 **/clr** 단일 appdomain 프로세스에서 실행할 수 있습니다.  참조 [/openmp (OpenMP 2.0 지원 활성화)](openmp-enable-openmp-2-0-support.md) 자세한 내용은 합니다.

- 함수는 가변 개수의 인수 (varargs)를 사용 하는 네이티브 함수로 생성 됩니다. 가변 인수 위치에 있는 관리 되는 데이터 형식은 네이티브 형식으로 마샬링됩니다. <xref:System.String?displayProperty=fullName> 형식은 실제로 와이드 문자 문자열 하지만 싱글바이트 문자열로 마샬링됩니다. 따라서 printf 지정자는 %%S (wchar_t *)입니다, 경우 마샬링합니다 %s 문자열을 대신 합니다.

- Va_arg 매크로 사용할 때 사용 하 여 컴파일할 때 예기치 않은 결과가 발생할 수 있습니다 **/clr: pure**합니다. 자세한 내용은 [va_arg, va_copy, va_end, va_start](../../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)합니다. **/clr: pure** 및 **/clr: safe** Visual Studio 2015에서 사용 되지 않고 Visual Studio 2017에서 지원 되지 않는 컴파일러 옵션입니다. "순수" 또는 "안전한" 해야 하는 코드를 이식 해야 C#입니다.

- 관리 코드, 매개 변수 정보 (함수 인수);를 가져오려면 스택 워크는 모든 함수에서에서의 호출 하지 않아야 P/Invoke 계층 하면 해당 정보가 더 수 있습니다.  예를 들어, 프록시/스텁이 있는 컴파일되지 않습니다 **/clr**합니다.

- 함수를 가능 하면 관리 코드로 컴파일되지만 일부 C++ 구문 관리 코드로 변환할 수 있습니다.  함수에서 함수 별로이 결정 됩니다. 일부 함수의 관리 코드로 변환할 수 함수 전체 변환 됩니다 네이티브 코드를 대신 합니다. 컴파일러에서 관리 되는 코드를 생성 하지 않도록 하는 다음과 같은 경우.

  - 컴파일러에서 생성 한 썽크 또는 도우미 함수입니다. 네이티브 썽크는 가상 함수 호출을 포함 한 함수 포인터를 통해 모든 함수 호출에 대해 생성 됩니다.

  - 호출 함수 `setjmp` 또는 `longjmp`합니다.

  - 특정 내장 루틴을 사용 하 여 컴퓨터 리소스를 직접 조작 하는 함수입니다. 사용 예를 들어 `__enable` 하 고 `__disable`, `_ReturnAddress` 및 `_AddressOfReturnAddress`, 멀티미디어 내장 함수는 네이티브 코드에서 모든 결과 또는 합니다.

  - 다음 함수는 `#pragma unmanaged` 지시문입니다. (유의 역, `#pragma managed`, 에서도 지원 됩니다.)

  - 함수에 대 한 참조를 포함 하는 정렬 된 형식, 즉, 형식을 사용 하 여 선언 `__declspec(align(...))`합니다.

## <a name="see-also"></a>참고자료

- [/clr(공용 언어 런타임 컴파일)](clr-common-language-runtime-compilation.md)
