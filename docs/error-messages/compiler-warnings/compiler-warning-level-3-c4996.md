---
title: 컴파일러 경고 (수준 3) C4996
ms.date: 11/17/2017
f1_keywords:
- C4996
helpviewer_keywords:
- C4996
ms.assetid: 926c7cc2-921d-43ed-ae75-634f560dd317
ms.openlocfilehash: ef1bc46b64ccbe1374fd795a9b5d56e091b47f48
ms.sourcegitcommit: faa42c8a051e746d99dcebe70fd4bbaf3b023ace
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2019
ms.locfileid: "57816427"
---
# <a name="compiler-warning-level-3-c4996"></a>컴파일러 경고 (수준 3) C4996

컴파일러가 사용되지 않는 선언을 발견했습니다. **이 경고는 항상 의도적인 라이브러리 또는 결과 알 수 없는 사용 되지 않는 기호를 사용 하지 않아야 하는 포함 된 헤더 파일의 작성자 메시지.** 실제 경고 메시지의 사용 중단 한정자 또는 특성 선언의 사이트에서 지정 됩니다.

이들은 C 런타임 라이브러리 및 표준 라이브러리 전체 목록 아님에서 생성 된 몇 가지 일반적인 C4996 메시지입니다. 링크를 참조 하거나 문제를 해결 하려면 또는 경고를 해제 하는 방법을 계속 읽어주세요.

- [이 항목에 대 한 POSIX 이름은 사용 되지 않습니다. 대신 ISO C 및 c + +와 호환 되는 이름: *new_name*합니다. 자세한 내용은 온라인 도움말을 참조하세요.](#posix-function-names)

- [이 함수 또는 변수 안전 하지 않을 수 있습니다. 사용 하는 것이 좋습니다 *safe_version* 대신 합니다. 사용 중단을 사용 하지 \_CRT\_SECURE\_NO\_경고 합니다.  자세한 내용은 온라인 도움말을 참조하세요.](#unsafe-crt-library-functions)

- [' std::*function_name*::\_Unchecked\_반복기::\_Deprecate' 호출 std::*function_name*-안전 하지 않을 수 있는 매개 변수를 사용 하 여이 호출에 의존 전달 된 값이 정확한 지 확인 하기 위해 호출자입니다. 이 경고를 사용하지 않으려면 -D_SCL_SECURE_NO_WARNINGS를 사용합니다. Visual c + + ' 확인 된 반복기 '를 사용 하는 방법은 설명서를 참조 하세요.](#unsafe-standard-library-functions)

- [이 함수 또는 변수 최신 라이브러리 또는 운영 체제 기능으로 대체 되었습니다. 사용 하는 것이 좋습니다 *new_item* 대신 합니다. 자세한 내용은 온라인 도움말을 참조하세요.](#obsolete-crt-functions-and-variables)

## <a name="cause"></a>원인

컴파일러는 함수 또는로 표시 된 변수를 발견할 경우 C4996 [사용 되지 않음](../../cpp/deprecated-cpp.md) 사용 하 여를 `__declspec(deprecated)` 한정자를 함수, 클래스 멤버 또는 C + + 14가 있는 형식 정의 액세스 하려고 시도 하면 또는 [ \[ \[사용 되지 않음\] \] ](../../cpp/attributes.md) 특성입니다. 사용할 수는 `__declspec(deprecated)` 한정자 또는 `[[deprecated]]` 라이브러리 또는 헤더 파일 사용 되지 않는 함수, 변수, 멤버 또는 형식 정의 대 한 클라이언트 경고에서 직접 특성입니다.

## <a name="remarks"></a>설명

로 표시 된 여러 함수, 멤버 함수, 템플릿 함수 및 Visual Studio에서 라이브러리의 전역 변수 *사용 되지 않는*합니다. 이러한 함수는 사용 되지 않습니다 수 있습니다 기본 이름이, 안전 하지 않을 수도 있습니다는 더 안전한 변형이 구식 일 수 또는 합니다. 많은 사용 중단 메시지는 사용 되지 않는 함수 또는 전역 변수에 대 한 추천을 포함합니다.

이 문제를 해결 하려면 일반적으로 권장 제안 된 안전 하 게 또는 업데이트 된 함수 및 전역 변수를 대신 사용 하도록 코드를 변경 합니다. 이식성 이유로 기존 함수 또는 변수를 사용 하는 경우 경고를 해제할 수 있습니다.

### <a name="to-turn-the-warning-off-without-fixing-the-issue"></a>문제를 해결 하지 않고 경고를 해제 하려면

사용 하 여 특정 코드 줄에 대 한 경고를 해제할 수 있습니다 합니다 [경고](../../preprocessor/warning.md) pragma `#pragma warning(suppress : 4996)`합니다. 해제할 수 있습니다도 경고 파일 내에서 경고 pragma를 사용 하 여 `#pragma warning(disable : 4996)`입니다.

해제할 수 있습니다 경고를 전역적으로 명령줄 빌드에 사용 하 여 합니다 **/wd4996** 명령줄 옵션입니다.

Visual Studio IDE에 전체 프로젝트에 대 한 경고를 끄려면:

- 엽니다는 **속성 페이지** 프로젝트 대화 상자. 속성 페이지 대화 상자를 사용 하는 방법에 대 한 자세한 내용은 [속성 페이지](../../build/reference/property-pages-visual-cpp.md)합니다.
- 선택 된 **구성 속성**, **C/c + +** 를 **고급** 페이지입니다.
- 편집 된 **특정 경고 사용 안 함** 추가할 속성 `4996`합니다. 선택할 **확인** 변경 내용을 적용 하려면.

또한 특정 특정 클래스의 라이브러리에서 사용 되는 사용 중단 경고를 해제 하려면 전처리기 매크로 사용할 수 있습니다. 이러한 매크로 대 한 설명은 다음과 같습니다.

Visual Studio에서 전처리기 매크로 정의 합니다.

- 엽니다는 **속성 페이지** 프로젝트 대화 상자. 속성 페이지 대화 상자를 사용 하는 방법에 대 한 자세한 내용은 [속성 페이지](../../build/reference/property-pages-visual-cpp.md)합니다.
- 확장 **구성 속성 > C/c + + > 전처리기**합니다.
- 에 **전처리기 정의** 속성 매크로 이름을 추가 합니다. **확인** 을 선택하여 저장한 다음 프로젝트를 다시 빌드합니다.

특정 원본 파일에만 매크로 정의 하려면 줄을와 같은 추가 `#define EXAMPLE_MACRO_NAME` 헤더 파일이 포함 된 모든 줄 앞입니다.

## <a name="specific-c4996-messages"></a>특정 C4996 메시지

C4996 경고 및 오류의 일반적인 원인 중 다음과 같습니다.

### <a name="posix-function-names"></a>POSIX 함수 이름

**이 항목에 대 한 POSIX 이름은 사용 되지 않습니다. 대신 ISO C 및 c + +와 호환 되는 이름:** *new_name*합니다. **자세한 내용은 온라인 도움말을 참조 하세요.**

Microsoft의 C99 및 c++03 규칙 전역 함수 구현이 정의 된 이름에 맞게 CRT의 일부 POSIX 함수 이름이 변경 합니다. 원래 POSIX 이름만 지원 되지 않습니다. 함수 자체입니다. 대부분의 경우 표준 규격 이름을 만들기 위해 POSIX 함수 이름에 선행 밑줄이 추가되었습니다. 컴파일러는 원래 함수 이름에 대 한 사용 중단 경고를 실행 하 고 기본 이름을 제안 합니다.

이 문제를 해결 하려면 일반적으로 권장 제안 된 함수 이름을 대신 사용 하도록 코드를 변경 합니다. 그러나 업데이트 된 이름은 Microsoft 전용입니다. 이식성 이유로 기존 함수 이름을 사용 해야 할 경우에 이러한 경고를 해제할 수 있습니다. 원래 이름 아래에 있는 라이브러리의 POSIX 함수를 사용할 수 있습니다.

이러한 함수에 대 한 사용 중단 경고를 끄려면 전처리기 매크로 정의할  **\_CRT\_NONSTDC\_아니오\_경고**합니다. 옵션을 포함 하 여 명령줄에서이 매크로 정의할 수 있습니다 `/D_CRT_NONSTDC_NO_WARNINGS`합니다.

### <a name="unsafe-crt-library-functions"></a>안전 하지 않은 CRT 라이브러리 함수

**이 함수 또는 변수 안전 하지 않을 수 있습니다. 사용 하는 것이 좋습니다** *safe_version* **대신 합니다. 사용 중단을 사용 하지 \_CRT\_SECURE\_NO\_경고 합니다.  자세한 내용은 온라인 도움말을 참조하세요.**

일부 CRT 및 c + + 표준 라이브러리 함수 및 전역 더 안전한 버전을 위해 Microsoft에 사용 되지 않습니다. 대부분의 경우 사용 되지 않는 함수는 검사 되지 않은 읽기 또는 심각한 보안 문제가 발생할 수 있는 버퍼에 쓰기 액세스를 허용 합니다. 컴파일러는 이러한 함수에 대해 사용 중단 경고를 실행하고 기본 설정 함수를 제안합니다.

이 문제를 해결 하려면 함수 또는 변수를 사용 하 여 권장 *safe_version* 대신 합니다. 버퍼 덮어쓰기 불가능 또는 코드에서 발생 하는 overread 이식성 이유로 코드를 변경할 수 없습니다를 확인 한 경우 경고를 해제할 수 있습니다.

CRT에서 이러한 함수에 대 한 사용 중단 경고를 해제 하려면 정의  **\_CRT\_SECURE\_아니오\_경고**합니다. 사용 되지 않는 전역 변수에 대 한 경고를 해제 하려면 정의  **\_CRT\_SECURE\_아니오\_경고\_GLOBALS**합니다. 이러한 사용 되지 않는 함수 및 전역 변수에 대 한 자세한 내용은 참조 하세요. [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md) 고 [안전한 라이브러리: C + + 표준 라이브러리](../../standard-library/safe-libraries-cpp-standard-library.md)합니다.

### <a name="unsafe-standard-library-functions"></a>안전 하지 않은 표준 라이브러리 함수

__' std::__*function_name*__::\_Unchecked\_반복기::\_Deprecate' 호출 std::__*function_name* **-안전 하지 않을 수 있는 매개 변수를 사용 하 여이 호출은 호출자가 전달 된 값이 올바른지 확인에 의존 합니다. -D를 사용 하 여이 경고를 사용 하지 않으려면\_SCL\_SECURE\_NO\_경고 합니다. Visual c + + ' 확인 된 반복기 '를 사용 하는 방법은 설명서를 참조 하세요.**

이 경고는 특정 c + + 표준 라이브러리 템플릿 함수는 매개 변수의 정확성을 검사 하지 않습니다 때문에 디버그 빌드에서 나타납니다. 대부분의 경우에서 인지 정보가 부족 컨테이너 경계를 확인 하는 함수를 사용할 수 있으므로 함수를 사용 하 여 반복기를 올바르게 사용할 수 있습니다. 이 경고 원본 프로그램에서 심각한 보안 취약점이 있을 수 있으므로 이러한 함수 사용을 확인할 수 있습니다. 자세한 내용은 [Checked Iterators](../../standard-library/checked-iterators.md)을 참조하세요.

한 요소 포인터를 전달 하는 경우이 경고 디버그 모드에서 표시 예를 들어 `std::copy` 일반 배열 대신 합니다. 이 문제를 해결 하려면 라이브러리에서 배열 범위를 확인 하 고 범위 검사를 수행할 수 있도록 적절 하 게 선언 된 배열을 사용 합니다.

```cpp
// C4996_copyarray.cpp
// compile with: cl /c /W4 /D_DEBUG C4996_copyarray.cpp
#include <algorithm>

void example(char const * const src) {
    char dest[1234];
    char * pdest3 = dest + 3;
    std::copy(src, src + 42, pdest3); // C4996
    std::copy(src, src + 42, dest);   // OK, copy can tell that dest is 1234 elements
}
```

몇 가지 표준 라이브러리 알고리즘은 C + + 14에서 "이중 범위" 버전이 하도록 업데이트 되었습니다. 이중 범위 버전을 사용 하는 경우 두 번째 범위 확인의 필요한 범위를 제공 합니다.

```cpp
// C4996_containers.cpp
// compile with: cl /c /W4 /D_DEBUG C4996_containers.cpp
#include <algorithm>

bool example(
    char const * const left,
    const size_t leftSize,
    char const * const right,
    const size_t rightSize)
{
    bool result = false;
    result = std::equal(left, left + leftSize, right); // C4996
    // To fix, try this form instead:
    // result = std::equal(left, left + leftSize, right, right + rightSize); // OK
    return result;
}
```

이 예제에서는 몇 가지 방법은 표준 라이브러리를 사용 하 여 반복기 사용을 확인 수 및 확인 되지 않은 사용 현황 위험할 수 있습니다.

```cpp
// C4996_standard.cpp
// compile with: cl /EHsc /W4 /MDd C4996_standard.cpp
#include <algorithm>
#include <array>
#include <iostream>
#include <iterator>
#include <numeric>
#include <string>
#include <vector>

using namespace std;

template <typename C> void print(const string& s, const C& c) {
    cout << s;

    for (const auto& e : c) {
        cout << e << " ";
    }

    cout << endl;
}

int main()
{
    vector<int> v(16);
    iota(v.begin(), v.end(), 0);
    print("v: ", v);

    // OK: vector::iterator is checked in debug mode
    // (i.e. an overrun triggers a debug assertion)
    vector<int> v2(16);
    transform(v.begin(), v.end(), v2.begin(), [](int n) { return n * 2; });
    print("v2: ", v2);

    // OK: back_insert_iterator is marked as checked in debug mode
    // (i.e. an overrun is impossible)
    vector<int> v3;
    transform(v.begin(), v.end(), back_inserter(v3), [](int n) { return n * 3; });
    print("v3: ", v3);

    // OK: array::iterator is checked in debug mode
    // (i.e. an overrun triggers a debug assertion)
    array<int, 16> a4;
    transform(v.begin(), v.end(), a4.begin(), [](int n) { return n * 4; });
    print("a4: ", a4);

    // OK: Raw arrays are checked in debug mode
    // (i.e. an overrun triggers a debug assertion)
    // NOTE: This applies only when raw arrays are
    // given to C++ Standard Library algorithms!
    int a5[16];
    transform(v.begin(), v.end(), a5, [](int n) { return n * 5; });
    print("a5: ", a5);

    // WARNING C4996: Pointers cannot be checked in debug mode
    // (i.e. an overrun triggers undefined behavior)
    int a6[16];
    int * p6 = a6;
    transform(v.begin(), v.end(), p6, [](int n) { return n * 6; });
    print("a6: ", a6);

    // OK: stdext::checked_array_iterator is checked in debug mode
    // (i.e. an overrun triggers a debug assertion)
    int a7[16];
    int * p7 = a7;
    transform(v.begin(), v.end(),
        stdext::make_checked_array_iterator(p7, 16),
        [](int n) { return n * 7; });
    print("a7: ", a7);

    // WARNING SILENCED: stdext::unchecked_array_iterator
    // is marked as checked in debug mode, but it performs no checking,
    // so an overrun triggers undefined behavior
    int a8[16];
    int * p8 = a8;
    transform( v.begin(), v.end(),
        stdext::make_unchecked_array_iterator(p8),
        [](int n) { return n * 8; });
    print("a8: ", a8);
}
```

코드에서 버퍼 오버런이 경고를 트리거하는 표준 라이브러리 함수에는 오류를 가질 수 없음을 확인 하는 경우에이 경고를 해제 하는 것이 좋습니다. 이러한 함수에 대 한 경고를 해제 하려면 정의  **\_SCL\_SECURE\_아니오\_경고**합니다.

### <a name="checked-iterators-enabled"></a>확인 된 반복기를 사용 하도록 설정

로 컴파일하는 경우 확인 된 반복기를 사용 하지 않는 경우에 C4996 발생할 수 있습니다 `_ITERATOR_DEBUG_LEVEL` 1 또는 2로 정의 합니다. 디버그 모드 빌드의 경우 기본적으로 2를 일반 정품 빌드에는 0으로 설정 됩니다. 자세한 내용은 [Checked Iterators](../../standard-library/checked-iterators.md) 를 참조하세요.

```cpp
// C4996_checked.cpp
// compile with: /EHsc /W4 /MDd C4996_checked.cpp
#define _ITERATOR_DEBUG_LEVEL 2

#include <algorithm>
#include <iterator>

using namespace std;
using namespace stdext;

int main() {
    int a[] = { 1, 2, 3 };
    int b[] = { 10, 11, 12 };
    copy(a, a + 3, b + 1);   // C4996
    // try the following line instead:
    // copy(a, a + 3, checked_array_iterator<int *>(b, 3));   // OK
}
```

### <a name="unsafe-mfc-or-atl-code"></a>안전 하지 않은 MFC 또는 ATL 코드

C4996은 보안상의 이유로 되지 않는 MFC 나 ATL 함수를 사용 하는 경우에 발생할 수 있습니다.

이 문제를 해결 하려면 업데이트 된 함수를 대신 사용 하도록 코드를 변경 하는 것이 좋습니다.

이러한 경고를 표시 하는 방법에 대 한 자세한 내용은 [_AFX_SECURE_NO_WARNINGS](../../mfc/reference/diagnostic-services.md#afx_secure_no_warnings)합니다.

### <a name="obsolete-crt-functions-and-variables"></a>사용 되지 않는 CRT 함수 및 변수

**이 함수 또는 변수 최신 라이브러리 또는 운영 체제 기능으로 대체 되었습니다. 사용 하는 것이 좋습니다** *new_item* **대신 합니다. 자세한 내용은 온라인 도움말을 참조하세요.**

일부 라이브러리 함수 및 전역 변수는 구식으로 사용되지 않습니다. 이러한 함수 및 변수는 이후 버전의 라이브러리에서 제거될 수도 있습니다. 컴파일러는 이러한 항목에 대해 사용 중단 경고를 실행하고 기본 설정 대체 항목을 제안합니다.

이 문제를 해결 하려면 제안 된 함수 또는 변수를 사용 하도록 코드를 변경 하는 것이 좋습니다.

이러한 항목에 대 한 사용 중단 경고를 해제 하려면 정의  **\_CRT\_OBSOLETE\_아니오\_경고**합니다. 자세한 내용은 사용되지 않는 함수 또는 변수에 대한 설명서를 참조하세요.

### <a name="marshalling-errors-in-clr-code"></a>CLR 코드의 마샬링 오류

C4996은 CLR 마샬링 라이브러리를 사용 하는 경우에 발생할 수 있습니다. 이 경우 C4996은 경고가 아니라 오류입니다. 사용 하는 경우이 오류가 발생 [marshal_as](../../dotnet/marshal-as.md) 필요로 하는 두 데이터 형식 간에 변환 하는 [marshal_context 클래스](../../dotnet/marshal-context-class.md)합니다. 마샬링 라이브러리가 변환을 지원 하지 않는 경우에이 오류가 발생할 수 있습니다. 마샬링 라이브러리에 대한 자세한 내용은 [Overview of Marshaling in C++](../../dotnet/overview-of-marshaling-in-cpp.md)를 참조하세요.

마샬링 라이브러리에서 변환 하는 컨텍스트가 필요 하기 때문에이 예제에서는 C4996이 생성을 `System::String` 에 `const char *`합니다.

```cpp
// C4996_Marshal.cpp
// compile with: /clr
// C4996 expected
#include <stdlib.h>
#include <string.h>
#include <msclr\marshal.h>

using namespace System;
using namespace msclr::interop;

int main() {
   String^ message = gcnew String("Test String to Marshal");
   const char* result;
   result = marshal_as<const char*>( message );
   return 0;
}
```

## <a name="example-user-defined-deprecated-function"></a>예제: 사용 되지 않는 사용자 정의 함수

특정 함수의 사용을 더 이상 권장 하는 경우 호출자에 게 경고 하기 위해 사용자 고유의 코드에서 사용 되지 않는 특성을 사용할 수 없습니다. 이 예제에서는 C4996 함수 사용 되는 줄과 사용 되지 않는 함수를 선언 하는 줄에 대해 생성 됩니다.

```cpp
// C4996.cpp
// compile with: /W3
// C4996 warning expected
#include <stdio.h>

// #pragma warning(disable : 4996)
void func1(void) {
   printf_s("\nIn func1");
}

__declspec(deprecated) void func1(int) {
   printf_s("\nIn func2");
}

int main() {
   func1();
   func1(1);    // C4996
}
```
