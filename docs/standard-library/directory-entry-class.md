---
title: directory_entry 클래스
ms.date: 09/10/2018
f1_keywords:
- filesystem/std::experimental::filesystem::directory_entry
- filesystem/std::experimental::filesystem::directory_entry::operator const std::experimental::filesystem::path &
- filesystem/std::experimental::filesystem::directory_entry::directory_entry
- filesystem/std::experimental::filesystem::directory_entry::operator=
- filesystem/std::experimental::filesystem::directory_entry::assign
- filesystem/std::experimental::filesystem::directory_entry::replace_filename
- filesystem/std::experimental::filesystem::directory_entry::path
- filesystem/std::experimental::filesystem::directory_entry::status
- filesystem/std::experimental::filesystem::directory_entry::symlink_status
- filesystem/std::experimental::filesystem::directory_entry::operator&lt;
- filesystem/std::experimental::filesystem::directory_entry::operator==
- filesystem/std::experimental::filesystem::directory_entry::operator!=
- filesystem/std::experimental::filesystem::directory_entry::operator&lt;=
- filesystem/std::experimental::filesystem::directory_entry::operator&gt;
- filesystem/std::experimental::filesystem::directory_entry::operator&gt;=
ms.assetid: 1827c67b-4137-4548-adb0-f955f7acaf08
helpviewer_keywords:
- std::experimental::filesystem::directory_entry
- std::experimental::filesystem::directory_entry::operator const std::experimental::filesystem::path &
- std::experimental::filesystem::directory_entry::directory_entry
- std::experimental::filesystem::directory_entry::operator=
- std::experimental::filesystem::directory_entry::assign
- std::experimental::filesystem::directory_entry::replace_filename
- std::experimental::filesystem::directory_entry::path
- std::experimental::filesystem::directory_entry::status
- std::experimental::filesystem::directory_entry::symlink_status
- std::experimental::filesystem::directory_entry::operator&lt;
- std::experimental::filesystem::directory_entry::operator==
- std::experimental::filesystem::directory_entry::operator!=
- std::experimental::filesystem::directory_entry::operator&lt;=
- std::experimental::filesystem::directory_entry::operator&gt;
- std::experimental::filesystem::directory_entry::operator&gt;=
ms.openlocfilehash: c1b68aefd44d8f0ac60c36307dee93333d801bb9
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64342980"
---
# <a name="directoryentry-class"></a>directory_entry 클래스

`*X`에서 반환하는 개체에 대해 설명합니다. 여기서 *X* 는 [directory_iterator](../standard-library/directory-iterator-class.md) 또는 [recursive_directory_iterator](../standard-library/recursive-directory-iterator-class.md)입니다.

## <a name="syntax"></a>구문

```cpp
class directory_entry;
```

## <a name="remarks"></a>설명

클래스는 [path](../standard-library/path-class.md) 형식의 개체를 저장합니다. 저장된 `path`는 [path 클래스](../standard-library/path-class.md)의 인스턴스이거나 `path`에서 파생된 형식의 인스턴스일 수 있습니다. 또한 두 개의 [file_type](../standard-library/filesystem-enumerations.md#file_type) 값도 저장합니다. 하나는 저장된 파일 이름의 상태에 대해 알려진 정보를 나타내고, 다른 하나는 파일 이름의 기호화된 링크 상태에 대해 알려진 정보를 나타냅니다.

자세한 내용 및 코드 예제를 보려면 [파일 시스템 탐색(C++)](../standard-library/file-system-navigation.md)을 참조하세요.

### <a name="constructors"></a>생성자

|생성자|설명|
|-|-|
|[directory_entry](#directory_entry)|기본 생성자는 예상대로 작동합니다. 네 번째 생성자는 초기화 `mypath` 하 *pval*, `mystat` 에 *stat_arg로*, 및 `mysymstat` 에 *symstat_arg로*합니다.|

### <a name="member-functions"></a>멤버 함수

|멤버 함수|설명|
|-|-|
|[assign](#assign)|멤버 함수는 할당 *pval* 하 `mypath`, *stat* 에 `mystat`, 및 *symstat* 를 `mysymstat`합니다.|
|[path](#path)|멤버 함수는 `mypath`를 반환합니다.|
|[replace_filename](#replace_filename)|멤버 함수 `mypath` 사용 하 여 `mypath.parent_path()`  /  *pval*를 `mystat` 사용 하 여 *stat_arg로*, 및 `mysymstat` 사용 하 여 *symstat_arg로*|
|[status](#status)|두 멤버 함수는 반환 `mystat` 먼저 변경 합니다.|
|[symlink_status](#symlink_status)|두 멤버 함수는 반환 `mysymstat` 먼저 변경 합니다.|

### <a name="operators"></a>연산자

|연산자|설명|
|-|-|
|[operator!=](#op_neq)|목록의 요소를 다른 목록의 복사본으로 바꿉니다.|
|[operator=](#op_as)|기본 멤버 대입 연산자가 예상대로 작동합니다.|
|[연산자==](#op_eq)|`mypath == right.mypath`를 반환합니다.|
|[operator<](#op_lt)|`mypath < right.mypath`를 반환합니다.|
|[operator<=](#op_lteq)|`!(right < *this)`를 반환합니다.|
|[operator>](#op_gt)|`right < *this`를 반환합니다.|
|[operator>=](#op_gteq)|`!(*this < right)`를 반환합니다.|
|[const path_type 연산자 &](#path_type)|`mypath`를 반환합니다.|

## <a name="requirements"></a>요구 사항

**헤더:** \<실험적/파일 시스템&gt;

**네임스페이스:** std::experimental::filesystem

## <a name="assign"></a> assign

멤버 함수는 할당 *pval* 에 `mypath`, *stat_arg로* 에 `mystat`, 및 *symstat_arg* 에 `mysymstat`입니다.

```cpp
void assign(const std::experimental::filesystem::path& pval,
    file_status stat_arg = file_status(),
    file_status symstat_arg = file_status());
```

### <a name="parameters"></a>매개 변수

*pval*<br/>
저장 된 파일 이름 경로입니다.

*stat_arg*<br/>
상태 저장된 된 파일 이름입니다.

*symstat_arg*<br/>
저장 된 파일 이름의 기호화 된 링크 상태입니다.

## <a name="directory_entry"></a> directory_entry

기본 생성자는 예상대로 작동합니다. 네 번째 생성자는 초기화 `mypath` 하 *pval*, `mystat` 에 *stat_arg로*, 및 `mysymstat` 에 *symstat_arg로*합니다.

```cpp
directory_entry() = default;
directory_entry(const directory_entry&) = default;
directory_entry(directory_entry&&) noexcept = default;
explicit directory_entry(const std::experimental::filesystem::path& pval,
    file_status stat_arg = file_status(),
    file_status symstat_arg = file_status());
```

### <a name="parameters"></a>매개 변수

*pval*<br/>
저장 된 파일 이름 경로입니다.

*stat_arg*<br/>
상태 저장된 된 파일 이름입니다.

*symstat_arg*<br/>
저장 된 파일 이름의 기호화 된 링크 상태입니다.

## <a name="op_neq"></a> operator!=

멤버 함수는 `!(*this == right)`를 반환합니다.

```cpp
bool operator!=(const directory_entry& right) const noexcept;
```

### <a name="parameters"></a>매개 변수

*right*<br/>
합니다 [directory_entry](../standard-library/directory-entry-class.md) 비교할는 `directory_entry`합니다.

## <a name="op_as"></a> operator=

기본 멤버 대입 연산자가 예상대로 작동합니다.

```cpp
directory_entry& operator=(const directory_entry&) = default;
directory_entry& operator=(directory_entry&&) noexcept = default;
```

### <a name="parameters"></a>매개 변수

*right*<br/>
합니다 [directory_entry](../standard-library/directory-entry-class.md) 에 복사 되는 `directory_entry`합니다.

## <a name="op_eq"></a> operator==

멤버 함수는 `mypath == right.mypath`를 반환합니다.

```cpp
bool operator==(const directory_entry& right) const noexcept;
```

### <a name="parameters"></a>매개 변수

*right*<br/>
합니다 [directory_entry](../standard-library/directory-entry-class.md) 비교할는 `directory_entry`합니다.

## <a name="op_lt"></a> 연산자&lt;

멤버 함수는 `mypath < right.mypath`를 반환합니다.

```cpp
bool operator<(const directory_entry& right) const noexcept;
```

### <a name="parameters"></a>매개 변수

*right*<br/>
합니다 [directory_entry](../standard-library/directory-entry-class.md) 비교할는 `directory_entry`합니다.

## <a name="op_lteq"></a> 연산자&lt;=

멤버 함수는 `!(right < *this)`를 반환합니다.

```cpp
bool operator&lt;=(const directory_entry& right) const noexcept;
```

### <a name="parameters"></a>매개 변수

*right*<br/>
합니다 [directory_entry](../standard-library/directory-entry-class.md) 비교할는 `directory_entry`합니다.

## <a name="op_gt"></a> 연산자&gt;

멤버 함수는 `right < *this`를 반환합니다.

```cpp
bool operator&gt;(const directory_entry& right) const noexcept;
```

### <a name="parameters"></a>매개 변수

*right*<br/>
합니다 [directory_entry](../standard-library/directory-entry-class.md) 비교할는 `directory_entry`합니다.

## <a name="op_gteq"></a> 연산자&gt;=

멤버 함수는 `!(*this < right)`를 반환합니다.

```cpp
bool operator&gt;=(const directory_entry& right) const noexcept;
```

### <a name="parameters"></a>매개 변수

*right*<br/>
합니다 [directory_entry](../standard-library/directory-entry-class.md) 비교할는 `directory_entry`합니다.

## <a name="path_type"></a> const path_type 연산자 &

멤버 연산자는 `mypath`을 반환합니다.

```cpp
operator const std::experimental::filesystem::path&() const;
```

## <a name="path"></a> 경로

멤버 함수는 `mypath`를 반환합니다.

```cpp
const std::experimental::filesystem::path& path() const noexcept;
```

## <a name="replace_filename"></a> replace_filename

멤버 함수 `mypath` 사용 하 여 `mypath.parent_path()`  /  *pval*를 `mystat` 사용 하 여 *stat_arg로*, 및 `mysymstat` 사용 하 여 *symstat_arg로*

```cpp
void replace_filename(
    const std::experimental::filesystem::path& pval,
    file_status stat_arg = file_status(),
    file_status symstat_arg = file_status());
```

### <a name="parameters"></a>매개 변수

*pval*<br/>
저장 된 파일 이름 경로입니다.

*stat_arg*<br/>
상태 저장된 된 파일 이름입니다.

*symstat_arg*<br/>
저장 된 파일 이름의 기호화 된 링크 상태입니다.

## <a name="status"></a> 상태

두 멤버 함수는 반환 `mystat` 변경 될 수 있는 먼저 다음과 같이 합니다.

1. 경우 `status_known(mystat)` 이면 아무 작업도 수행 합니다.

1. 그렇지 않고 `!status_known(mysymstat) && !is_symlink(mysymstat)` 한 다음 `mystat = mysymstat`합니다.

```cpp
file_status status() const;
file_status status(error_code& ec) const noexcept;
```

### <a name="parameters"></a>매개 변수

*ec*<br/>
상태 오류 코드입니다.

## <a name="symlink_status"></a> symlink_status

두 멤버 함수는 반환 `mysymstat` 변경 될 수 있는 먼저 다음과 같이 합니다. 경우 `status_known(mysymstat)` 이면 아무 작업도 수행 합니다. 그렇지 않으면 `mysymstat = symlink_status(mypval)`입니다.

```cpp
file_status symlink_status() const;
file_status symlink_status(error_code& ec) const noexcept;
```

### <a name="parameters"></a>매개 변수

*ec*<br/>
상태 오류 코드입니다.

## <a name="see-also"></a>참고자료

[헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<filesystem&gt;](../standard-library/filesystem.md)<br/>
