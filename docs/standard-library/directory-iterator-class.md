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
ms.openlocfilehash: 8c6dcce3de32c7e25d2489cb508454dff500a1a6
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68454421"
---
# <a name="directoryiterator-class"></a>directory_iterator 클래스

디렉터리에서 파일 이름을 통해 시퀀스되는 입력 반복기에 대해 설명합니다. 반복기 `X`의 경우 식은 `*X` 파일 이름 및 상태에 대해 알려진 모든 `directory_entry` 항목을 래핑하는 클래스의 개체로 계산 됩니다.

이 클래스는 표시의 목적을 `path`위해 여기 `mydir` 에 호출 되는 형식의 개체를 저장 합니다 .이 개체는 시퀀싱 할 디렉터리의 이름을 나타내고 `myentry` 여기에는 현재 `directory_entry` 를 나타내는 형식의 개체가 있습니다. 디렉터리 시퀀스의 파일 이름입니다. 형식의 `directory_entry` 기본 생성 된 개체는 빈 `mydir` 경로 이름을 가지 며 시퀀스의 끝 반복기를 나타냅니다.

예를 들어, 및 `abc` `ghi`항목 `def` 을 포함 하는 디렉터리를 지정 하는 경우 코드는 다음과 같습니다.

`for (directory_iterator next(path("abc")), end; next != end; ++next)     visit(next->path());`

는 및 `visit` 인수`path("abc/ghi")`를 사용 하 여를 호출 합니다. `path("abc/def")`

자세한 내용 및 코드 예제를 보려면 [파일 시스템 탐색(C++)](../standard-library/file-system-navigation.md)을 참조하세요.

## <a name="syntax"></a>구문

```cpp
class directory_iterator;
```

### <a name="constructors"></a>생성자

|생성자|Description|
|-|-|
|[directory_iterator](#directory_iterator)|디렉터리의 파일 이름을 통해 시퀀스 되는 입력 반복기를 생성 합니다.|

### <a name="member-functions"></a>멤버 함수

|멤버 함수|Description|
|-|-|
|[increment](#increment)|디렉터리의 다음 파일 이름으로 이동 하려고 합니다.|

### <a name="operators"></a>연산자

|연산자|설명|
|-|-|
|[operator!=](#op_neq)|`!(*this == right)`를 반환합니다.|
|[operator=](#op_as)|기본 멤버 대입 연산자가 예상대로 작동합니다.|
|[연산자==](#op_eq)|와 *right* 가 둘 다 `*this` 시퀀스의 끝 반복기 이거나 둘 다 시퀀스의 끝 반복기가 아닌 경우에만 **true** 를 반환 합니다.|
|[operator*](#op_star)|`myentry`를 반환합니다.|
|[operator->](#op_cast)|`&**this`를 반환합니다.|
|[operator++](#op_increment)|는 `increment()`를 호출 하 `*this`여 개체의 복사본을 반환 하 고를 호출한 `increment()`다음 복사본을 반환 합니다.|

## <a name="requirements"></a>요구 사항

**헤더:** \<experimental/filesystem>

**네임스페이스:** std::experimental::filesystem

## <a name="directory_iterator"></a> directory_iterator::directory_iterator

첫 번째 생성자는 시퀀스의 끝 반복기를 생성합니다. 두 번째 및 세 번째 생성자  는 pval `mydir`에를 저장 한 다음 디렉터리로 열고 `mydir` 읽으려고 시도 합니다. 성공 하면 첫 번째 파일 이름을의 `myentry`디렉터리에 저장 하 고, 그렇지 않으면 시퀀스의 끝 반복기를 생성 합니다.

기본 생성자는 예상대로 작동합니다.

```cpp
directory_iterator() noexcept;
explicit directory_iterator(const path& pval);

directory_iterator(const path& pval, error_code& ec) noexcept;
directory_iterator(const directory_iterator&) = default;
directory_iterator(directory_iterator&&) noexcept = default;
```

### <a name="parameters"></a>매개 변수

*pval*\
저장 된 파일 이름 경로입니다.

*ec*\
상태 오류 코드입니다.

*directory_iterator*\
저장 된 개체입니다.

## <a name="increment"></a> directory_iterator::increment

함수는 디렉터리의 다음 파일 이름으로 이동하려고 합니다. 성공 하면 해당 파일 이름을에 `myentry`저장 하 고, 그렇지 않으면 시퀀스의 끝 반복기를 생성 합니다.

```cpp
directory_iterator& increment(error_code& ec) noexcept;
```

## <a name="op_neq"></a> directory_iterator::operator!=

멤버 연산자는 `!(*this == right)`을 반환합니다.

```cpp
bool operator!=(const directory_iterator& right) const;
```

### <a name="parameters"></a>매개 변수

*오른쪽*\
와 [](../standard-library/directory-iterator-class.md) 비교할 `directory_iterator`directory_iterator입니다.

## <a name="op_as"></a> directory_iterator::operator=

기본 멤버 대입 연산자가 예상대로 작동합니다.

```cpp
directory_iterator& operator=(const directory_iterator&) = default;
directory_iterator& operator=(directory_iterator&&) noexcept = default;
```

### <a name="parameters"></a>매개 변수

*오른쪽*\
에 [](../standard-library/directory-iterator-class.md) 복사 `directory_iterator`되는 directory_iterator입니다.

## <a name="op_eq"></a> directory_iterator::operator==

멤버 연산자는 및 *권한이* 모두 `*this` 시퀀스의 끝 반복기 이거나 둘 다 시퀀스의 끝 반복기가 아닌 경우에만 **true** 를 반환 합니다.

```cpp
bool operator==(const directory_iterator& right) const;
```

### <a name="parameters"></a>매개 변수

*오른쪽*\
와 [](../standard-library/directory-iterator-class.md) 비교할 `directory_iterator`directory_iterator입니다.

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

첫 번째 멤버 함수는 `increment()`를 호출한 다음 `*this`을 반환 합니다. 두 번째 멤버 함수는 개체의 복사본을 만들고를 호출한 `increment()`다음 복사본을 반환 합니다.

```cpp
directory_iterator& operator++();
directory_iterator& operator++(int);
```

### <a name="parameters"></a>매개 변수

*int*\
증가값입니다.

## <a name="see-also"></a>참고자료

[헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)\
[\<filesystem>](../standard-library/filesystem.md)\
[파일 시스템 탐색(C++)](../standard-library/file-system-navigation.md)
