---
title: '&lt;cstdlib&gt;'
ms.date: 11/04/2016
f1_keywords:
- <cstdlib>
helpviewer_keywords:
- cstdlib header
ms.assetid: 0a6aaebf-84e9-4b60-ae90-17e11981cf54
ms.openlocfilehash: 70e05ad734fa49ba8cb96e4bf83bc05b99c5f55c
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68246524"
---
# <a name="ltcstdlibgt"></a>&lt;cstdlib&gt;

표준 C 라이브러리 헤더를 포함 \<b. h >에 연결된 된 이름을 추가 하 고는 `std` 네임 스페이스입니다. 외부 링크를 사용 하 여 C 표준 라이브러리 헤더에 선언 된 이름에 선언 되어 있는지 확인이 헤더를 포함 하는 `std` 네임 스페이스입니다.

> [!NOTE]
> \<b. h > 형식을 포함 하지 않습니다 **wchar_t**합니다.

## <a name="requirements"></a>요구 사항

**헤더**: \<cstdlib >

**네임스페이스:** std

## <a name="namespace-and-macros"></a>Namespace 및 매크로

```cpp
namespace std {
    using size_t = see definition;
    using div_t = see definition;
    using ldiv_t = see definition;
    using lldiv_t = see definition;
}

#define NULL
#define EXIT_FAILURE
#define EXIT_SUCCESS
#define RAND_MAX
#define MB_CUR_MAX
```

## <a name="exposition-only-functions"></a>함수만 표시

```cpp
extern "C" using c-atexit-handler = void();
extern "C++" using atexit-handler = void();
extern "C" using c-compare-pred = int(const void*, const void*);
extern "C++" using compare-pred = int(const void*, const void*);
```

## <a name="start-and-termination-functions"></a>시작 및 종료 함수

|함수|Description|
|-|-|
|[_Exit](#_exit)|소멸자 또는 등록 된 함수를 사용 하지 않고 프로그램을 종료 합니다.|
|[abort](#abort)|소멸자를 사용 하지 않고 프로그램을 종료 합니다.|
|[atexit](#atexit)|프로그램 종료에 대 한 함수를 등록 합니다.|
|[exit](#exit)|스레드 및 정적 저장소를 다음 반환 컨트롤을 사용 하 여 개체를 제거합니다.|
|[at_quick_exit](#at_quick_exit)|프로그램 종료에 대 한 인수 없이 함수를 등록 합니다.|
|[quick_exit](#quick_exit)|프로그램 종료에 대 한 유지 개체를 사용 하 여 함수를 등록 합니다.|
|[getenv](#getenv)|C 표준 라이브러리 참조를 참조 하세요.|
|[system](#system)|C 표준 라이브러리 참조를 참조 하세요.|

### <a name="_exit"></a> _Exit

```cpp
[[noreturn]] void _Exit(int status) noexcept;
```

#### <a name="remarks"></a>설명

프로그램이 종료 되 고 전달 하는 함수를 호출 하지 않고 자동 개체, 스레드 또는 정적 저장 기간에 대 한 소멸자를 실행 하지 않고 `atexit()`합니다. 함수 `_Exit` 는 신호 스레드로부터 안전 합니다.

### <a name="abort"></a> 중단

```cpp
[[noreturn]] void abort() noexcept;
```

#### <a name="remarks"></a>설명

프로그램이 종료 되 고 전달 하는 함수를 호출 하지 않고 자동 개체, 스레드 또는 정적 저장 기간에 대 한 소멸자를 실행 하지 않고 `atexit()`합니다. 함수 `abort` 는 신호 스레드로부터 안전 합니다.

### <a name="at_quick_exit"></a> at_quick_exit

```cpp
int at_quick_exit(c-atexit-handler * func) noexcept;
int at_quick_exit(atexit-handler * func) noexcept;
```

#### <a name="return-value"></a>반환 값

등록이 성공, 실패 한 경우 0이 아닌 경우 0입니다.

#### <a name="remarks"></a>설명

`at_quick_exit()` 함수에서 가리키는 함수를 등록 *func* 인수 없이 호출 될 때 `quick_exit` 라고 합니다. 가 지정 되지 않은 대 한 호출이 `at_quick_exit()` 에 대 한 모든 호출 전에 발생 하지 않습니다 하 `quick_exit` 성공할 및 `at_quick_exit()` 함수는 데이터 경합을 도입 되지 않습니다. 등록의 순서를 확정적이 지 않을 경우 `at_quick_exit` 이후 및 스레드와 보다 좀 더 호출한 `at_quick_exit` 등록와 다릅니다.를 `atexit` 등록 응용 프로그램으로 모두 등록 함수를 호출 해야 할 수는 동일한 인수입니다. 구현이 최소한 32 함수의 등록을 지원 됩니다.

### <a name="atexit"></a> atexit

```cpp
int atexit(c-atexit-handler * func) noexcept;
int atexit(atexit-handler * func) noexcept;
```

#### <a name="remarks"></a>설명

`atexit()` 함수에서 가리키는 함수를 등록 *func* 프로그램이 정상 종료 시 인수 없이 호출할 수 있습니다. 가 지정 되지 않은 대 한 호출이 `atexit()` 를 호출 하기 전에 발생 하지 않습니다 하 `exit()` 성공할 및 `atexit()` 함수는 데이터 경합을 도입 되지 않습니다. 구현이 최소한 32 함수의 등록을 지원 됩니다.

#### <a name="return-value"></a>반환 값

등록이 성공, 실패 한 경우 0이 아닌 경우 0을 반환 합니다.

### <a name="exit"></a> 종료

```cpp
[[noreturn]] void exit(int status);
```

#### <a name="remarks"></a>설명

먼저 스레드 저장 기간이 있는 개체 및 연결 된 현재 스레드 소멸 됩니다.

다음으로, 정적 저장 기간이 있는 개체가 제거 되 고 호출 하 여 등록 된 함수 `atexit` 라고 합니다. 호출의 결과로 자동 개체 소멸 되지 `exit()`합니다. 컨트롤 등록 된 함수에 의해 호출을 퇴사 하는 경우 `exit` 함수는 throw 된 예외에 대 한 처리기를 제공 하지 때문에 `std::terminate()` 호출 됩니다. 함수가 등록 될 때마다 호출 됩니다. 자동 저장 기간이 있는 모든 객체는 프로그램 인 main 함수에 자동 개체가 없습니다 및 실행에 대 한 호출에서에서 `exit()`합니다. Main에서 발견 되는 예외를 throw 하 여 이러한 기본 함수를 직접 제어를 전송할 수 있습니다.

다음으로 열려 있는 모든 C 스트림을 (에 선언 된 함수 시그니처를 통해 조정 하는 대로 <cstdio>)를 호출 하 여 생성 버퍼링 된 데이터가 기록 되지 않은 모든 파일과 플러시, 열려 있는 모든 C 스트림이 닫혀 `tmpfile()` 제거 됩니다.

마지막으로, 컨트롤은 호스트 환경에 반환 됩니다. 상태가 아니거나 EXIT_SUCCESS 또는 0 인 구현 시 정의 된 형식의 상태 성공적으로 종료는 반환 됩니다. 상태가 EXIT_FAILURE 인 경우 구현 시 정의 된 형식의 상태 실패 한 종료는 반환 됩니다. 그렇지 않으면 반환 상태 구현 시 정의 됩니다.

### <a name="getenv"></a> getenv

```cpp
char* getenv(const char* name);
```

### <a name="quick_exit"></a> quick_exit

```cpp
[[noreturn]] void quick_exit(int status) noexcept;
```

#### <a name="remarks"></a>설명

함수를 호출 하 여 등록 `at_quick_exit` 제외 하 고 이전에 등록 된 모든 함수는 마치 이미 등록 된 시점에 호출 된 후에 함수를 호출할 수는 해당 등록의 역순으로 호출 됩니다. 호출 결과 개체는 소멸 되지 `quick_exit`합니다. 컨트롤 등록 된 함수에 의해 호출을 퇴사 하는 경우 `quick_exit` 함수는 throw 된 예외에 대 한 처리기를 제공 하지 때문에 `std::terminate()` 호출 됩니다. 함수를 통해 등록할 `at_quick_exit` 를 호출 하는 스레드를 호출한 `quick_exit`, 스레드 저장 기간이 있는 개체의 id에 의존해 서는 안 되는 다른 스레드를 등록 하는 것 이므로 함수를 등록 하는 보다 합니다. 등록 된 함수를 호출한 후 `quick_exit` 를 호출 해야 `_Exit(status)`합니다. 표준 파일 버퍼 플러시 되지 않습니다. 함수 `quick_exit` 함수를 등록 하는 경우의 신호 안전한 `at_quick_exit` 됩니다.

### <a name="system"></a> 시스템

```cpp
int system(const char* string);
```

## <a name="memory-allocation-functions"></a>메모리 할당 함수

```cpp
void* aligned_alloc(size_t alignment, size_t size);
void* calloc(size_t nmemb, size_t size);
void free(void* ptr);
void* malloc(size_t size);
void* realloc(void* ptr, size_t size);
double atof(const char* nptr);
int atoi(const char* nptr);
long int atol(const char* nptr);
long long int atoll(const char* nptr);
double strtod(const char* nptr, char** endptr);
float strtof(const char* nptr, char** endptr);
long double strtold(const char* nptr, char** endptr);
long int strtol(const char* nptr, char** endptr, int base);
long long int strtoll(const char* nptr, char** endptr, int base);
unsigned long int strtoul(const char* nptr, char** endptr, int base);
unsigned long long int strtoull(const char* nptr, char** endptr, int base);
```

#### <a name="remarks"></a>설명

이러한 함수는 C 표준 라이브러리에 지정 된 의미 체계를 가집니다.

##  <a name="multibyte--wide-string-and-character-conversion-functions"></a>멀티 바이트 / 와이드 문자열 및 문자 변환 함수

```cpp
int mblen(const char* s, size_t n);
int mbtowc(wchar_t* pwc, const char* s, size_t n);
int wctomb(char* s, wchar_t wchar);
size_t mbstowcs(wchar_t* pwcs, const char* s, size_t n);
size_t wcstombs(char* s, const wchar_t* pwcs, size_t n);
```

### <a name="remarks"></a>설명

이러한 함수는 C 표준 라이브러리에 지정 된 의미 체계를 가집니다.

## <a name="algorithm-functions"></a>알고리즘 함수

```cpp
void* bsearch(const void* key, const void* base, size_t nmemb, size_t size, c-compare-pred * compar);
void* bsearch(const void* key, const void* base, size_t nmemb, size_t size, compare-pred * compar);
void qsort(void* base, size_t nmemb, size_t size, c-compare-pred * compar);
void qsort(void* base, size_t nmemb, size_t size, compare-pred * compar);
```

### <a name="remarks"></a>설명

이러한 함수는 C 표준 라이브러리에 지정 된 의미 체계를 가집니다.

## <a name="low-quality-random-number-generation-functions"></a>품질이 임의 숫자 생성 함수

```cpp
int rand();
void srand(unsigned int seed);
```

### <a name="remarks"></a>설명

이러한 함수는 C 표준 라이브러리에 지정 된 의미 체계를 가집니다.

## <a name="absolute-values"></a>절대값

```cpp
int abs(int j);
long int abs(long int j);
long long int abs(long long int j);
float abs(float j);
double abs(double j);
long double abs(long double j);
long int labs(long int j);
long long int llabs(long long int j);
div_t div(int numer, int denom);
ldiv_t div(long int numer, long int denom);
lldiv_t div(long long int numer, long long int denom);
ldiv_t ldiv(long int numer, long int denom);
lldiv_t lldiv(long long int numer, long long int denom);
```

### <a name="remarks"></a>설명

이러한 함수는 C 표준 라이브러리에 지정 된 의미 체계를 가집니다.

## <a name="functions"></a>함수

```cpp
void* bsearch(const void* key, const void* base, size_t nmemb, size_t size,
c-compare-pred * compar);
void* bsearch(const void* key, const void* base, size_t nmemb, size_t size,
compare-pred * compar);
void qsort(void* base, size_t nmemb, size_t size, c-compare-pred * compar);
void qsort(void* base, size_t nmemb, size_t size, compare-pred * compar);
```

## <a name="see-also"></a>참고자료

[헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ 표준 라이브러리 개요](../standard-library/cpp-standard-library-overview.md)<br/>
[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
