---
title: static_assert
ms.date: 11/04/2016
f1_keywords:
- static_assert_cpp
helpviewer_keywords:
- C++ keywords, static_assert
- C2338
- assertions [C++], static_assert
- static_assert
ms.assetid: 28dd3668-e78c-4de8-ba68-552084743426
ms.openlocfilehash: d5ef1ba45001a2b1a3ee1f2da46f66224857b070
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62330653"
---
# <a name="staticassert"></a>static_assert

컴파일 시 소프트웨어 어설션을 테스트합니다. 지정 된 상수 식이 FALSE 인 경우 컴파일러가 하나를 제공 하 고 컴파일은 C2338; 오류로 인해 실패 하는 경우 지정된 된 메시지가 표시 하는 이 고, 그렇지 선언에 영향을 주지 않습니다.

## <a name="syntax"></a>구문

```
static_assert( constant-expression, string-literal );

static_assert( constant-expression ); // Visual Studio 2017 and later
```

#### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*constant-expression*|부울로 변환할 수 있는 정수 계열 상수 식입니다.<br /><br /> 계산된 된 식이 0 이면 (false)를 *문자열 리터럴* 매개 변수가 표시 되 고 컴파일이 오류와 함께 실패 합니다. 식이 0이 아닌 값 (true)를 **static_assert** 선언에 영향을 주지 않습니다.|
|*string-literal*|경우에 표시 되는 메시지를는 *상수-식* 매개 변수가 0입니다. 메시지는 문자열의 문자를 [기본 문자 집합](../c-language/ascii-character-set.md) 는 컴파일러의 아니라 [멀티 바이트 또는 와이드 문자](../c-language/multibyte-and-wide-characters.md)합니다.|

## <a name="remarks"></a>설명

합니다 *상수-식* 의 매개 변수를 **static_assert** 선언 나타냅니다는 *소프트웨어 어설션을*합니다. 소프트웨어 어설션은 프로그램의 특정 지점에서 true가 될 조건을 지정합니다. 조건이 true 인 경우는 **static_assert** 선언에 영향을 주지 않습니다. 조건이 false 이면 어설션이 실패 하는 컴파일러의 메시지를 표시 *문자열 리터럴* 매개 변수 및 오류와 함께 컴파일이 실패 합니다. Visual Studio 2017 이상 버전에서는 문자열 리터럴 매개 변수는 선택 사항입니다.

합니다 **static_assert** 선언은 컴파일 시 소프트웨어 어설션을 테스트 합니다. 반면에 [assert 매크로, _assert, _wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md) 매크로 런타임 시 소프트웨어 어설션을 테스트 하 고 공간 또는 시간의 런타임 비용을 발생 시킵니다. 합니다 **static_assert** 선언은 디버깅 템플릿에 템플릿 인수에 포함 될 수 있으므로 특히 유용 합니다 *상수-식* 매개 변수입니다.

컴파일러를 검사 합니다 **static_assert** 선언이 발견 될 때 구문 오류에 대 한 선언을 합니다. 컴파일러는 계산 된 *상수-식* 템플릿 매개 변수에 종속 되지 않는 경우에 즉시 매개 변수. 컴파일러는 계산이 고, 그렇지 합니다 *상수-식* 템플릿이 인스턴스화될 때 매개 변수입니다. 그 결과, 컴파일러는 선언이 발생할 때 진단 메시지를 한 번 내보내고 템플릿이 인스턴스화될 때 다시 한 번 메시지를 내보낼 수 있습니다.

사용할 수는 **static_assert** 네임 스페이스, 클래스 또는 블록 범위가 있는 키워드입니다. (합니다 **static_assert** 키워드는 네임 스페이스 범위에서 사용할 수 있으므로 새 이름을 프로그램에 알리지 하는 경우에 기술적으로 선언 합니다.)

## <a name="description"></a>설명

다음 예제에서는 **static_assert** 선언은 네임 스페이스 범위를 갖습니다. 컴파일러가 `void *` 형식의 크기를 알고 있기 때문에 식이 즉시 계산됩니다.

## <a name="example"></a>예제

```cpp
static_assert(sizeof(void *) == 4, "64-bit code generation is not supported.");
```

## <a name="description"></a>설명

다음 예제에서는 **static_assert** 선언은 클래스 범위를 갖습니다. 합니다 **static_assert** 템플릿 매개 변수 인지 확인을 *일반 이전 데이터* (POD) 형식입니다. 컴파일러 검사를 **static_assert** 선언 되지만 평가 되지 않는 경우 선언 합니다 *상수-식* 까지 매개 변수는 `basic_string` 에서클래스템플릿이인스턴스화될`main()`.

## <a name="example"></a>예제

```cpp
#include <type_traits>
#include <iosfwd>
namespace std {
template <class CharT, class Traits = std::char_traits<CharT> >
class basic_string {
    static_assert(std::is_pod<CharT>::value,
                  "Template argument CharT must be a POD type in class template basic_string");
    // ...
    };
}

struct NonPOD {
    NonPOD(const NonPOD &) {}
    virtual ~NonPOD() {}
};

int main()
{
    std::basic_string<char> bs;
}
```

## <a name="description"></a>설명

다음 예제에서는 **static_assert** 선언은 블록 범위를 갖습니다. 합니다 **static_assert** VMPage 구조체의 크기는 시스템의 가상 메모리 pagesize 같음 인지 확인 합니다.

## <a name="example"></a>예제

```cpp
#include <sys/param.h> // defines PAGESIZE
class VMMClient {
public:
    struct VMPage { // ...
           };
    int check_pagesize() {
    static_assert(sizeof(VMPage) == PAGESIZE,
        "Struct VMPage must be the same size as a system virtual memory page.");
    // ...
    }
// ...
};
```

## <a name="see-also"></a>참고자료

[어설션 및 사용자 제공 메시지(C++)](../cpp/assertion-and-user-supplied-messages-cpp.md)<br/>
[#error 지시문(C/C++)](../preprocessor/hash-error-directive-c-cpp.md)<br/>
[assert Macro, _assert, _wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md)<br/>
[템플릿](../cpp/templates-cpp.md)<br/>
[ASCII 문자 집합](../c-language/ascii-character-set.md)<br/>
[선언 및 정의](declarations-and-definitions-cpp.md)