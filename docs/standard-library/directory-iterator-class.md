---
title: directory_iterator 클래스
ms.date: 09/10/2018
f1_keywords:
- filesystem/std::experimental::filesystem::directory_iterator
- filesystem/std::experimental::filesystem::_Directory_iterator::_Directory_iterator
- filesystem/std::experimental::filesystem::directory_iterator::directory_iterator
- filesystem/std::experimental::filesystem::directory_iterator::increment
- filesystem/std::experimental::filesystem::directory_iterator::operator=
- filesystem/std::experimental::filesystem::directory_iterator::operator==
- filesystem/std::experimental::filesystem::directory_iterator::operator!=
- filesystem/std::experimental::filesystem::directory_iterator::operator*
- filesystem/std::experimental::filesystem::directory_iterator::operator-&gt;
- filesystem/std::experimental::filesystem::directory_iterator::operator++
ms.assetid: dca2ecf8-3e69-4644-a83d-705061e10cc8
helpviewer_keywords:
- std::experimental::filesystem::directory_iterator
- std::experimental::filesystem::_Directory_iterator::_Directory_iterator
- std::experimental::filesystem::directory_iterator
- std::experimental::filesystem::directory_iterator::directory_iterator
- std::experimental::filesystem::directory_iterator::increment
- std::experimental::filesystem::directory_iterator::operator=
- std::experimental::filesystem::directory_iterator::operator==
- std::experimental::filesystem::directory_iterator::operator!=
- std::experimental::filesystem::directory_iterator::operator*
- std::experimental::filesystem::directory_iterator::operator-&gt;
- std::experimental::filesystem::directory_iterator::operator++
ms.openlocfilehash: 6763f2a96b771fadbec311cf8740352fff53e29a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62413848"
---
# <a name="directoryiterator-class"></a>directory_iterator 클래스

디렉터리에서 파일 이름을 통해 시퀀스되는 입력 반복기에 대해 설명합니다. 반복기에 대 한 `X`, 식 `*X` 클래스의 개체로 계산 `directory_entry` 파일 이름 및 해당 상태에 대 한 알려진 모든 항목을 래핑하는 합니다.

클래스 형식의 개체를 저장 `path`라는 `mydir` 시퀀스 할 디렉터리의 이름을 나타내는 표시 및 형식의 개체에 대 한 여기 `directory_entry` 호출 `myentry` 현재 나타내는 여기 디렉터리 시퀀스에서 파일 이름입니다. 형식의 기본 생성 개체를 `directory_entry` 는 빈 `mydir` pathname 시퀀스의 끝 반복기를 나타냅니다.

예를 들어, 디렉터리를 지정 `abc` 항목과 `def` 고 `ghi`, 코드:

`for (directory_iterator next(path("abc")), end; next != end; ++next)     visit(next->path());`

호출 `visit` 인수를 사용 하 여 `path("abc/def")` 고 `path("abc/ghi")`입니다.

자세한 내용 및 코드 예제를 보려면 [파일 시스템 탐색(C++)](../standard-library/file-system-navigation.md)을 참조하세요.

## <a name="syntax"></a>구문

```cpp
class directory_iterator;
```

### <a name="constructors"></a>생성자

|생성자|설명|
|-|-|
|[directory_iterator](#directory_iterator)|디렉터리의 파일 이름을 통해 시퀀스 되는 입력된 반복기를 생성 합니다.|

### <a name="member-functions"></a>멤버 함수

|멤버 함수|설명|
|-|-|
|[increment](#increment)|디렉터리에서 다음 파일 이름으로 이동 하려고 합니다.|

### <a name="operators"></a>연산자

|연산자|설명|
|-|-|
|[operator!=](#op_neq)|`!(*this == right)`를 반환합니다.|
|[operator=](#op_as)|기본 멤버 대입 연산자가 예상대로 작동합니다.|
|[연산자==](#op_eq)|반환 **true** 두 경우에 `*this` 하 고 *오른쪽* 가 시퀀스의 끝 반복기 이거나 둘 다 하지 최종-의-시퀀스-반복기는 합니다.|
|[operator*](#op_star)|`myentry`를 반환합니다.|
|[operator->](#op_cast)|`&**this`를 반환합니다.|
|[operator++](#op_increment)|호출 `increment()`, 다음 반환 `*this`, 호출 개체의 복사본 또는 `increment()`, 그런 다음 복사본을 반환 합니다.|

## <a name="requirements"></a>요구 사항

**헤더:** \<experimental/filesystem>

**네임스페이스:** std::experimental::filesystem

## <a name="directory_iterator"></a> directory_iterator::directory_iterator

첫 번째 생성자는 시퀀스의 끝 반복기를 생성합니다. 두 번째 및 세 번째 생성자 저장소 *pval* 에서 `mydir`을 열고 읽는 시도 `mydir` 디렉터리로 합니다. 경우 성공 하면 첫 번째 파일에에서 저장 디렉터리 `myentry`; 시퀀스의 끝 반복기를 생성 합니다.

기본 생성자는 예상대로 작동합니다.

```cpp
directory_iterator() noexcept;
explicit directory_iterator(const path& pval);

directory_iterator(const path& pval, error_code& ec) noexcept;
directory_iterator(const directory_iterator&) = default;
directory_iterator(directory_iterator&&) noexcept = default;
```

### <a name="parameters"></a>매개 변수

*pval*<br/>
저장 된 파일 이름 경로입니다.

*ec*<br/>
상태 오류 코드입니다.

*directory_iterator*<br/>
저장 된 개체입니다.

## <a name="increment"></a> directory_iterator::increment

함수는 디렉터리의 다음 파일 이름으로 이동하려고 합니다. 성공 하는 경우 해당 파일에서를 저장 `myentry`; 그렇지 않으면 시퀀스의 끝 반복기를 생성 합니다.

```cpp
directory_iterator& increment(error_code& ec) noexcept;
```

## <a name="op_neq"></a> directory_iterator::operator!=

멤버 연산자는 `!(*this == right)`을 반환합니다.

```cpp
bool operator!=(const directory_iterator& right) const;
```

### <a name="parameters"></a>매개 변수

*right*<br/>
합니다 [directory_iterator](../standard-library/directory-iterator-class.md) 비교할는 `directory_iterator`합니다.

## <a name="op_as"></a> directory_iterator::operator=

기본 멤버 대입 연산자가 예상대로 작동합니다.

```cpp
directory_iterator& operator=(const directory_iterator&) = default;
directory_iterator& operator=(directory_iterator&&) noexcept = default;
```

### <a name="parameters"></a>매개 변수

*right*<br/>
합니다 [directory_iterator](../standard-library/directory-iterator-class.md) 에 복사 되는 `directory_iterator`합니다.

## <a name="op_eq"></a> directory_iterator::operator==

멤버 연산자를 반환 합니다 **true** 두 경우에 `*this` 하 고 *오른쪽* 가 시퀀스의 끝 반복기 이거나 둘 다 하지 최종-의-시퀀스-반복기는 합니다.

```cpp
bool operator==(const directory_iterator& right) const;
```

### <a name="parameters"></a>매개 변수

*right*<br/>
합니다 [directory_iterator](../standard-library/directory-iterator-class.md) 비교할는 `directory_iterator`합니다.

## <a name="op_star"></a> directory_iterator::operator*

멤버 연산자는 `myentry`을 반환합니다.

```cpp
const directory_entry& operator*() const;
```

## <a name="op_cast"></a> directory_iterator::operator->

멤버 함수는 `&**this`를 반환합니다.

```cpp
const directory_entry * operator->() const;
```

## <a name="op_increment"></a> directory_iterator::operator++

첫 번째 멤버 함수 호출 `increment()`를 반환 합니다 `*this`합니다. 두 번째 멤버 함수 호출 개체의 복사본 `increment()`, 그런 다음 복사본을 반환 합니다.

```cpp
directory_iterator& operator++();
directory_iterator& operator++(int);
```

### <a name="parameters"></a>매개 변수

*int*<br/>
증가 수입니다.

## <a name="see-also"></a>참고자료

[헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<filesystem>](../standard-library/filesystem.md)<br/>
[파일 시스템 탐색(C++)](../standard-library/file-system-navigation.md)<br/>
