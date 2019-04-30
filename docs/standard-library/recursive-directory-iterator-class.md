---
title: recursive_directory_iterator 클래스
ms.date: 09/10/2018
f1_keywords:
- filesystem/std::tr2::sys::recursive_directory_iterator
ms.assetid: 79a061bd-5b64-404c-97e8-749c888c2ced
ms.openlocfilehash: 52e6f738aa226dba26bae0cf6e97cd18d107d677
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62370133"
---
# <a name="recursivedirectoryiterator-class"></a>recursive_directory_iterator 클래스

입력된 반복기를 디렉터리의 파일 이름을 통해 시퀀스 되 수 있는 하위 디렉터리가 재귀적으로 내림차순으로 설명 합니다. 반복기에 대 한 `X`, 식 `*X` 클래스의 개체로 계산 `directory_entry` 파일 이름 및 해당 상태에 대 한 알려진 모든 항목을 래핑하는 합니다.

자세한 내용 및 코드 예제를 보려면 [파일 시스템 탐색(C++)](../standard-library/file-system-navigation.md)을 참조하세요.

## <a name="syntax"></a>구문

```cpp
class recursive_directory_iterator;
```

## <a name="remarks"></a>설명

템플릿 클래스에는 다음 항목이 저장됩니다.

1. 형식의 개체 `stack<pair<directory_iterator, path>>`라는 `mystack` 여기을 시퀀스 할 디렉터리의 중첩을 나타내는 표시를 위해

1. 형식의 개체 `directory_entry` 호출 `myentry` 디렉터리 시퀀스에서 현재 파일 이름을 나타내는 여기

1. 형식의 개체 **bool**라는 `no_push` 여기에 하위 디렉터리로 재귀적 상속이 비활성화 되었는지 여부를 기록 합니다.

1. 형식의 개체 `directory_options`라는 `myoptions` 생성 시 설정 된 옵션을 기록 하는 여기

형식의 기본 생성 개체를 `recursive_directory_entry` 에 시퀀스의 끝 반복기가 `mystack.top().first` 시퀀스의 끝 반복기를 나타냅니다. 예를 들어, 디렉터리를 지정 `abc` 항목과 `def` (디렉터리) `def/ghi`, 및 `jkl`, 코드:

```cpp
for (recursive_directory_iterator next(path("abc")), end; next != end; ++next)
    visit(next->path());
```

인수를 사용 하 여 visit를 호출 `path("abc/def/ghi")` 고 `path("abc/jkl")`입니다. 두 가지 방법으로 디렉터리 하위 트리를 통한 시퀀싱을 한정할 수 있습니다.

1. Symlink 디렉터리 생성 하는 경우에 검색 됩니다는 `recursive_directory_iterator` 사용 하 여는 `directory_options` 값인 인수 `directory_options::follow_directory_symlink`합니다.

1. 호출 하는 경우 `disable_recursion_pending` 다음에 증가 하는 동안 후속 디렉터리가 재귀적으로 검색 되지 것입니다.

### <a name="constructors"></a>생성자

|생성자|설명|
|-|-|
|[recursive_directory_iterator](#recursive_directory_iterator)|`recursive_directory_iterator`를 생성합니다.|

### <a name="member-functions"></a>멤버 함수

|멤버 함수|설명|
|-|-|
|[depth](#depth)|반환 `mystack.size() - 1`이므로 `pval` 깊이가 0입니다.|
|[disable_recursion_pending](#disable_recursion_pending)|저장소 **true** 에서 `no_push`합니다.|
|[increment](#increment)|시퀀스의 다음 파일 이름으로 이동 합니다.|
|[options](#options)|`myoptions`를 반환합니다.|
|[pop](#pop)|다음 개체를 반환 합니다.|
|[recursion_pending](#recursion_pending)|`!no_push`를 반환합니다.|

### <a name="operators"></a>연산자

|연산자|설명|
|-|-|
|[operator!=](#op_neq)|`!(*this == right)`를 반환합니다.|
|[operator=](#op_as)|기본 멤버 대입 연산자가 예상대로 작동합니다.|
|[연산자==](#op_eq)|반환 **true** 두 경우에 `*this` 하 고 *오른쪽* 가 시퀀스의 끝 반복기 이거나 둘 다 하지 최종-의-시퀀스-반복기는 합니다.|
|[operator*](#op_multiply)|`myentry`를 반환합니다.|
|[operator->](#op_cast)|`&**this`를 반환합니다.|
|[operator++](#op_increment)|증가 된 `recursive_directory_iterator`합니다.|

## <a name="requirements"></a>요구 사항

**헤더:** \<파일 시스템 >

**네임스페이스:** std::tr2::sys

## <a name="depth"></a> recursive_directory_iterator::depth

반환 `mystack.size() - 1`이므로 `pval` 깊이가 0입니다.

```cpp
int depth() const;
```

## <a name="disable_recursion_pending"></a> recursive_directory_iterator::disable_recursion_pending

저장소 **true** 에서 `no_push`합니다.

```cpp
void disable_recursion_pending();
```

## <a name="increment"></a> recursive_directory_iterator::increment

시퀀스의 다음 파일 이름으로 이동 합니다.

```cpp
recursive_directory_iterator& increment(error_code& ec) noexcept;
```

### <a name="parameters"></a>매개 변수

*ec*<br/>
지정 된 오류 코드입니다.

### <a name="remarks"></a>설명

함수가 중첩된 시퀀스에서 다음 파일 이름으로 이동하려고 합니다. 성공 하는 경우 해당 파일에서를 저장 `myentry`; 그렇지 않으면 시퀀스의 끝 반복기를 생성 합니다.

## <a name="op_neq"></a> recursive_directory_iterator::operator!=

`!(*this == right)`를 반환합니다.

```cpp
bool operator!=(const recursive_directory_iterator& right) const;
```

### <a name="parameters"></a>매개 변수

*right*<br/>
합니다 [recursive_directory_iterator](../standard-library/recursive-directory-iterator-class.md) 비교 합니다.

## <a name="op_as"></a> recursive_directory_iterator::operator=

기본 멤버 대입 연산자가 예상대로 작동합니다.

```cpp
recursive_directory_iterator& operator=(const recursive_directory_iterator&) = default;
recursive_directory_iterator& operator=(recursive_directory_iterator&&) noexcept = default;
```

### <a name="parameters"></a>매개 변수

*recursive_directory_iterator*<br/>
합니다 [recursive_directory_iterator](../standard-library/recursive-directory-iterator-class.md) 에 복사 되는 `recursive_directory_iterator`합니다.

## <a name="op_eq"></a> recursive_directory_iterator::operator==

반환 **true** 두 경우에 `*this` 하 고 *오른쪽* 가 시퀀스의 끝 반복기 이거나 둘 다 하지 최종-의-시퀀스-반복기는 합니다.

```cpp
bool operator==(const recursive_directory_iterator& right) const;
```

### <a name="parameters"></a>매개 변수

*right*<br/>
합니다 [recursive_directory_iterator](../standard-library/recursive-directory-iterator-class.md) 비교 합니다.

## <a name="op_multiply"></a> recursive_directory_iterator::operator*

`myentry`를 반환합니다.

```cpp
const directory_entry& operator*() const;
```

## <a name="op_cast"></a> recursive_directory_iterator::operator->

`&**this`를 반환합니다.

```cpp
const directory_entry * operator->() const;
```

## <a name="op_increment"></a> recursive_directory_iterator::operator++

증가 된 `recursive_directory_iterator`합니다.

```cpp
recursive_directory_iterator& operator++();

recursive_directory_iterator& operator++(int);
```

### <a name="parameters"></a>매개 변수

*int*<br/>
지정한 증가값입니다.

### <a name="remarks"></a>설명

첫 번째 멤버 함수 호출 `increment()`를 반환 합니다 `*this`합니다. 두 번째 멤버 함수 호출 개체의 복사본 `increment()`, 그런 다음 복사본을 반환 합니다.

## <a name="options"></a> recursive_directory_iterator::options

`myoptions`를 반환합니다.

```cpp
directory_options options() const;
```

## <a name="pop"></a> recursive_directory_iterator::pop

다음 개체를 반환 합니다.

```cpp
void pop();
```

### <a name="remarks"></a>설명

경우 `depth() == 0` 개체 시퀀스의 끝 반복기가 됩니다. 그렇지 않은 경우 멤버 함수는 현재(최하위) 디렉터리 검색을 종료하고 다음으로 낮은 깊이에서 다시 시작합니다.

## <a name="recursion_pending"></a> recursive_directory_iterator::recursion_pending

`!no_push`를 반환합니다.

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

*pval*<br/>
지정된 경로입니다.

*error_code*<br/>
지정 된 오류 코드입니다.

*opts*<br/>
지정 된 디렉터리 옵션입니다.

*recursive_directory_iterator*<br/>
생성된 `recursive_directory_iterator`이 복사본으로 지정될 `recursive_directory_iterator`입니다.

### <a name="remarks"></a>설명

첫 번째 생성자는 시퀀스의 끝 반복기를 생성합니다. 두 번째 및 세 번째 생성자 저장소 **false** 에서 `no_push` 및 `directory_options::none` 에서 `myoptions`을 열고 읽는 시도 *pval* 디렉터리로. 경우 성공 하면 초기화 `mystack` 및 `myentry` 중첩 된 시퀀스에서 첫 번째 directory가 아닌 파일 이름을 지정 하려면 시퀀스의 끝 반복기를 생성 합니다.

네 번째와 다섯 번째 생성자는 동일 하 게 두 번째 및 세 번째 먼저 저장 한다는 *opts* 에서 `myoptions`합니다. 기본 생성자는 예상대로 작동합니다.

## <a name="see-also"></a>참고자료

[헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<filesystem>](../standard-library/filesystem.md)<br/>
[파일 시스템 탐색(C++)](../standard-library/file-system-navigation.md)<br/>
