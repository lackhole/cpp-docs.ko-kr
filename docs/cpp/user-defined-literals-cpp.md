---
title: 사용자 정의 리터럴 (C++)
ms.date: 11/04/2016
ms.assetid: ff4a5bec-f795-4705-a2c0-53788fd57609
ms.openlocfilehash: 1de94b43423bb5b420be29d3cace146e265a1459
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62392117"
---
# <a name="user-defined-literals--c"></a>사용자 정의 리터럴 (C++)

리터럴의 5가지 주요 범주는 정수, 문자, 부동 소수점, 문자열, 부울 및 포인터입니다.  C++ 11부터 이러한 범주에 따라 사용자 고유의 리터럴을 정의하여 일반적인 구문에 대한 구문 바로 가기를 제공하고 형식 안전성을 높일 수 있습니다. 예를 들어 Distance 클래스가 있다고 가정합니다. 킬로미터와 마일에 대해 리터럴을 하나씩 정의하고 간단히 auto d = 42.0_km or auto d = 42.0_mi를 작성하여 사용자가 측정 단위를 명시적으로 지정하도록 장려할 수 있습니다. 사용자 정의 리터럴에 성능상의 이점이나 단점은 없습니다. 주로 편의상 또는 컴파일 시간 형식 추론을 위해 사용됩니다. 표준 라이브러리의 시간 및 기간 작업에 대 한 사용자 정의 리터럴 및에 대 한 std: string, std:: complex, 단위는 \<chrono > 헤더:

```cpp
Distance d = 36.0_mi + 42.0_km;         // Custom UDL (see below)
    std::string str = "hello"s + "World"s;  // Standard Library <string> UDL
    complex<double> num =
        (2.0 + 3.01i) * (5.0 + 4.3i);       // Standard Library <complex> UDL
    auto duration = 15ms + 42h;             // Standard Library <chrono> UDLs
```

## <a name="user-defined-literal-operator-signatures"></a>사용자 정의 리터럴 연산자 서명

사용자 정의 리터럴을 정의 하 여 구현 하는 **연산자 ""** 다음 형식 중 하나를 사용 하 여 네임 스페이스 범위에서:

```cpp
ReturnType operator "" _a(unsigned long long int);   // Literal operator for user-defined INTEGRAL literal
ReturnType operator "" _b(long double);              // Literal operator for user-defined FLOATING literal
ReturnType operator "" _c(char);                     // Literal operator for user-defined CHARACTER literal
ReturnType operator "" _d(wchar_t);                  // Literal operator for user-defined CHARACTER literal
ReturnType operator "" _e(char16_t);                 // Literal operator for user-defined CHARACTER literal
ReturnType operator "" _f(char32_t);                 // Literal operator for user-defined CHARACTER literal
ReturnType operator "" _g(const     char*, size_t);  // Literal operator for user-defined STRING literal
ReturnType operator "" _h(const  wchar_t*, size_t);  // Literal operator for user-defined STRING literal
ReturnType operator "" _i(const char16_t*, size_t);  // Literal operator for user-defined STRING literal
ReturnType operator "" _g(const char32_t*, size_t);  // Literal operator for user-defined STRING literal
ReturnType operator "" _r(const char*);              // Raw literal operator
template<char...> ReturnType operator "" _t();       // Literal operator template
```

앞의 예제에서 연산자 이름은 사용자가 제공하는 이름에 대한 자리 표시자이지만 선행 밑줄이 필요합니다. 표준 라이브러리만 밑줄 없이 리터럴을 정의할 수 있습니다. 반환 형식에서 변환 또는 리터럴이 수행하는 기타 작업을 사용자 지정할 수 있습니다. 또한 이러한 모든 연산자를 `constexpr`로 정의할 수 있습니다.

## <a name="cooked-literals"></a>가공된 리터럴

소스 코드에서 사용자 정의 여부에 관계없이 모든 리터럴은 본질적으로 `101`, `54.7`, `"hello"` 또는 `true`와 같은 영숫자 문자의 시퀀스입니다. 컴파일러는 정수, float, const char 시퀀스 해석\* 문자열 및 등입니다. 컴파일러가 리터럴 값으로 할당 한 모든 형식을 입력으로 허용 하는 사용자 정의 리터럴을 비공식적으로 라고 하며를 *가공 된 리터럴*합니다. `_r` 및 `_t`를 제외한 위의 모든 연산자는 가공된 리터럴입니다. 예를 들어 리터럴 `42.0_km`는 _b와 유사한 서명을 가진 _km이라는 연산자에 바인딩하고 리터럴 `42_km`은 _a와 유사한 서명을 가진 연산자에 바인딩합니다.

다음 예제에서는 사용자 정의 리터럴을 통해 호출자에게 명시적으로 입력을 지정하도록 장려하는 방법을 보여 줍니다. `Distance`를 생성하려면 사용자가 적절한 사용자 정의 리터럴을 사용하여 킬로미터 또는 마일을 명시적으로 지정해야 합니다. 물론 다른 방법으로 동일한 결과를 얻을 수도 있지만 사용자 정의 리터럴이 대체 방법보다 더 간단합니다.

```cpp
struct Distance
{
private:
    explicit Distance(long double val) : kilometers(val)
    {}

    friend Distance operator"" _km(long double  val);
    friend Distance operator"" _mi(long double val);
    long double kilometers{ 0 };
public:
    long double get_kilometers() { return kilometers; }
    Distance operator+(Distance& other)
    {
        return Distance(get_kilometers() + other.get_kilometers());
    }
};

Distance operator"" _km(long double  val)
{
    return Distance(val);
}

Distance operator"" _mi(long double val)
{
    return Distance(val * 1.6);
}
int main(int argc, char* argv[])
{
    // Must have a decimal point to bind to the operator we defined!
    Distance d{ 402.0_km }; // construct using kilometers
    cout << "Kilometers in d: " << d.get_kilometers() << endl; // 402

    Distance d2{ 402.0_mi }; // construct using miles
    cout << "Kilometers in d2: " << d2.get_kilometers() << endl;  //643.2

    // add distances constructed with different units
    Distance d3 = 36.0_mi + 42.0_km;
    cout << "d3 value = " << d3.get_kilometers() << endl; // 99.6

    // Distance d4(90.0); // error constructor not accessible

    string s;
    getline(cin, s);
    return 0;
}
```

리터럴 숫자는 10진수를 사용해야 합니다. 그렇지 않으면 숫자가 정수로 해석되며 형식이 연산자와 호환되지 않습니다. 부동 소수점 입력, 형식은 이어야 합니다. 참고 **long double**, 한 정수 계열 형식 이어야 합니다 **long long**합니다.

## <a name="raw-literals"></a>원시 리터럴

원시 사용자 정의 리터럴에서 정의한 연산자는 리터럴을 char 값의 시퀀스로 받아들이며 해당 시퀀스를 숫자, 문자열 또는 기타 형식으로 해석하는 것은 사용자가 결정합니다. 이 페이지의 앞부분에 나온 연산자 목록에서 `_r` 및 `_t`는 원시 리터럴을 정의하는 데 사용할 수 있습니다.

```cpp
ReturnType operator "" _r(const char*);              // Raw literal operator
template<char...> ReturnType operator "" _t();       // Literal operator template
```

원시 리터럴을 사용하여 컴파일러가 수행하는 것과 다른 입력 시퀀스의 사용자 지정 해석을 제공할 수 있습니다. 예를 들어 `4.75987` 시퀀스를 IEEE 754 부동 소수점 형식 대신 사용자 지정 10진수 형식으로 변환하는 리터럴을 정의할 수 있습니다. 가공된 리터럴과 마찬가지로, 원시 리터럴을 사용하여 입력 시퀀스의 컴파일 타임 유효성 검사를 수행할 수도 있습니다.

### <a name="example-limitations-of-raw-literals"></a>예제: 원시 리터럴의 제한

원시 리터럴 연산자 및 리터럴 연산자 템플릿은 다음 예제와 같이 정수 계열 및 부동 소수점 사용자 정의 리터럴에 대해서만 작동합니다.

```cpp
#include <cstddef>
#include <cstdio>

// Literal operator for user-defined INTEGRAL literal
void operator "" _dump(unsigned long long int lit)
{
    printf("operator \"\" _dump(unsigned long long int) : ===>%llu<===\n", lit);
};

// Literal operator for user-defined FLOATING literal
void operator "" _dump(long double lit)
{
    printf("operator \"\" _dump(long double)            : ===>%Lf<===\n",  lit);
};

// Literal operator for user-defined CHARACTER literal
void operator "" _dump(char lit)
{
    printf("operator \"\" _dump(char)                   : ===>%c<===\n",   lit);
};

void operator "" _dump(wchar_t lit)
{
    printf("operator \"\" _dump(wchar_t)                : ===>%d<===\n",   lit);
};

void operator "" _dump(char16_t lit)
{
    printf("operator \"\" _dump(char16_t)               : ===>%d<===\n",   lit);
};

void operator "" _dump(char32_t lit)
{
    printf("operator \"\" _dump(char32_t)               : ===>%d<===\n",   lit);
};

// Literal operator for user-defined STRING literal
void operator "" _dump(const     char* lit, size_t)
{
    printf("operator \"\" _dump(const     char*, size_t): ===>%s<===\n",   lit);
};

void operator "" _dump(const  wchar_t* lit, size_t)
{
    printf("operator \"\" _dump(const  wchar_t*, size_t): ===>%ls<===\n",  lit);
};

void operator "" _dump(const char16_t* lit, size_t)
{
    printf("operator \"\" _dump(const char16_t*, size_t):\n"                  );
};

void operator "" _dump(const char32_t* lit, size_t)
{
    printf("operator \"\" _dump(const char32_t*, size_t):\n"                  );
};

// Raw literal operator
void operator "" _dump_raw(const char* lit)
{
    printf("operator \"\" _dump_raw(const char*)        : ===>%s<===\n",   lit);
};

template<char...> void operator "" _dump_template();       // Literal operator template

int main(int argc, const char* argv[])
{
    42_dump;
    3.1415926_dump;
    3.14e+25_dump;
     'A'_dump;
    L'B'_dump;
    u'C'_dump;
    U'D'_dump;
      "Hello World"_dump;
     L"Wide String"_dump;
    u8"UTF-8 String"_dump;
     u"UTF-16 String"_dump;
     U"UTF-32 String"_dump;
    42_dump_raw;
    3.1415926_dump_raw;
    3.14e+25_dump_raw;

    // There is no raw literal operator or literal operator template support on these types:
    //  'A'_dump_raw;
    // L'B'_dump_raw;
    // u'C'_dump_raw;
    // U'D'_dump_raw;
    //   "Hello World"_dump_raw;
    //  L"Wide String"_dump_raw;
    // u8"UTF-8 String"_dump_raw;
    //  u"UTF-16 String"_dump_raw;
    //  U"UTF-32 String"_dump_raw;
}
```

```Output
operator "" _dump(unsigned long long int) : ===>42<===
operator "" _dump(long double)            : ===>3.141593<===
operator "" _dump(long double)            : ===>31399999999999998506827776.000000<===
operator "" _dump(char)                   : ===>A<===
operator "" _dump(wchar_t)                : ===>66<===
operator "" _dump(char16_t)               : ===>67<===
operator "" _dump(char32_t)               : ===>68<===
operator "" _dump(const     char*, size_t): ===>Hello World<===
operator "" _dump(const  wchar_t*, size_t): ===>Wide String<===
operator "" _dump(const     char*, size_t): ===>UTF-8 String<===
operator "" _dump(const char16_t*, size_t):
operator "" _dump(const char32_t*, size_t):
operator "" _dump_raw(const char*)        : ===>42<===
operator "" _dump_raw(const char*)        : ===>3.1415926<===
operator "" _dump_raw(const char*)        : ===>3.14e+25<===
```