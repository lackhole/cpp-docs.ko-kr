---
title: '&lt;filesystem&gt; 함수'
ms.date: 03/27/2019
f1_keywords:
- FILESYSTEM/std::experimental::filesystem::absolute
- FILESYSTEM/std::experimental::filesystem::canonical
- FILESYSTEM/std::experimental::filesystem::copy
- FILESYSTEM/std::experimental::filesystem::copy_file
- FILESYSTEM/std::experimental::filesystem::copy_symlink
- FILESYSTEM/std::experimental::filesystem::create_directories
- FILESYSTEM/std::experimental::filesystem::create_directory
- FILESYSTEM/std::experimental::filesystem::create_directory_symlink
- FILESYSTEM/std::experimental::filesystem::create_hard_link
- FILESYSTEM/std::experimental::filesystem::create_symlink
- FILESYSTEM/std::experimental::filesystem::current_path
- FILESYSTEM/std::experimental::filesystem::equivalent
- FILESYSTEM/std::experimental::filesystem::exists
- FILESYSTEM/std::experimental::filesystem::file_size
- FILESYSTEM/std::experimental::filesystem::hard_link_count
- FILESYSTEM/std::experimental::filesystem::hash_value
- FILESYSTEM/std::experimental::filesystem::is_block_file
- FILESYSTEM/std::experimental::filesystem::is_character_file
- FILESYSTEM/std::experimental::filesystem::is_directory
- FILESYSTEM/std::experimental::filesystem::is_empty
- FILESYSTEM/std::experimental::filesystem::is_fifo
- FILESYSTEM/std::experimental::filesystem::is_other
- FILESYSTEM/std::experimental::filesystem::is_regular_file
- FILESYSTEM/std::experimental::filesystem::is_socket
- FILESYSTEM/std::experimental::filesystem::is_symlink
- FILESYSTEM/std::experimental::filesystem::last_write_time
- FILESYSTEM/std::experimental::filesystem::permissions
- FILESYSTEM/std::experimental::filesystem::read_symlink
- FILESYSTEM/std::experimental::filesystem::remove
- FILESYSTEM/std::experimental::filesystem::remove_all
- FILESYSTEM/std::experimental::filesystem::rename
- FILESYSTEM/std::experimental::filesystem::resize_file
- FILESYSTEM/std::experimental::filesystem::space
- FILESYSTEM/std::experimental::filesystem::status
- FILESYSTEM/std::experimental::filesystem::status_known
- FILESYSTEM/std::experimental::filesystem::swap
- FILESYSTEM/std::experimental::filesystem::symlink_status
- FILESYSTEM/std::experimental::filesystem::system_complete
- FILESYSTEM/std::experimental::filesystem::temp_directory_path
- FILESYSTEM/std::experimental::filesystem::u8path
ms.assetid: be3cb821-4728-4d47-ab78-858fa8aa5045
helpviewer_keywords:
- std::experimental::filesystem::absolute
- std::experimental::filesystem::canonical
- std::experimental::filesystem::copy
- std::experimental::filesystem::copy_file
- std::experimental::filesystem::copy_symlink
- std::experimental::filesystem::create_directories
- std::experimental::filesystem::create_directory
- std::experimental::filesystem::create_directory_symlink
- std::experimental::filesystem::create_hard_link
- std::experimental::filesystem::create_symlink
- std::experimental::filesystem::current_path
- std::experimental::filesystem::equivalent
- std::experimental::filesystem::exists
- std::experimental::filesystem::file_size
- std::experimental::filesystem::hard_link_count
- std::experimental::filesystem::hash_value
- std::experimental::filesystem::is_block_file
- std::experimental::filesystem::is_character_file
- std::experimental::filesystem::is_directory
- std::experimental::filesystem::is_empty
- std::experimental::filesystem::is_fifo
- std::experimental::filesystem::is_other
- std::experimental::filesystem::is_regular_file
- std::experimental::filesystem::is_socket
- std::experimental::filesystem::is_symlink
- std::experimental::filesystem::last_write_time
- std::experimental::filesystem::permissions
- std::experimental::filesystem::read_symlink
- std::experimental::filesystem::remove
- std::experimental::filesystem::remove_all
- std::experimental::filesystem::rename
- std::experimental::filesystem::resize_file
- std::experimental::filesystem::space
- std::experimental::filesystem::status
- std::experimental::filesystem::status_known
- std::experimental::filesystem::swap
- std::experimental::filesystem::symlink_status
- std::experimental::filesystem::system_complete
- std::experimental::filesystem::temp_directory_path
- std::experimental::filesystem::u8path
ms.openlocfilehash: 11a1857052dd7c242993e8a19afe26aae3c97c06
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62405107"
---
# <a name="ltfilesystemgt-functions"></a>&lt;filesystem&gt; 함수

[\<filesystem>](../standard-library/filesystem.md) 헤더의 이러한 사용 가능한 함수는 경로, 파일, symlink, 디렉터리 및 볼륨에서 수정 및 쿼리 작업을 수행합니다. 자세한 내용 및 코드 예제를 보려면 [파일 시스템 탐색(C++)](../standard-library/file-system-navigation.md)을 참조하세요.

||||
|-|-|-|
|[absolute](#absolute)|[begin](#begin)|[canonical](#canonical)|
|[copy](#copy)|[copy_file](#copy_file)|[copy_symlink](#copy_symlink)|
|[create_directories](#create_directories)|[create_directory](#create_directory)|[create_directory_symlink](#create_directory_symlink)|
|[create_hard_link](#create_hard_link)|[create_symlink](#create_symlink)|[current_path](#current_path)|
|[end](#end)|[equivalent](#equivalent)|[exists](#exists)|
|[file_size](#file_size)|[hard_link_count](#hard_link_count)|[hash_value](#hash_value)|
|[is_block_file](#is_block_file)|[is_character_file](#is_character_file)|[is_directory](#is_directory)|
|[is_empty](#is_empty)|[is_fifo](#is_fifo)|[is_other](#is_other)|
|[is_regular_file](#is_regular_file)|[is_socket](#is_socket)|[is_symlink](#is_symlink)|
|[last_write_time](#last_write_time)|[permissions](#permissions)|[read_symlink](#read_symlink)|
|[remove](#remove)|[remove_all](#remove_all)|[rename](#rename)|
|[resize_file](#resize_file)|[space](#space)|[status](#status)|
|[status_known](#status_known)|[swap](#swap)|[symlink_status](#symlink_status)|
|[system_complete](#system_complete)|[temp_directory_path](#temp_directory_path)|[u8path](#u8path)|

## <a name="absolute"></a> 절대

```cpp
path absolute(const path& pval, const path& base = current_path());
```

함수에 해당 하는 절대 경로 이름을 반환 합니다. *pval* 경로 상대적인 `base`:

1. 하는 경우 `pval.has_root_name() && pval.has_root_directory()` 반환 *pval*합니다.

1. 하는 경우 `pval.has_root_name() && !pval.has_root_directory()` 반환 `pval.root_name()`  /  `absolute(base).root_directory()`  /  `absolute(base).relative_path()`  /  `pval.relative_path()`합니다.

1. 하는 경우 `!pval.has_root_name() && pval.has_root_directory()` 반환 `absolute(base).root_name()`  /  *pval*합니다.

1. 하는 경우 `!pval.has_root_name() && !pval.has_root_directory()` 반환 `absolute(base)`  /  *pval*합니다.

## <a name="begin"></a>  begin

```cpp
const directory_iterator& begin(const directory_iterator& iter) noexcept;
const recursive_directory_iterator&
    begin(const recursive_directory_iterator& iter) noexcept;
```

두 함수 모두 반환 *iter*합니다.

## <a name="canonical"></a>  canonical

```cpp
path canonical(const path& pval, const path& base = current_path());
path canonical(const path& pval, error_code& ec);
path canonical(const path& pval, const path& base, error_code& ec);
```

모든 함수는 절대 경로 형성 `pabs = absolute(pval, base)` (또는 `pabs = absolute(pval)` 기준 매개 변수가 없는 오버 로드), 단계의 다음 시퀀스의 정규 형식 줄이는 것:

1. 모든 경로 구성 요소 `X` 는 `is_symlink(X)` 됩니다 **true** 바뀝니다 `read_symlink(X)`합니다.

1. 모든 경로 구성 요소 `.` (점은 이전 경로 구성 요소에서 설정한 현재 디렉터리를 임) 제거 됩니다.

1. 경로 구성 요소의 모든 쌍 `X` / `..` (점-점은 이전 경로 구성 요소에서 설정한 부모 디렉터리 임 하는 데 사용) 제거 됩니다.

그런 다음 반환 `pabs`합니다.

## <a name="copy"></a>  copy

```cpp
void copy(const path& from, const path& to);
void copy(const path& from, const path& to, error_code& ec) noexcept;
void copy(const path& from, const path& to, copy_options opts);
void copy(const path& from, const path& to, copy_options opts, error_code& ec) noexcept;
```

복사 하거나 하나 이상의 파일을 연결할 수 모든 함수 *에서* 하 *에* 제어 *opts*,으로 사용 되는 `copy_options::none` 없는오버로드에대한*opts* 매개 변수입니다. *opts* 중 하나만 포함 됩니다.

- `skip_existing`, `overwrite_existing`또는 `update_existing`

- `copy_symlinks` 또는 `skip_symlinks`

- `directories_only`, `create_symlinks`또는 `create_hard_links`

함수는 먼저 file_status 값을 결정 `f` 에 대 한 *에서* 하 고 `t` 에 대 한 *에*:

- 경우 `opts & (copy_options::create_symlinks | copy_options::skip_symlinks)`를 호출 하 여 `symlink_status`

- 호출 하 여 그렇지 않은 경우 `status`

- 그렇지 않으면 오류를 보고합니다.

경우 `!exists(f) || equivalent(f, t) || is_other(f) || is_other(t) || is_directory(f)&& is_regular_file(t)`, 보고는 오류 (하 고 아무 작업도 수행).

그렇지 않은 경우, `is_symlink(f)` 후:

- 경우 `options & copy_options::skip_symlinks` 이면 아무 작업도 수행 합니다.

- 그렇지 않고 `!exists(t)&& options & copy_options::copy_symlinks` 한 다음 `copy_symlink(from, to, opts)`합니다.

- 그렇지 않으면 오류를 보고합니다.

그렇지 않은 경우, `is_regular_file(f)` 후:

- 경우 `opts & copy_options::directories_only` 이면 아무 작업도 수행 합니다.

- 그렇지 않고 `opts & copy_options::create_symlinks` 한 다음 `create_symlink(to, from)`합니다.

- 그렇지 않고 `opts & copy_options::create_hard_links` 한 다음 `create_hard_link(to, from)`합니다.

- 그렇지 않고 `is_directory(f)` 한 다음 `copy_file(from, to`  /  `from.filename(), opts)`합니다.

- 그렇지 않으면 `copy_file(from, to, opts)`입니다.

그렇지 않은 경우, `is_directory(f) && (opts & copy_options::recursive || !opts)` 후:

```cpp
if (!exists(t))
{  // copy directory contents recursively
    create_directory(to, from, ec);

    for (directory_iterator next(from), end; ec == error_code() && next != end; ++next)
    {
        copy(next->path(), to / next->path().filename(), opts, ec);
    }
}
```

그렇지 않으면 아무 작업도 수행하지 않습니다.

## <a name="copy_file"></a>  copy_file

```cpp
bool copy_file(const path& from, const path& to);
bool copy_file(const path& from, const path& to, error_code& ec) noexcept;
bool copy_file(const path& from, const path& to, copy_options opts);
bool copy_file(const path& from, const path& to, copy_options opts, error_code& ec) noexcept;
```

함수에서 파일을 복사할 수 있는 모든 *에서* 하 *하* 제어 *opts*,으로 사용 되는 `copy_options::none` 없는 오버 로드에 대 한 *opts*  매개 변수입니다. *opts* 중 하나만 포함 됩니다 `skip_existing`하십시오 `overwrite_existing`, 또는 `update_existing`합니다.

경우 `exists(to) && !(opts & (copy_options::skip_existing | copy_options::overwrite_existing | copy_options::update_existing))` 이면 파일이 이미 있다는 오류로 보고 합니다.

그렇지 `!exists(to) || opts & copy_options::overwrite_existing || opts & copy_options::update_existing&& last_write_time(to) < last_write_time(from) || !(opts & (copy_options::skip_existing | copy_options::overwrite_existing | copy_options:update_existing))` 내용과 파일의 특성을 복사 하려고 *에서* 파일로 *에*입니다. 복사 시도가 실패하는 경우 오류로 보고합니다.

이 함수는 반환 **true** 복사를 시도 하 여 성공, 그렇지 않은 경우 **false**합니다.

## <a name="copy_symlink"></a>  copy_symlink

```cpp
void copy_symlink(const path& from, const path& to);
void copy_symlink(const path& from, const path& to, error_code& ec) noexcept;
```

하는 경우 `is_directory(from)` 함수를 호출 하 여 `create_directory_symlink(from, to)`입니다. 그렇지 않으면 `create_symlink(from, to)`합니다.

## <a name="create_directories"></a>  create_directories

```cpp
bool create_directories(const path& pval);
bool create_directories(const path& pval, error_code& ec) noexcept;
```

a\/b\/c와 같은 경로 이름에 대해 함수는 필요에 따라 디렉터리 a\/b\/c를 만들 수 있도록 필요에 따라 디렉터리 a 및 a\/b를 만듭니다. 반환 **true** 디렉터리를 실제로 만드는 경우에 *pval*합니다.

## <a name="create_directory"></a>  create_directory

```cpp
bool create_directory(const path& pval);

bool create_directory(const path& pval, error_code& ec) noexcept;
bool create_directory(const path& pval, const path& attr);
bool create_directory(const path& pval, const path& attr, error_code& ec) noexcept;
```

이 함수는 디렉터리를 만듭니다 *pval* 필요에 따라 합니다. 만 true를 반환 디렉터리를 실제로 만드는 경우 *pval*, 경우 기존 파일에서 사용 권한을 복사 *attr*를 사용 하거나 `perms::all` 없는 오버 로드에 대 한 *attr*  매개 변수입니다.

## <a name="create_directory_symlink"></a>  create_directory_symlink

```cpp
void create_directory_symlink(const path& to, const path& link);
void create_directory_symlink(const path& to, const path& link, error_code& ec) noexcept;
```

이 함수는 디렉터리를 symlink로 링크를 만듭니다 *에*입니다.

## <a name="create_hard_link"></a>  create_hard_link

```cpp
void create_hard_link(const path& to,  const path& link);
void create_hard_link(const path& to, const path& link, error_code& ec) noexcept;
```

함수는 디렉터리 또는 파일에 하드 링크로 만듭니다 *에*입니다.

## <a name="create_symlink"></a>  create_symlink

```cpp
void create_symlink(const path& to,  const path& link);

void create_symlink(const path& to, const path& link, error_code& ec) noexcept;
```

함수를 만듭니다 *링크* 파일로 symlink로 *하려면*합니다.

## <a name="current_path"></a>  current_path

```cpp
path current_path();
path current_path(error_code& ec);
void current_path(const path& pval);
void current_path(const path& pval, error_code& ec) noexcept;
```

매개 변수가 없는 함수 *pval* 현재 디렉터리의 경로 이름을 반환 합니다. 나머지 함수는 현재 디렉터리를 설정 *pval*합니다.

## <a name="end"></a>  end

```cpp
directory_iterator& end(const directory_iterator& iter) noexcept;
recursive_directory_iterator& end(const recursive_directory_iterator& iter) noexcept;
```

첫 번째 함수 `directory_iterator()` 두 번째 함수를 반환 하 고 `recursive_directory_iterator()`

## <a name="equivalent"></a>  equivalent

```cpp
bool equivalent(const path& left, const path& right);
bool equivalent(const path& left, const path& right, error_code& ec) noexcept;
```

이 함수는 반환 **true** 경우에만 *왼쪽* 하 고 *오른쪽* 에서 동일한 파일 시스템 엔터티를 지정 합니다.

## <a name="exists"></a>  exists

```cpp
bool exists(file_status stat) noexcept;
bool exists(const path& pval);
bool exists(const path& pval, error_code& ec) noexcept;
```

첫 번째 함수는 `status_known && stat.type() != file_not_found`를 반환합니다. 두 번째 및 세 번째 함수는 반환 `exists(status(pval))`합니다.

## <a name="file_size"></a>  file_size

```cpp
uintmax_t file_size(const path& pval);
uintmax_t file_size(const path& pval, error_code& ec) noexcept;
```

함수에 지정 된 파일의 바이트 크기를 반환 *pval*이면 `exists(pval) && is_regular_file(pval)` 및 파일 크기를 확인할 수 있습니다. 그렇지 않으면 오류를 보고 하며 반환 `uintmax_t(-1)`합니다.

## <a name="hard_link_count"></a>  hard_link_count

```cpp
uintmax_t hard_link_count(const path& pval);
uintmax_t hard_link_count(const path& pval, error_code& ec) noexcept;
```

함수에 대 한 하드 링크의 수를 반환 합니다. *pval*, 또는 \-1에 오류가 발생 합니다.

## <a name="hash_value"></a>  hash_value

```cpp
size_t hash_value(const path& pval) noexcept;
```

함수에 대 한 해시 값을 반환 `pval.native()`합니다.

## <a name="is_block_file"></a>  is_block_file

```cpp
bool is_block_file(file_status stat) noexcept;
bool is_block_file(const path& pval);
bool is_block_file(const path& pval, error_code& ec) noexcept;
```

첫 번째 함수는 `stat.type() == file_type::block`를 반환합니다. 반환할 함수 나머지 `is_block_file(status(pval))`합니다.

## <a name="is_character_file"></a>  is_character_file

```cpp
bool is_character_file(file_status stat) noexcept;
bool is_character_file(const path& pval);
bool is_character_file(const path& pval, error_code& ec) noexcept;
```

첫 번째 함수는 `stat.type() == file_type::character`를 반환합니다. 반환할 함수 나머지 `is_character_file(status(pval))`합니다.

## <a name="is_directory"></a>  is_directory

```cpp
bool is_directory(file_status stat) noexcept;
bool is_directory(const path& pval);
bool is_directory(const path& pval, error_code& ec) noexcept;
```

첫 번째 함수는 `stat.type() == file_type::directory`를 반환합니다. 반환할 함수 나머지 `is_directory_file(status(pval))`합니다.

## <a name="is_empty"></a>  is_empty

```cpp
bool is_empty(file_status stat) noexcept;
bool is_empty(const path& pval);
bool is_empty(const path& pval, error_code& ec) noexcept;
```

하는 경우 `is_directory(pval)` 함수가 반환 `directory_iterator(pval) == directory_iterator()`; 그렇지 않으면 반환 `file_size(pval) == 0`합니다.

## <a name="is_fifo"></a>  is_fifo

```cpp
bool is_fifo(file_status stat) noexcept;
bool is_fifo(const path& pval);
bool is_fifo(const path& pval, error_code& ec) noexcept;
```

첫 번째 함수는 `stat.type() == file_type::fifo`를 반환합니다. 반환할 함수 나머지 `is_fifo(status(pval))`합니다.

## <a name="is_other"></a>  is_other

```cpp
bool is_other(file_status stat) noexcept;
bool is_other(const path& pval);
bool is_other(const path& pval, error_code& ec) noexcept;
```

첫 번째 함수는 `stat.type() == file_type::other`를 반환합니다. 반환할 함수 나머지 `is_other(status(pval))`합니다.

## <a name="is_regular_file"></a>  is_regular_file

```cpp
bool is_regular_file(file_status stat) noexcept;
bool is_regular_file(const path& pval);
bool is_regular_file(const path& pval, error_code& ec) noexcept;
```

첫 번째 함수는 `stat.type() == file_type::regular`를 반환합니다. 반환할 함수 나머지 `is_regular_file(status(pval))`합니다.

## <a name="is_socket"></a>  is_socket

```cpp
bool is_socket(file_status stat) noexcept;
bool is_socket(const path& pval);
bool is_socket(const path& pval, error_code& ec) noexcept;
```

첫 번째 함수는 `stat.type() == file_type::socket`를 반환합니다. 반환할 함수 나머지 `is_socket(status(pval))`합니다.

## <a name="is_symlink"></a>  is_symlink

```cpp
bool is_symlink(file_status stat) noexcept;
bool is_symlink(const path& pval);
bool is_symlink(const path& pval, error_code& ec) noexcept;
```

첫 번째 함수는 `stat.type() == file_type::symlink`를 반환합니다. 반환할 함수 나머지 `is_symlink(status(pval))`합니다.

## <a name="last_write_time"></a>  last_write_time

```cpp
file_time_type last_write_time(const path& pval);
file_time_type last_write_time(const path& pval, error_code& ec) noexcept;
void last_write_time(const path& pval, file_time_type new_time);
void last_write_time(const path& pval, file_time_type new_time, error_code& ec) noexcept;
```

처음 두 함수에 대 한 마지막 데이터 수정 시간을 반환 *pval*, 또는 `file_time_type(-1)` 오류가 발생 합니다. 마지막 두 함수에 대 한 마지막 데이터 수정 시간을 설정 *pval* 하 *new_time으로*입니다.

## <a name="permissions"></a>  permissions

```cpp
void permissions(const path& pval, perms mask);
void permissions(const path& pval, perms mask, error_code& ec) noexcept;
```

함수는 지정 된 경로 이름에 대 한 사용 권한을 설정 *pval* 하 `mask & perms::mask` 제어 `perms & (perms::add_perms | perms::remove_perms)`입니다. *마스크* 중 하나만 포함 됩니다 `perms::add_perms` 고 `perms::remove_perms`입니다.

하는 경우 `mask & perms::add_perms` 함수 사용 권한을 설정 `status(pval).permissions() | mask & perms::mask`합니다. 그렇지 않고 `mask & perms::remove_perms` 함수 사용 권한을 설정 `status(pval).permissions() & ~(mask & perms::mask)`합니다. 함수 권한으로 설정 하는 고, 그렇지 `mask & perms::mask`합니다.

## <a name="read_symlink"></a>  read_symlink

```cpp
path read_symlink(const path& pval);
path read_symlink(const path& pval, error_code& ec);
```

함수는 오류를 보고 하 고 반환 `path()` 경우 `!is_symlink(pval)`합니다. 그렇지 않은 경우 함수는 기호 링크를 포함하는 `path` 형식의 개체를 반환합니다.

## <a name="remove"></a>  remove

```cpp
bool remove(const path& pval);
bool remove(const path& pval, error_code& ec) noexcept;
```

이 함수는 반환 **true** 경우에만 `exists(symlink_status(pval))` 고 파일이 성공적으로 제거 됩니다. symlink가 지정하는 파일이 아닌 symlink 자체가 제거됩니다.

## <a name="remove_all"></a>  remove_all

```cpp
uintmax_t remove_all(const path& pval);
uintmax_t remove_all(const path& pval, error_code& ec) noexcept;
```

하는 경우 *pval* 디렉터리 함수를 재귀적으로 모든 디렉터리 항목을 다음 항목 자체를 제거 합니다. 그렇지 않으면 함수 호출 `remove`합니다. 함수는 성공적으로 제거된 모든 요소의 수를 반환합니다.

## <a name="rename"></a>  rename

```cpp
void rename(const path& from,  const path& to);
void rename(const path& from,  const path& to, error_code& ec) noexcept;
```

함수 이름 바꾸기 *에서* 하 *하려면*합니다. symlink가 지정하는 파일이 아닌 symlink 자체의 이름을 바꿉니다.

## <a name="resize_file"></a>  resize_file

```cpp
void resize(const path& pval, uintmax_t size);
void resize(const path& pval, uintmax_t size, error_code& ec) noexcept;
```

파일의 크기를 변경 하는 함수는 `file_size(pval) == size`

## <a name="space"></a>  space

```cpp
space_info space(const path& pval);
space_info space(const path& pval, error_code& ec) noexcept;
```

지정 된 볼륨에 대 한 정보를 반환 *pval*, 형식 구조의 `space_info`. 구조에 포함 된 `uintmax_t(-1)` 확인할 수 없는 모든 값에 대 한 합니다.

## <a name="status"></a>  status

```cpp
file_status status(const path& pval);
file_status status(const path& pval, error_code& ec) noexcept;
```

함수 반환 경로 이름 상태, 파일 형식 및 연관 된 권한만 *pval*합니다. symlink 자체는 테스트되지 않고 symlink가 지정하는 파일이 테스트됩니다.

## <a name="status_known"></a>  status_known

```cpp
bool status_known(file_status stat) noexcept;
```

함수 반환 `stat.type() != file_type::none`

## <a name="swap"></a>  swap

```cpp
void swap(path& left, path& right) noexcept;
```

콘텐츠를 교환 하는 함수 *왼쪽* 하 고 *오른쪽*합니다.

## <a name="symlink_status"></a>  symlink_status

```cpp
file_status symlink_status(const path& pval);
file_status symlink_status(const path& pval, erroxr_code& ec) noexcept;
```

함수 반환 경로 이름 symlink 상태, 파일 형식 및 연관 된 권한만 *pval*합니다. 함수는 동일 하 게 동작 `status(pval)` symlink이 테스트 자체를 제외 하 고 파일이 아닌 지정 합니다.

## <a name="system_complete"></a>  system_complete

```cpp
path system_complete(const path& pval);
path system_complete(const path& pval, error_code& ec);
```

이 함수는 필요에 따라 루트 이름과 연결된 현재 디렉터리를 고려하는 절대 경로 이름을 반환합니다. \(Posix에서 함수는 다음과 같이 반환 됩니다. `absolute(pval)`합니다.\)

## <a name="temp_directory_path"></a>  temp_directory_path

```cpp
path temp_directory_path();
path temp_directory_path(error_code& ec);
```

이 함수는 임시 파일을 포함하는 데 적합한 디렉터리의 경로 이름을 반환합니다.

## <a name="u8path"></a>  u8path

```cpp
template <class Source>
path u8path(const Source& source);

template <class InIt>
path u8path(InIt first, InIt last);
```

첫 번째 함수 동일 `path(source)` 두 번째 함수는 동일 하 게 동작 하 고 `path(first, last)` 제외 하 고 각각의 경우에서 지정 된 소스가 파일 시스템에 관계 없이 u t F-8로 인코드된 char 요소의 시퀀스로 수행 됩니다.
