---
title: path 클래스
ms.date: 09/27/2018
f1_keywords:
- filesystem/std::experimental::filesystem::path
ms.assetid: 8a1227ca-aeb2-4e0e-84aa-86e34e4f4fe8
ms.openlocfilehash: 10c865aa2bc2431850c69e9dfedbef37414b2cb9
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68455094"
---
# <a name="path-class"></a>path 클래스

**Path** 클래스는 표시의 목적으로 여기 `string_type`에 호출 `myname` 되는 형식의 개체를 저장 합니다. 경로 이름으로 사용 하는 데 적합 합니다. `string_type`는의 `basic_string<value_type>`동의어입니다. 여기서 `value_type` 는 Windows의 **wchar_t** 또는 POSIX의 **char** 에 대 한 동의어입니다.

자세한 내용 및 코드 예제를 보려면 [파일 시스템 탐색(C++)](../standard-library/file-system-navigation.md)을 참조하세요.

## <a name="syntax"></a>구문

```cpp
class path;
```

### <a name="constructors"></a>생성자

|생성자|Description|
|-|-|
|[path](#path)|`path`를 생성합니다.|

### <a name="typedefs"></a>형식 정의

|형식 이름|Description|
|-|-|
|[const_iterator](#const_iterator)|`iterator`의 동의어입니다.|
|[iterator](#iterator)|`path` 의`myname`구성 요소를 지정 하는 양방향 상수 반복기입니다.|
|[string_type](#string_type)|이 형식은 `basic_string<value_type>`의 동의어입니다.|

### <a name="member-functions"></a>멤버 함수

|멤버 함수|설명|
|-|-|
|[append](#append)|필요에 따라 preferred_separator를 `mypath`변환 하 고 삽입 하 여 지정 된 시퀀스를 추가 합니다.|
|[assign](#assign)|필요 `mypath` 에 따라 변환 된 지정 된 시퀀스로 대체 합니다.|
|[begin](#begin)|경로 이름 `path::iterator` 에서 첫 번째 경로 요소를 지정 하는를 반환 합니다 (있는 경우).|
|[c_str](#c_str)|의 `mypath`첫 번째 문자에 대 한 포인터를 반환 합니다.|
|[clear](#clear)|를 `mypath.clear()`실행 합니다.|
|[compare](#compare)|비교 값을 반환 합니다.|
|[concat](#compare)|필요에 따라 변환 되었지만 `mypath`구분 기호를 삽입 하지 않는 지정 된 시퀀스를에 추가 합니다.|
|[empty](#empty)|`mypath.empty()`를 반환합니다.|
|[end](#end)|형식의 `iterator`시퀀스의 끝 반복기를 반환 합니다.|
|[extension](#extension)|의 `filename()`접미사를 반환 합니다.|
|[filename](#filename)|myname의 루트 디렉터리 구성 요소, 특히 `empty() path() : *--end()`을 참조하세요. 구성 요소는 비어 있을 수 있습니다.|
|[generic_string](#generic_string)|슬래시로 변환된 백슬래시와 함께 `this->string<Elem, Traits, Alloc>(al)` 를 반환합니다(Windows).|
|[generic_u16string](#generic_u16string)|슬래시로 변환된 백슬래시와 함께 `u16string()` 를 반환합니다(Windows).|
|[generic_u32string](#generic_u32string)|슬래시로 변환된 백슬래시와 함께 `u32string()` 를 반환합니다(Windows).|
|[generic_u8string](#generic_u8string)|슬래시로 변환된 백슬래시와 함께 `u8string()` 를 반환합니다(Windows).|
|[generic_wstring](#generic_wstring)|슬래시로 변환된 백슬래시와 함께 `wstring()` 를 반환합니다(Windows).|
|[has_extension](#has_extension)|`!extension().empty()`를 반환합니다.|
|[has_filename](#has_filename)|`!filename().empty()`를 반환합니다.|
|[has_parent_path](#has_parent_path)|`!parent_path().empty()`를 반환합니다.|
|[has_relative_path](#has_relative_path)|`!relative_path().empty()`를 반환합니다.|
|[has_root_directory](#has_root_directory)|`!root_directory().empty()`를 반환합니다.|
|[has_root_name](#has_root_name)|`!root_name().empty()`를 반환합니다.|
|[has_root_path](#has_root_path)|`!root_path().empty()`를 반환합니다.|
|[has_stem](#has_stem)|`!stem().empty()`를 반환합니다.|
|[is_absolute](#is_absolute)|Windows의 경우 함수는를 `has_root_name() && has_root_directory()`반환 합니다. Posix의 경우 함수는를 `has_root_directory()`반환 합니다.|
|[is_relative](#is_relative)|`!is_absolute()`를 반환합니다.|
|[make_preferred](#make_preferred)|필요에 따라 각 구분 기호를 preferred_separator 변환 합니다.|
|[native](#native)|`myname`를 반환합니다.|
|[parent_path](#parent_path)|의 `myname`부모 경로 구성 요소를 반환 합니다.|
|[preferred_separator](#preferred_separator)|상수 개체는 호스트 운영 체제에 따라 경로 구성 요소를 구분하는 기본 문자를 제공합니다. |
|[relative_path](#relative_path)|의 `myname`상대 경로 구성 요소를 반환 합니다. |
|[remove_filename](#remove_filename)|파일 이름을 제거 합니다.|
|[replace_extension](#replace_extension)|의 `myname`확장을 바꿉니다. |
|[replace_filename](#replace_filename)|파일 이름을 바꿉니다.|
|[root_directory](#root_directory)|의 `myname`루트 디렉터리 구성 요소를 반환 합니다. |
|[root_name](#root_name)|의 `myname`루트 이름 구성 요소를 반환 합니다. |
|[root_path](#root_path)|의 `myname`루트 경로 구성 요소를 반환 합니다.|
|[stem](#stem)|`stem` 의`myname`구성 요소를 반환 합니다.|
|[string](#string)|에 `mypath`저장 된 시퀀스를 변환 합니다.|
|[swap](#swap)|를 `swap(mypath, right.mypath)`실행 합니다.|
|[u16string](#u16string)|에 `mypath` 저장 된 시퀀스를 u t f-16으로 변환 하 여 형식의 `u16string`개체에 저장 된 대로 반환 합니다.|
|[u32string](#u32string)|에 `mypath` 저장 된 시퀀스를 u t f-32로 변환 하 여 형식의 `u32string`개체에 저장 된 대로 반환 합니다.|
|[u8string](#u8string)|에 `mypath` 저장 된 시퀀스를 u t f-8로 변환 하 여 형식의 `u8string`개체에 저장 된 대로 반환 합니다.|
|[value_type](#value_type)|형식은 호스트 운영 체제에서 선호하는 경로 요소를 설명합니다.|
|[wstring](#wstring)|에 `mypath` 저장 된 시퀀스를 `wchar_t` 시퀀스에 대해 호스트 시스템에서 선호 하는 인코딩으로 변환 하 고 형식의 `wstring`개체에 저장 된 대로 반환 합니다.|

### <a name="operators"></a>연산자

|연산자|설명|
|-|-|
|[operator=](#op_as)|경로의 요소를 다른 경로의 복사본으로 바꿉니다.|
|[operator+=](#op_add)|다양 `concat` 한 식입니다.|
|[operator/=](#op_divide)|다양 `append` 한 식입니다.|
|[operator string_type](#op_string)|`myname`를 반환합니다.|

## <a name="requirements"></a>요구 사항

**헤더:** \<파일 시스템 >

**네임스페이스:** std::experimental::filesystem

## <a name="append"></a>경로:: append

필요한 경우 지정 된 시퀀스 `mypath`를에 추가 하 고 `preferred_separator` , 변환 하 고, 삽입 합니다.

```cpp
template <class Source>
path& append(const Source& source);

template <class InIt>
path& append(InIt first, InIt last);
```

### <a name="parameters"></a>매개 변수

*원본*\
지정 된 시퀀스입니다.

*기본*\
지정 된 시퀀스의 시작입니다.

*최신*\
지정 된 시퀀스의 끝입니다.

## <a name="assign"></a>path:: assign

필요 `mypath` 에 따라 변환 된 지정 된 시퀀스로 대체 합니다.

```cpp
template <class Source>
path& assign(const Source& source);

template <class InIt>
path& assign(InIt first, InIt last);
```

### <a name="parameters"></a>매개 변수

*원본*\
지정 된 시퀀스입니다.

*기본*\
지정 된 시퀀스의 시작입니다.

*최신*\
지정 된 시퀀스의 끝입니다.

## <a name="begin"></a>path:: begin

경로 이름 `path::iterator` 에서 첫 번째 경로 요소를 지정 하는를 반환 합니다 (있는 경우).

```cpp
iterator begin() const;
```

## <a name="c_str"></a> path::c_str

의 `mypath`첫 번째 문자에 대 한 포인터를 반환 합니다.

```cpp
const value_type& *c_str() const noexcept;
```

## <a name="clear"></a>경로:: clear

를 `mypath.clear()`실행 합니다.

```cpp
void clear() noexcept;
```

## <a name="compare"></a> path::compare

첫 번째 함수는 `mypath.compare(pval.native())`를 반환합니다. 두 번째 함수는 `mypath.compare(str)`를 반환합니다. 세 번째 함수는 `mypath.compare(ptr)`를 반환 합니다.

```cpp
int compare(const path& pval) const noexcept;
int compare(const string_type& str) const;
int compare(const value_type *ptr) const;
```

### <a name="parameters"></a>매개 변수

*pval*\
비교할 경로입니다.

*문자열*\
비교할 문자열입니다.

*ptr*\
비교할 포인터입니다.

## <a name="concat"></a> path::concat

필요에 따라 변환 되었지만 `mypath`구분 기호를 삽입 하지 않는 지정 된 시퀀스를에 추가 합니다.

```cpp
template <class Source>
path& concat(const Source& source);

template <class InIt>
path& concat(InIt first, InIt last);
```

### <a name="parameters"></a>매개 변수

*원본*\
지정 된 시퀀스입니다.

*기본*\
지정 된 시퀀스의 시작입니다.

*최신*\
지정 된 시퀀스의 끝입니다.

## <a name="const_iterator"></a> path::const_iterator

`iterator`의 동의어입니다.

```cpp
typedef iterator const_iterator;
```

## <a name="empty"></a> path::empty

`mypath.empty()`를 반환합니다.

```cpp
bool empty() const noexcept;
```

## <a name="end"></a>경로:: end

형식의 `iterator`시퀀스의 끝 반복기를 반환 합니다.

```cpp
iterator end() const;
```

## <a name="extension"></a> path::extension

의 `filename()`접미사를 반환 합니다.

```cpp
path extension() const;
```

### <a name="remarks"></a>설명

는 다음과 같은의 `filename() X` 접미사를 반환 합니다.

`X == path(".") || X == path("..")` 또는에점이없는`X` 경우 접미사가 비어 있습니다.

그렇지 않은 경우 접미사가 맨 오른쪽 점으로 시작되고 해당 점을 포함합니다.

## <a name="filename"></a> path::filename

myname의 루트 디렉터리 구성 요소, 특히 `empty() path() : *--end()`을 참조하세요. 구성 요소는 비어 있을 수 있습니다.

```cpp
path filename() const;
```

## <a name="generic_string"></a> path::generic_string

슬래시로 변환된 백슬래시와 함께 `this->string<Elem, Traits, Alloc>(al)` 를 반환합니다(Windows).

```cpp
template <class Elem,
    class Traits = char_traits<Elem>,
    class Alloc = allocator<Elem>>
  basic_string<Elem, Traits, Alloc>
    generic_string(const Alloc& al = Alloc()) const;

string generic_string() const;
```

## <a name="generic_u16string"></a> path::generic_u16string

슬래시로 변환된 백슬래시와 함께 `u16string()` 를 반환합니다(Windows).

```cpp
u16string generic_u16string() const;
```

## <a name="generic_u32string"></a> path::generic_u32string

슬래시로 변환된 백슬래시와 함께 `u32string()` 를 반환합니다(Windows).

```cpp
u32string generic_u32string() const;
```

## <a name="generic_u8string"></a> path::generic_u8string

슬래시로 변환된 백슬래시와 함께 `u8string()` 를 반환합니다(Windows).

```cpp
string generic_u8string() const;
```

## <a name="generic_wstring"></a> path::generic_wstring

슬래시로 변환된 백슬래시와 함께 `wstring()` 를 반환합니다(Windows).

```cpp
wstring generic_wstring() const;
```

## <a name="has_extension"></a>경로:: has_extension

`!extension().empty()`를 반환합니다.

```cpp
bool has_extension() const;
```

## <a name="has_filename"></a>경로:: has_filename

`!filename().empty()`를 반환합니다.

```cpp
bool has_filename() const;
```

## <a name="has_parent_path"></a>경로:: has_parent_path

`!parent_path().empty()`를 반환합니다.

```cpp
bool has_parent_path() const;
```

## <a name="has_relative_path"></a> path::has_relative_path

`!relative_path().empty()`를 반환합니다.

```cpp
bool has_relative_path() const;
```

## <a name="has_root_directory"></a> path::has_root_directory

`!root_directory().empty()`를 반환합니다.

```cpp
bool has_root_directory() const;
```

## <a name="has_root_name"></a> path::has_root_name

`!root_name().empty()`를 반환합니다.

```cpp
bool has_root_name() const;
```

## <a name="has_root_path"></a> path::has_root_path

`!root_path().empty()`를 반환합니다.

```cpp
bool has_root_path() const;
```

## <a name="has_stem"></a> path::has_stem

`!stem().empty()`를 반환합니다.

```cpp
bool has_stem() const;
```

## <a name="is_absolute"></a> path::is_absolute

Windows의 경우 함수는를 `has_root_name() && has_root_directory()`반환 합니다. Posix의 경우 함수는를 `has_root_directory()`반환 합니다.

```cpp
bool is_absolute() const;
```

## <a name="is_relative"></a> path::is_relative

`!is_absolute()`를 반환합니다.

```cpp
bool is_relative() const;
```

## <a name="iterator"></a>path:: iterator

의 `myname`경로 구성 요소를 지정 하는 양방향 상수 반복기입니다.

```cpp
class iterator
   {
   // bidirectional iterator for path
   typedef bidirectional_iterator_tag iterator_category;
   typedef path_type value_type;
   typedef ptrdiff_t difference_type;
   typedef const value_type *pointer;
   typedef const value_type& reference;
   // ...
   };
```

### <a name="remarks"></a>설명

이 클래스는 시퀀스에서의 `path` `myname` 구성 요소를 지정 하는 양방향 상수 반복기를 설명 합니다.

1. 루트 이름(있는 경우)

1. 루트 디렉터리(있는 경우)

1. 파일 이름 (있는 경우)으로 `path`끝나는 부모의 나머지 디렉터리 요소 (있는 경우)

`pval` 다음 유형의`path`개체:

1. `path::iterator X = pval.begin()`경로 이름에서 `path` 첫 번째 요소를 지정 합니다 (있는 경우).

1. `X == pval.end()`가 구성 요소 `X` 시퀀스의 끝을 지나서 있는 경우는 true입니다.

3. `*X`현재 구성 요소와 일치 하는 문자열을 반환 합니다.

1. `++X`는 시퀀스에서 다음 구성 요소(있는 경우)를 지정합니다.

1. `--X`는 시퀀스에서 이전 구성 요소(있는 경우)를 지정합니다.

1. 변경 `myname` 하면에서 요소를 `myname`지정 하는 모든 반복기가 무효화 됩니다.

## <a name="make_preferred"></a> path::make_preferred

필요에 `preferred_separator` 따라 각 구분 기호를로 변환 합니다.

```cpp
path& make_preferred();
```

## <a name="native"></a>path:: native

`myname`를 반환합니다.

```cpp
const string_type& native() const noexcept;
```

## <a name="op_as"></a> path::operator=

경로의 요소를 다른 경로의 복사본으로 바꿉니다.

```cpp
path& operator=(const path& right);
path& operator=(path&& right) noexcept;

template <class Source>
path& operator=(const Source& source);
```

### <a name="parameters"></a>매개 변수

*오른쪽*\
`path`에 복사할 [경로](../standard-library/path-class.md)입니다.

*원본*\
원본 경로입니다.

### <a name="remarks"></a>설명

첫 번째 멤버 연산자는 `right.myname` 를 `myname`로 복사 합니다. 두 번째 멤버 연산자는 `right.myname` 로 `myname`이동 합니다. 세 번째 멤버 연산자는와 동일 하 `*this = path(source)`게 동작 합니다.

## <a name="op_add"></a>path:: operator + =

다양 `concat` 한 식입니다.

```cpp
path& operator+=(const path& right);
path& operator+=(const string_type& str);
path& operator+=(const value_type *ptr);
path& operator+=(value_type elem);

template <class Source>
path& operator+=(const Source& source);

template <class Elem>
path& operator+=(Elem elem);
```

### <a name="parameters"></a>매개 변수

*오른쪽*\
추가 된 경로입니다.

*문자열*\
추가 된 문자열입니다.

*ptr*\
추가 된 포인터입니다.

*e*\
추가 `value_type` 된 또는 `Elem`입니다.

*원본*\
추가 된 원본입니다.

### <a name="remarks"></a>설명

멤버 함수는 다음 해당 식과 동일하게 작동합니다.

1. `concat(right);`

1. `concat(path(str));`

1. `concat(ptr);`

1. `concat(string_type(1, elem));`

1. `concat(source);`

1. `concat(path(basic_string<Elem>(1, elem)));`

## <a name="op_divide"></a> path::operator/=

다양 `append` 한 식입니다.

```cpp
path& operator/=(const path& right);

template <class Source>
path& operator/=(const Source& source);
```

### <a name="parameters"></a>매개 변수

*오른쪽*\
추가 된 경로입니다.

*원본*\
추가 된 원본입니다.

### <a name="remarks"></a>설명

멤버 함수는 다음 해당 식과 동일하게 작동합니다.

1. `append(right);`

1. `append(source);`

## <a name="op_string"></a> path::operator string_type

`myname`를 반환합니다.

```cpp
operator string_type() const;
```

## <a name="parent_path"></a> path::parent_path

의 `myname`부모 경로 구성 요소를 반환 합니다.

```cpp
path parent_path() const;
```

### <a name="remarks"></a>설명

는의 `myname`부모 경로 구성 요소, 특히를 제거한 `filename().native()` 후 `myname` 의 접두사와 바로 앞의 디렉터리 구분 기호를 반환 합니다. 동일 하 게 적용 `begin() != end()`하는 경우 범위 `[begin(), --end())` 에 있는 모든 요소를 연속적으로 적용 `operator/=`하 여 결합 합니다. 구성 요소는 비어 있을 수 있습니다.

## <a name="path"></a>경로::p a

여러 가지 `path` 방법으로을 생성 합니다.

```cpp
path();

path(const path& right);
path(path&& right) noexcept;

template <class Source>
path(const Source& source);

template <class Source>
path(const Source& source, const locale& loc);

template <class InIt>
path(InIt first, InIt last);

template <class InIt>
path(InIt first, InIt last, const locale& loc);
```

### <a name="parameters"></a>매개 변수

*오른쪽*\
생성 된 경로가 복사본으로 지정할 경로입니다.

*원본*\
생성 된 경로를 복사할 원본입니다.

*loc*\
지정 된 로캘입니다.

*기본*\
복사할 첫 번째 요소의 위치입니다.

*최신*\
복사할 마지막 요소의 위치입니다.

### <a name="remarks"></a>설명

생성자는 다음과 같은 `myname` 다양 한 방법으로 구성 됩니다.

`path()` 는`myname()`입니다.

의 `path(const path& right`경우) `myname(right.myname)`입니다.

`path(path&& right)` 는`myname(right.myname)`입니다.

`template<class Source> path(const Source& source)` 는`myname(source)`입니다.

그 이유는 `myname(source)` 에서`loc`필요한 codecvt 패싯을 가져오는 것입니다. `template<class Source> path(const Source& source, const locale& loc)`

`template<class InIt> path(InIt first, InIt last)` 는`myname(first, last)`입니다.

그 이유는 `myname(first, last)` 에서`loc`필요한 codecvt 패싯을 가져오는 것입니다. `template<class InIt> path(InIt first, InIt last, const locale& loc)`

## <a name="preferred_separator"></a> path::preferred_separator

상수 개체는 호스트 운영 체제에 따라 경로 구성 요소를 구분하는 기본 문자를 제공합니다.

```cpp
#if _WIN32_C_LIB
static constexpr value_type preferred_separator == L'\\';
#else // assume Posix
static constexpr value_type preferred_separator == '/';
#endif // filesystem model now defined
```

### <a name="remarks"></a>설명

대부분의 Windows 컨텍스트에서는 L'/'을 대신 사용하여 동일하게 허용됩니다.

## <a name="relative_path"></a> path::relative_path

의 `myname`상대 경로 구성 요소를 반환 합니다.

```cpp
path relative_path() const;
```

### <a name="remarks"></a>설명

는의 `myname`상대 경로 구성 요소, 특히를 제거한 `root_path().native()` 후 `myname` 의 접미사 및 즉시 중복 디렉터리 구분 기호를 반환 합니다. 구성 요소는 비어 있을 수 있습니다.

## <a name="remove_filename"></a> path::remove_filename

파일 이름을 제거 합니다.

```cpp
path& remove_filename();
```

## <a name="replace_extension"></a> path::replace_extension

의 `myname`확장을 바꿉니다.

```cpp
path& replace_extension(const path& newext = path());
```

### <a name="parameters"></a>매개 변수

*newext*\
새 확장명입니다.

### <a name="remarks"></a>설명

는 먼저에서 `myname`접미사 `extension().native()` 를 제거 합니다. 그런 다음 `!newext.empty() && newext[0] != dot` `dot` `myname`(가 인 `*path(".").c_str()`경우)가에 추가 됩니다. `dot` 그런 다음 *newext* 가에 `myname`추가 됩니다.

## <a name="replace_filename"></a> path::replace_filename

파일 이름을 바꿉니다.

```cpp
path& replace_filename(const path& pval);
```

### <a name="parameters"></a>매개 변수

*pval*\
파일 이름의 경로입니다.

### <a name="remarks"></a>설명

멤버 함수에서 다음을 실행합니다.

```cpp
remove_filename();

*this /= pval;
return (*this);
```

## <a name="root_directory"></a> path::root_directory

의 `myname`루트 디렉터리 구성 요소를 반환 합니다.

```cpp
path root_directory() const;
```

### <a name="remarks"></a>설명

구성 요소는 비어 있을 수 있습니다.

## <a name="root_name"></a> path::root_name

의 `myname`루트 이름 구성 요소를 반환 합니다.

```cpp
path root_name() const;
```

### <a name="remarks"></a>설명

구성 요소는 비어 있을 수 있습니다.

## <a name="root_path"></a> path::root_path

의 `myname`루트 경로 구성 요소를 반환 합니다.

```cpp
path root_path() const;
```

### <a name="remarks"></a>설명

특히 `myname` 의루트`root_name()`경로 구성 요소를 반환 합니다.  /  `root_directory` 구성 요소는 비어 있을 수 있습니다.

## <a name="stem"></a>path:: 스템

`stem` 의`myname`구성 요소를 반환 합니다.

```cpp
path stem() const;
```

### <a name="remarks"></a>설명

는의 `stem` `myname`구성 요소를 반환 `filename().native()` 합니다 .이 `extension().native()` 구성 요소는 임의의 후행 제거를 포함 합니다. 구성 요소는 비어 있을 수 있습니다.

## <a name="string"></a>path:: string

에 `mypath`저장 된 시퀀스를 변환 합니다.

```cpp
template \<class Elem, class Traits = char_traits\<Elem>, class Alloc = allocator\<Elem>>
basic_string\<Elem, Traits, Alloc> string(const Alloc& al = Alloc()) const;
string string() const;
```

### <a name="remarks"></a>설명

첫 번째 (템플릿) 멤버 함수는 다음과 같은 방식으로 `mypath` 저장 된 시퀀스를 변환 합니다.

1. `string()` 에 대한 `string<char, Traits, Alloc>()`

1. `wstring()` 에 대한 `string<wchar_t, Traits, Alloc>()`

1. `u16string()` 에 대한 `string<char16_t, Traits, Alloc>()`

1. `u32string()` 에 대한 `string<char32_t, Traits, Alloc>()`

두 번째 멤버 함수는에 `mypath` 저장 된 시퀀스를 **문자** 시퀀스에 대해 호스트 시스템에서 선호 하는 인코딩으로 변환 하 고 형식의 `string`개체에 저장 된 대로 반환 합니다.

## <a name="string_type"></a> path::string_type

이 형식은 `basic_string<value_type>`의 동의어입니다.

```cpp
typedef basic_string<value_type> string_type;
```

## <a name="swap"></a> path::swap

를 `swap(mypath, right.mypath)`실행 합니다.

```cpp
void swap(path& right) noexcept;
```

## <a name="u16string"></a>경로:: u16string

에 `mypath` 저장 된 시퀀스를 u t f-16으로 변환 하 여 형식의 `u16string`개체에 저장 된 대로 반환 합니다.

```cpp
u16string u16string() const;
```

## <a name="u32string"></a>경로:: u32string

에 `mypath` 저장 된 시퀀스를 u t f-32로 변환 하 여 형식의 `u32string`개체에 저장 된 대로 반환 합니다.

```cpp
u32string u32string() const;
```

## <a name="u8string"></a>경로:: u8string

에 `mypath` 저장 된 시퀀스를 u t f-8로 변환 하 여 형식의 `u8string`개체에 저장 된 대로 반환 합니다.

```cpp
string u8string() const;
```

## <a name="value_type"></a> path::value_type

형식은 호스트 운영 체제 `path` 에서 선호 하는 요소를 설명 합니다.

```cpp
#if _WIN32_C_LIB
typedef wchar_t value_type;
#else // assume Posix
typedef char value_type;
#endif // filesystem model now defined
```

## <a name="wstring"></a> path::wstring

에 `mypath` 저장 된 시퀀스를 **wchar_t** 시퀀스에 대해 호스트 시스템에서 선호 하는 인코딩으로 변환 하 고 형식의 `wstring`개체에 저장 된 대로 반환 합니다.

```cpp
wstring wstring() const;
```

## <a name="see-also"></a>참고자료

[헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)
