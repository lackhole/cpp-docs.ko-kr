---
title: recursive_directory_iterator 클래스
ms.date: 09/10/2018
f1_keywords:
- filesystem/std::tr2::sys::recursive_directory_iterator
ms.assetid: 79a061bd-5b64-404c-97e8-749c888c2ced
ms.openlocfilehash: a5200c030986ebbcfccb1eba2963e8317c879eb6
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72686800"
---
# <a name="recursive_directory_iterator-class"></a>recursive_directory_iterator 클래스

디렉터리의 파일 이름을 통해 시퀀스 되는 입력 반복기에 대해 설명 합니다. 하위 디렉터리는 재귀적으로 내림차순으로 정렬 됩니다. 반복기 `X`의 경우 식 `*X`는 파일 이름과 상태에 대해 알려진 모든 항목을 래핑하는 `directory_entry` 클래스의 개체로 계산 됩니다.

자세한 내용 및 코드 예제를 보려면 [파일 시스템 탐색(C++)](../standard-library/file-system-navigation.md)을 참조하세요.

## <a name="syntax"></a>구문

```cpp
class recursive_directory_iterator;
```

## <a name="remarks"></a>주의

클래스 템플릿은 다음을 저장 합니다.

1. 표시의 용도를 위해 여기에 `mystack` 이라는 `stack<pair<directory_iterator, path>>` 형식의 개체입니다 .이 개체는 시퀀싱 할 디렉터리의 중첩을 나타냅니다.

1. `directory_entry` 형식의 개체는 디렉터리 시퀀스의 현재 파일 이름을 나타내는 `myentry` 여기에서 호출 됩니다.

1. 여기에 `no_push` 이라고 하는 **bool**형식의 개체입니다 .이 개체는 하위 디렉터리에 대 한 재귀를 사용할 수 없는지 여부를 기록 합니다.

1. `directory_options` 형식의 개체입니다. 여기에서 `myoptions`는 생성 시 설정 된 옵션을 기록 합니다.

@No__t_0 형식의 기본 생성 된 개체 `mystack.top().first`에는 시퀀스의 끝 반복기가 있으며 시퀀스의 끝 반복기를 나타냅니다. 예를 들어, 디렉터리가 `def` (디렉터리), `def/ghi` 및 `jkl` 인 디렉터리가 `abc` 경우 코드는 다음과 같습니다.

```cpp
for (recursive_directory_iterator next(path("abc")), end; next != end; ++next)
    visit(next->path());
```

`path("abc/def/ghi")` 인수와 `path("abc/jkl")`를 사용 하 여 방문을 호출 합니다. 다음 두 가지 방법으로 디렉터리 하위 트리를 통한 시퀀싱을 한정할 수 있습니다.

1. 값을 `directory_options::follow_directory_symlink` 하는 `directory_options` 인수를 사용 하 여 `recursive_directory_iterator`를 생성 하는 경우에만 디렉터리 symlink 검색 됩니다.

1. @No__t_0를 호출 하면 증분 중에 발생 한 후속 디렉터리가 재귀적으로 검색 되지 않습니다.

### <a name="constructors"></a>생성자

|생성자|설명|
|-|-|
|[recursive_directory_iterator](#recursive_directory_iterator)|`recursive_directory_iterator`를 생성합니다.|

### <a name="member-functions"></a>멤버 함수

|멤버 함수|설명|
|-|-|
|[depth](#depth)|는 `mystack.size() - 1`를 반환 하므로 `pval` 깊이가 0입니다.|
|[disable_recursion_pending](#disable_recursion_pending)|@No__t_1에 **true** 를 저장 합니다.|
|[increment](#increment)|시퀀스에서 다음 파일 이름으로 이동 합니다.|
|[options](#options)|`myoptions`을 반환합니다.|
|[pop](#pop)|다음 개체를 반환 합니다.|
|[recursion_pending](#recursion_pending)|`!no_push`을 반환합니다.|

### <a name="operators"></a>연산자

|연산자|설명|
|-|-|
|[operator!=](#op_neq)|`!(*this == right)`을 반환합니다.|
|[operator=](#op_as)|기본 멤버 대입 연산자가 예상대로 작동합니다.|
|[연산자==](#op_eq)|@No__t_1와 *right* 가 둘 다 시퀀스의 끝 반복기 이거나 둘 다 시퀀스의 끝 반복기가 아닌 경우에만 **true** 를 반환 합니다.|
|[operator*](#op_multiply)|`myentry`을 반환합니다.|
|[operator->](#op_cast)|`&**this`을 반환합니다.|
|[operator++](#op_increment)|@No__t_0를 늘립니다.|

## <a name="requirements"></a>요구 사항

**헤더:** \<filesystem >

**네임스페이스:** std::tr2::sys

## <a name="depth"></a> recursive_directory_iterator::depth

는 `mystack.size() - 1`를 반환 하므로 `pval` 깊이가 0입니다.

```cpp
int depth() const;
```

## <a name="disable_recursion_pending"></a> recursive_directory_iterator::disable_recursion_pending

@No__t_1에 **true** 를 저장 합니다.

```cpp
void disable_recursion_pending();
```

## <a name="increment"></a> recursive_directory_iterator::increment

시퀀스에서 다음 파일 이름으로 이동 합니다.

```cpp
recursive_directory_iterator& increment(error_code& ec) noexcept;
```

### <a name="parameters"></a>매개 변수

*ec* \
지정 된 오류 코드입니다.

### <a name="remarks"></a>주의

함수가 중첩된 시퀀스에서 다음 파일 이름으로 이동하려고 합니다. 성공 하면 해당 파일 이름을 `myentry`에 저장 합니다. 그렇지 않으면 시퀀스의 끝 반복기를 생성 합니다.

## <a name="op_neq"></a> recursive_directory_iterator::operator!=

`!(*this == right)`을 반환합니다.

```cpp
bool operator!=(const recursive_directory_iterator& right) const;
```

### <a name="parameters"></a>매개 변수

*오른쪽* \
비교할 [recursive_directory_iterator](../standard-library/recursive-directory-iterator-class.md) 입니다.

## <a name="op_as"></a> recursive_directory_iterator::operator=

기본 멤버 대입 연산자가 예상대로 작동합니다.

```cpp
recursive_directory_iterator& operator=(const recursive_directory_iterator&) = default;
recursive_directory_iterator& operator=(recursive_directory_iterator&&) noexcept = default;
```

### <a name="parameters"></a>매개 변수

*recursive_directory_iterator* \
`recursive_directory_iterator`에 복사되는 [recursive_directory_iterator](../standard-library/recursive-directory-iterator-class.md)입니다.

## <a name="op_eq"></a> recursive_directory_iterator::operator==

@No__t_1와 *right* 가 둘 다 시퀀스의 끝 반복기 이거나 둘 다 시퀀스의 끝 반복기가 아닌 경우에만 **true** 를 반환 합니다.

```cpp
bool operator==(const recursive_directory_iterator& right) const;
```

### <a name="parameters"></a>매개 변수

*오른쪽* \
비교할 [recursive_directory_iterator](../standard-library/recursive-directory-iterator-class.md) 입니다.

## <a name="op_multiply"></a> recursive_directory_iterator::operator*

`myentry`을 반환합니다.

```cpp
const directory_entry& operator*() const;
```

## <a name="op_cast"></a> recursive_directory_iterator::operator->

`&**this`을 반환합니다.

```cpp
const directory_entry * operator->() const;
```

## <a name="op_increment"></a> recursive_directory_iterator::operator++

@No__t_0를 늘립니다.

```cpp
recursive_directory_iterator& operator++();

recursive_directory_iterator& operator++(int);
```

### <a name="parameters"></a>매개 변수

*int* \
지정 된 증가값입니다.

### <a name="remarks"></a>주의

첫 번째 멤버 함수는 `increment()`를 호출한 다음 `*this`를 반환 합니다. 두 번째 멤버 함수는 개체의 복사본을 만들고 `increment()`를 호출한 다음 복사본을 반환 합니다.

## <a name="options"></a> recursive_directory_iterator::options

`myoptions`을 반환합니다.

```cpp
directory_options options() const;
```

## <a name="pop"></a> recursive_directory_iterator::pop

다음 개체를 반환 합니다.

```cpp
void pop();
```

### <a name="remarks"></a>주의

@No__t_0 경우 개체가 시퀀스의 끝 반복기가 됩니다. 그렇지 않은 경우 멤버 함수는 현재(최하위) 디렉터리 검색을 종료하고 다음으로 낮은 깊이에서 다시 시작합니다.

## <a name="recursion_pending"></a> recursive_directory_iterator::recursion_pending

`!no_push`을 반환합니다.

```cpp
bool recursion_pending() const;
```

## <a name="recursive_directory_iterator"></a> recursive_directory_iterator::recursive_directory_iterator

`recursive_directory_iterator`를 생성합니다.

```cpp
recursive_directory_iterator() noexcept;
explicit recursive_directory_iterator(const path& pval);

recursive_directory_iterator(const path& pval,
    error_code& ec) noexcept;
recursive_directory_iterator(const path& pval,
    directory_options opts);

recursive_directory_iterator(const path& pval,
    directory_options opts,
    error_code& ec) noexcept;
recursive_directory_iterator(const recursive_directory_iterator&) = default;
recursive_directory_iterator(recursive_directory_iterator&&) noexcept = default;
```

### <a name="parameters"></a>매개 변수

*pval* \
지정된 경로입니다.

*error_code* \
지정 된 오류 코드입니다.

*opts* \
지정 된 디렉터리 옵션입니다.

*recursive_directory_iterator* \
생성된 `recursive_directory_iterator`이 복사본으로 지정될 `recursive_directory_iterator`입니다.

### <a name="remarks"></a>주의

첫 번째 생성자는 시퀀스의 끝 반복기를 생성합니다. 두 번째 및 세 번째 생성자는 `no_push`에 **false** 를 저장 하 고 `myoptions`에 `directory_options::none` 한 다음 *pval* 를 디렉터리로 열고 읽습니다. 성공 하면 `mystack`를 초기화 하 고 `myentry` 중첩 된 시퀀스에서 디렉터리가 아닌 첫 번째 파일 이름을 지정 합니다. 그렇지 않으면 시퀀스의 끝 반복기를 생성 합니다.

네 번째 및 다섯 번째 생성자는 `myoptions`에 먼저 *opts* 를 저장 한다는 점을 제외 하 고 두 번째와 세 번째 생성자와 동일 하 게 동작 합니다. 기본 생성자는 예상대로 작동합니다.

## <a name="see-also"></a>참조

[헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)\
[\<filesystem>](../standard-library/filesystem.md)\
[파일 시스템 탐색(C++)](../standard-library/file-system-navigation.md)
