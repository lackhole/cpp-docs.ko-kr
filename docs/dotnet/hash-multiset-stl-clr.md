---
title: hash_multiset(STL/CLR)
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- cliext::hash_multiset
- cliext::hash_multiset::begin
- cliext::hash_multiset::bucket_count
- cliext::hash_multiset::clear
- cliext::hash_multiset::const_iterator
- cliext::hash_multiset::const_reference
- cliext::hash_multiset::const_reverse_iterator
- cliext::hash_multiset::count
- cliext::hash_multiset::difference_type
- cliext::hash_multiset::empty
- cliext::hash_multiset::end
- cliext::hash_multiset::equal_range
- cliext::hash_multiset::erase
- cliext::hash_multiset::find
- cliext::hash_multiset::generic_container
- cliext::hash_multiset::generic_iterator
- cliext::hash_multiset::generic_reverse_iterator
- cliext::hash_multiset::generic_value
- cliext::hash_multiset::hash_delegate
- cliext::hash_multiset::hash_multiset
- cliext::hash_multiset::hasher
- cliext::hash_multiset::insert
- cliext::hash_multiset::iterator
- cliext::hash_multiset::key_comp
- cliext::hash_multiset::key_compare
- cliext::hash_multiset::key_type
- cliext::hash_multiset::load_factor
- cliext::hash_multiset::lower_bound
- cliext::hash_multiset::make_value
- cliext::hash_multiset::max_load_factor
- cliext::hash_multiset::operator=
- cliext::hash_multiset::rbegin
- cliext::hash_multiset::reference
- cliext::hash_multiset::rehash
- cliext::hash_multiset::rend
- cliext::hash_multiset::reverse_iterator
- cliext::hash_multiset::size
- cliext::hash_multiset::size_type
- cliext::hash_multiset::swap
- cliext::hash_multiset::to_array
- cliext::hash_multiset::upper_bound
- cliext::hash_multiset::value_comp
- cliext::hash_multiset::value_compare
- cliext::hash_multiset::value_type
helpviewer_keywords:
- <cliext/hash_set> header [STL/CLR]
- hash_multiset class [STL/CLR]
- <hash_set> header [STL/CLR]
- begin member [STL/CLR]
- bucket_count member [STL/CLR]
- clear member [STL/CLR]
- const_iterator member [STL/CLR]
- const_reference member [STL/CLR]
- const_reverse_iterator member [STL/CLR]
- count member [STL/CLR]
- difference_type member [STL/CLR]
- empty member [STL/CLR]
- end member [STL/CLR]
- equal_range member [STL/CLR]
- erase member [STL/CLR]
- find member [STL/CLR]
- generic_container member [STL/CLR]
- generic_iterator member [STL/CLR]
- generic_reverse_iterator member [STL/CLR]
- generic_value member [STL/CLR]
- hash_delegate member [STL/CLR]
- hash_multiset member [STL/CLR]
- hasher member [STL/CLR]
- insert member [STL/CLR]
- iterator member [STL/CLR]
- key_comp member [STL/CLR]
- key_compare member [STL/CLR]
- key_type member [STL/CLR]
- load_factor member [STL/CLR]
- lower_bound member [STL/CLR]
- make_value member [STL/CLR]
- max_load_factor member [STL/CLR]
- operator= member [STL/CLR]
- rbegin member [STL/CLR]
- reference member [STL/CLR]
- rehash member [STL/CLR]
- rend member [STL/CLR]
- reverse_iterator member [STL/CLR]
- size member [STL/CLR]
- size_type member [STL/CLR]
- swap member [STL/CLR]
- to_array member [STL/CLR]
- upper_bound member [STL/CLR]
- value_comp member [STL/CLR]
- value_compare member [STL/CLR]
- value_type member [STL/CLR]
ms.assetid: 8462bd21-6829-4dd3-ac81-c42d6fdf92f0
ms.openlocfilehash: 8d8e7ab9bcbaf9ea8ce95558c53d5936473f9c8f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62222977"
---
# <a name="hashmultiset-stlclr"></a>hash_multiset(STL/CLR)

템플릿 클래스는 요소의 양방향 액세스할 수 있는 다양 한 길이의 시퀀스를 제어 하는 개체를 설명 합니다. 컨테이너를 사용 하 `hash_multiset` 해시 테이블로 요소의 시퀀스를 관리 하려면 각 테이블 항목에 양방향 저장는 노드 및 한 개의 요소 저장 하는 각 노드의 목록을 연결 합니다. 각 요소의 값은 시퀀스를 정렬 키로 사용 됩니다.

아래 설명에 `GValue` 같습니다 `GKey`를 차례로 동일 *키* 후자는 참조 형식, 하지 않는 한이 경우에서는 `Key^`합니다.

## <a name="syntax"></a>구문

```cpp
template<typename Key>
    ref class hash_multiset
        :   public
        System::ICloneable,
        System::Collections::IEnumerable,
        System::Collections::ICollection,
        System::Collections::Generic::IEnumerable<GValue>,
        System::Collections::Generic::ICollection<GValue>,
        System::Collections::Generic::IList<GValue>,
        Microsoft::VisualC::StlClr::IHash<Gkey, GValue>
    { ..... };
```

### <a name="parameters"></a>매개 변수

*키*<br/>
제어 된 시퀀스의 요소 키 구성 요소의 형식입니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<cliext/hash_set >

**Namespace:** cliext

## <a name="declarations"></a>선언

|형식 정의|설명|
|---------------------|-----------------|
|[hash_multiset::const_iterator(STL/CLR)](#const_iterator)|제어되는 시퀀스에 대한 상수 반복기의 형식입니다.|
|[hash_multiset::const_reference(STL/CLR)](#const_reference)|요소에 대한 상수 참조의 형식입니다.|
|[hash_multiset::const_reverse_iterator(STL/CLR)](#const_reverse_iterator)|제어되는 시퀀스에 대한 상수 역방향 반복기의 형식입니다.|
|[hash_multiset::difference_type(STL/CLR)](#difference_type)|두 요소 사이의 (가능한 경우 부호 있는) 거리의 형식입니다.|
|[hash_multiset::generic_container(STL/CLR)](#generic_container)|컨테이너에 대 한 제네릭 인터페이스의 형식입니다.|
|[hash_multiset::generic_iterator(STL/CLR)](#generic_iterator)|컨테이너에 대 한 제네릭 인터페이스에 대 한 반복기의 형식입니다.|
|[hash_multiset::generic_reverse_iterator(STL/CLR)](#generic_reverse_iterator)|컨테이너에 대 한 제네릭 인터페이스에 대 한 역방향 반복기의 형식입니다.|
|[hash_multiset::generic_value(STL/CLR)](#generic_value)|제네릭 인터페이스에 대 한 컨테이너 요소 형식입니다.|
|[hash_multiset::hasher(STL/CLR)](#hasher)|키의 해시 대리자입니다.|
|[hash_multiset::iterator(STL/CLR)](#iterator)|제어되는 시퀀스에 대한 반복기의 형식입니다.|
|[hash_multiset::key_compare(STL/CLR)](#key_compare)|두 키의 순서 지정 대리자입니다.|
|[hash_multiset::key_type(STL/CLR)](#key_type)|정렬 키의 형식입니다.|
|[hash_multiset::reference(STL/CLR)](#reference)|요소에 대한 참조의 형식입니다.|
|[hash_multiset::reverse_iterator(STL/CLR)](#reverse_iterator)|제어되는 시퀀스에 대한 반대 반복기의 형식입니다.|
|[hash_multiset::size_type(STL/CLR)](#size_type)|두 요소 사이의 (음수가) 거리의 형식입니다.|
|[hash_multiset::value_compare(STL/CLR)](#value_compare)|두 요소 값의 순서 지정 대리자입니다.|
|[hash_multiset::value_type(STL/CLR)](#value_type)|요소의 형식입니다.|

|멤버 함수|설명|
|---------------------|-----------------|
|[hash_multiset::begin(STL/CLR)](#begin)|제어되는 시퀀스의 시작을 지정합니다.|
|[hash_multiset::bucket_count(STL/CLR)](#bucket_count)|버킷 수를 셉니다.|
|[hash_multiset::clear(STL/CLR)](#clear)|모든 요소를 제거합니다.|
|[hash_multiset::count(STL/CLR)](#count)|지정된 된 키와 일치 하는 요소를 계산 합니다.|
|[hash_multiset::empty(STL/CLR)](#empty)|요소가 있는지 여부를 테스트합니다.|
|[hash_multiset::end(STL/CLR)](#end)|제어되는 시퀀스의 끝을 지정합니다.|
|[hash_multiset::equal_range(STL/CLR)](#equal_range)|지정된 키와 일치하는 범위를 찾습니다.|
|[hash_multiset::erase(STL/CLR)](#erase)|지정된 위치에 있는 요소를 제거합니다.|
|[hash_multiset::find(STL/CLR)](#find)|지정된 키와 일치하는 요소를 찾습니다.|
|[hash_multiset::hash_delegate(STL/CLR)](#hash_delegate)|해시 키에 대 한 대리자를 복사합니다.|
|[hash_multiset::hash_multiset(STL/CLR)](#hash_multiset)|컨테이너 개체를 만듭니다.|
|[hash_multiset::insert(STL/CLR)](#insert)|요소를 추가합니다.|
|[hash_multiset::key_comp(STL/CLR)](#key_comp)|두 개의 키에 대 한 순서 지정 대리자를 복사합니다.|
|[hash_multiset::load_factor(STL/CLR)](#load_factor)|버킷당 평균 요소 수를 계산합니다.|
|[hash_multiset::lower_bound(STL/CLR)](#lower_bound)|지정된 된 키와 일치 하는 범위의 시작 부분을 찾습니다.|
|[hash_multiset::make_value(STL/CLR)](#make_value)|값 개체를 생성합니다.|
|[hash_multiset::max_load_factor(STL/CLR)](#max_load_factor)|버킷당 최대 요소 수를 가져오거나 설정합니다.|
|[hash_multiset::rbegin(STL/CLR)](#rbegin)|제어되는 역방향 시퀀스의 시작을 지정합니다.|
|[hash_multiset::rehash(STL/CLR)](#rehash)|해시 테이블을 다시 빌드합니다.|
|[hash_multiset::rend(STL/CLR)](#rend)|제어되는 역방향 시퀀스의 끝을 지정합니다.|
|[hash_multiset::size(STL/CLR)](#size)|요소 수를 계산합니다.|
|[hash_multiset::swap(STL/CLR)](#swap)|두 컨테이너의 내용을 바꿉니다.|
|[hash_multiset::to_array(STL/CLR)](#to_array)|제어 되는 시퀀스를 새 배열에 복사합니다.|
|[hash_multiset::upper_bound(STL/CLR)](#upper_bound)|지정된 된 키와 일치 하는 범위의 끝을 찾습니다.|
|[hash_multiset::value_comp(STL/CLR)](#value_comp)|두 요소 값에 대 한 순서 지정 대리자를 복사합니다.|

|연산자|설명|
|--------------|-----------------|
|[hash_multiset::operator=(STL/CLR)](#op)|제어되는 시퀀스를 바꿉니다.|

## <a name="interfaces"></a>인터페이스

|인터페이스|설명|
|---------------|-----------------|
|<xref:System.ICloneable>|개체를 복제 합니다.|
|<xref:System.Collections.IEnumerable>|요소 시퀀스입니다.|
|<xref:System.Collections.ICollection>|요소 그룹을 유지 합니다.|
|<xref:System.Collections.Generic.IEnumerable%601>|형식화 된 요소 시퀀스입니다.|
|<xref:System.Collections.Generic.ICollection%601>|형식화 된 요소 그룹을 유지 합니다.|
|IHash\<키, 값 >|제네릭 컨테이너를 유지 합니다.|

## <a name="remarks"></a>설명

개체를 할당 하 고 양방향으로 연결 된 목록에서 개별 노드로 제어 하는 시퀀스에 대 한 저장소를 해제 합니다. 액세스 속도 개체 하위 목록, 시퀀스로 목록 전체를 효율적으로 관리 목록 (해시 테이블)에 대 한 포인터의 다양 한 길이의 배열을 유지 관리 하거나 수도 버킷에 있습니다. 다른 한 노드의 콘텐츠를 복사 하 여 되지 노드 간 링크를 변경 하 여 순서가 지정 된 보관 하는 버킷으로 요소를 삽입 합니다. 즉, 삽입 하 고 나머지 요소를 방해 하지 않고 자유롭게 요소를 제거할 수 있습니다.

개체 형식의 저장 된 대리자 개체를 호출 하 여 제어 하는 각 버킷 정렬 [hash_set:: key_compare (STL/CLR)](../dotnet/hash-set-key-compare-stl-clr.md)합니다. Hash_set;을 생성 하는 경우 저장 된 대리자 개체를 지정할 수 있습니다. 기본값은 비교 없는 대리자 개체를 지정 하면 `operator<=(key_type, key_type)`합니다.

멤버 함수를 호출 하 여 저장 된 대리자 개체를 액세스할 [hash_set:: key_comp (STL/CLR)](../dotnet/hash-set-key-comp-stl-clr.md)`()`합니다. 이러한 대리자 개체 형식의 키 간에 동일한 순서를 정의 해야 합니다 [hash_set:: key_type (STL/CLR)](../dotnet/hash-set-key-type-stl-clr.md)합니다. 즉, 두 개의 키에 대 한 `X` 고 `Y`:

`key_comp()(X, Y)` 호출할 때마다 동일한 부울 결과 반환.

하는 경우 `key_comp()(X, Y) && key_comp()(Y, X)` 가 true 이면 `X` 및 `Y` 동일 하 게 정렬 하 라고 합니다.

처럼 동작 하는 정렬 규칙이 `operator<=(key_type, key_type)`, `operator>=(key_type, key_type)` 또는 `operator==(key_type, key_type)` eqivalent 순서를 정의 합니다.

컨테이너 되도록만 요소 키가 동일한 순서 (및 동일한 정수 값으로 해시)을 버킷 내에서 인접 한 note 합니다. 템플릿 클래스와 달리 [hash_set (STL/CLR)](../dotnet/hash-set-stl-clr.md)를 템플릿 클래스의 개체 `hash_multiset` 모든 요소에 대 한 키가 고유한 지 필요 하지 않습니다. (두 개 이상의 키 수 동일 하 게 정렬 됩니다.)

개체는 버킷 형식의 저장 된 대리자 개체를 호출 하 여 지정된 된 정렬 키를 포함 해야 결정 [hash_set:: hasher (STL/CLR)](../dotnet/hash-set-hasher-stl-clr.md)합니다. 멤버 함수를 호출 하 여이 저장 된 개체를 액세스할 [hash_set:: hash_delegate (STL/CLR)](../dotnet/hash-set-hash-delegate-stl-clr.md) `()` 키 값에 따라 달라 지는 정수 값을 가져오려고 합니다. Hash_set;을 생성 하는 경우 저장 된 대리자 개체를 지정할 수 있습니다. 기본값은 함수 없는 대리자 개체를 지정 하면 `System::Object::hash_value(key_type)`합니다. 즉, 모든 키에 대 한 `X` 고 `Y`:

`hash_delegate()(X)` 호출할 때마다 동일한 정수 결과 반환합니다.

경우 `X` 하 고 `Y` 동일 하 게 정렬, 한 다음 `hash_delegate()(X)` 와 같은 정수 결과 반환 해야 `hash_delegate()(Y)`합니다.

각 요소는 키와 값으로 사용 됩니다. 시퀀스는 조회, 삽입 및 모범 사례에 적어도 (일정 시간)-시퀀스의 요소 수와 무관 있는 작업의 수를 사용 하 여 임의 요소의 제거를 허용 하는 방식으로 표시 됩니다. 또한, 요소를 삽입할 경우 어떤 반복기도 무효화되지 않으며, 요소를 제거할 경우 제거된 요소를 가리키고 있는 반복기만 무효화됩니다.

해시 된 값은 균일 하 게 분산 되지 경우 단, 해시 테이블 수 중복 제거 합니다. 항상를 동일한 값을 반환 하는 해시 함수에 대 한 심각한-조회, 삽입 및 제거는 (선형 시간) 시퀀스의 요소 수에 비례 합니다. 컨테이너에서 평균 버킷 크기를 적절 한 해시 함수를 선택 하려고 하 고 해시 테이블 크기 (총 버킷), 있지만 이러한 옵션 중 일부 또는 모두 재정의할 수 있습니다. 예를 들어 함수를 보려면 [hash_set:: max_load_factor (STL/CLR)](../dotnet/hash-set-max-load-factor-stl-clr.md) 하 고 [hash_set:: rehash (STL/CLR)](../dotnet/hash-set-rehash-stl-clr.md)합니다.

Hash_multiset은 제어 된 시퀀스의 요소를 지정 하는 반복기를 제공 하는 인접 요소를 실행할 수 있습니다 즉 양방향 반복기를 지원 합니다. 반환 된 반복기에 해당 하는 특수 헤드 노드 [hash_multiset:: end (STL/CLR)](../dotnet/hash-multiset-end-stl-clr.md)`()`합니다. 있는 경우에 제어 된 시퀀스에서 마지막 요소를 연결할이 반복기를 감소 시킬 수 있습니다. 헤드 노드에 도달 하는 hash_multiset 반복기를 증가 시킬 수 있습니다 및 같음 비교 다음 `end()`합니다. 반환 된 반복기를 역 참조할 수 없습니다 있지만 `end()`합니다.

직접 임의 액세스 반복기를 필요로 하는 숫자 위치-지정 된 hash_multiset 요소를 참조할 수 없습니다는 참고 합니다.

Hash_multiset 반복기에 연결 된 해당 컨테이너에 대 한 핸들을 저장 하는 해당 연결된 hash_multiset 노드에 대 한 핸들을 저장 합니다. 반복기는 연결 된 컨테이너 개체에만 사용할 수 있습니다. Hash_multiset 반복기를 해당 연결된 hash_multiset 노드 일부 hash_multiset와 연결 된 유효한 상태로 유지 됩니다. 또한 유효한 반복기는 역-액세스 또는 같지 않은 하기만-지정 된 요소 값을 변경 하는 데 사용할 수 있습니다 `end()`합니다.

지우거 나 요소를 제거 합니다. 저장된 된 값에 대 한 소멸자를 호출 합니다. 모든 요소를 지웁니다 컨테이너를 제거 합니다. 따라서 요소 형식인 ref 클래스는 컨테이너 보다 수명이 길 컨테이너 요소가 있는지 확인 합니다. 단, 핸들의 컨테이너에는 *되지* 해당 요소를 제거 합니다.

## <a name="members"></a>멤버

## <a name="begin"></a> hash_multiset:: begin (STL/CLR)

제어되는 시퀀스의 시작을 지정합니다.

### <a name="syntax"></a>구문

```cpp
iterator begin();
```

### <a name="remarks"></a>설명

멤버 함수는 제어 된 시퀀스 또는 빈 시퀀스의 끝 바로 다음 첫 번째 요소를 지정 하는 양방향 반복기를 반환 합니다. 지정 하는 반복기를 사용 하면는 `current` 상태가 제어 된 시퀀스의 시작 부분 제어 된 시퀀스의 길이가 변경 되 면 변경할 수 있습니다.

### <a name="example"></a>예제

```cpp
// cliext_hash_multiset_begin.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_multiset<wchar_t> Myhash_multiset;
int main()
    {
    Myhash_multiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect first two items
    Myhash_multiset::iterator it = c1.begin();
    System::Console::WriteLine("*begin() = {0}", *it);
    System::Console::WriteLine("*++begin() = {0}", *++it);
    return (0);
    }
```

```Output
a b c
*begin() = a
*++begin() = b
```

## <a name="bucket_count"></a> hash_multiset:: bucket_count (STL/CLR)

버킷 수를 셉니다.

### <a name="syntax"></a>구문

```cpp
int bucket_count();
```

### <a name="remarks"></a>설명

멤버 함수는 현재 버킷 수를 반환 합니다. 해시 테이블의 크기를 결정 하는 데 사용할 수 있습니다.

### <a name="example"></a>예제

```cpp
// cliext_hash_multiset_bucket_count.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_multiset<wchar_t> Myhash_multiset;
int main()
    {
    Myhash_multiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect current parameters
    System::Console::WriteLine("bucket_count() = {0}", c1.bucket_count());
    System::Console::WriteLine("load_factor() = {0}", c1.load_factor());
    System::Console::WriteLine("max_load_factor() = {0}",
        c1.max_load_factor());
    System::Console::WriteLine();

    // change max_load_factor and redisplay
    c1.max_load_factor(0.25f);
    System::Console::WriteLine("bucket_count() = {0}", c1.bucket_count());
    System::Console::WriteLine("load_factor() = {0}", c1.load_factor());
    System::Console::WriteLine("max_load_factor() = {0}",
        c1.max_load_factor());
    System::Console::WriteLine();

    // rehash and redisplay
    c1.rehash(100);
    System::Console::WriteLine("bucket_count() = {0}", c1.bucket_count());
    System::Console::WriteLine("load_factor() = {0}", c1.load_factor());
    System::Console::WriteLine("max_load_factor() = {0}",
        c1.max_load_factor());
    return (0);
    }
```

```Output
a b c
bucket_count() = 16
load_factor() = 0.1875
max_load_factor() = 4

bucket_count() = 16
load_factor() = 0.1875
max_load_factor() = 0.25

bucket_count() = 128
load_factor() = 0.0234375
max_load_factor() = 0.25
```

## <a name="clear"></a> hash_multiset:: clear (STL/CLR)

모든 요소를 제거합니다.

### <a name="syntax"></a>구문

```cpp
void clear();
```

### <a name="remarks"></a>설명

멤버 함수는 효과적으로 호출한 [hash_multiset:: erase (STL/CLR)](../dotnet/hash-multiset-erase-stl-clr.md) `(` [hash_multiset:: begin (STL/CLR)](../dotnet/hash-multiset-begin-stl-clr.md) `(),` [hash_multiset:: end (STL/CLR) ](../dotnet/hash-multiset-end-stl-clr.md)`())`. 제어 되는 시퀀스 비어 있는지 확인 하는 데 사용할 수 있습니다.

### <a name="example"></a>예제

```cpp
// cliext_hash_multiset_clear.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_multiset<wchar_t> Myhash_multiset;
int main()
    {
    Myhash_multiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // clear the container and reinspect
    c1.clear();
    System::Console::WriteLine("size() = {0}", c1.size());

    // add elements and clear again
    c1.insert(L'a');
    c1.insert(L'b');

    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    c1.clear();
    System::Console::WriteLine("size() = {0}", c1.size());
    return (0);
    }
```

```Output
a b c
size() = 0
a b
size() = 0
```

## <a name="const_iterator"></a> hash_multiset:: const_iterator (STL/CLR)

제어되는 시퀀스에 대한 상수 반복기의 형식입니다.

### <a name="syntax"></a>구문

```cpp
typedef T2 const_iterator;
```

### <a name="remarks"></a>설명

이 형식은 지정 되지 않은 형식의 개체를 설명 `T2` 제어 되는 시퀀스의 상수 양방향 반복기로 사용할 수 있는 합니다.

### <a name="example"></a>예제

```cpp
// cliext_hash_multiset_const_iterator.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_multiset<wchar_t> Myhash_multiset;
int main()
    {
    Myhash_multiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display contents " a b c"
    Myhash_multiset::const_iterator cit = c1.begin();
    for (; cit != c1.end(); ++cit)
        System::Console::Write("{0} ", *cit);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="const_reference"></a> hash_multiset:: const_reference (STL/CLR)

요소에 대한 상수 참조의 형식입니다.

### <a name="syntax"></a>구문

```cpp
typedef value_type% const_reference;
```

### <a name="remarks"></a>설명

형식 요소에 대 한 상수 참조를 설명합니다.

### <a name="example"></a>예제

```cpp
// cliext_hash_multiset_const_reference.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_multiset<wchar_t> Myhash_multiset;
int main()
    {
    Myhash_multiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    Myhash_multiset::const_iterator cit = c1.begin();
    for (; cit != c1.end(); ++cit)
        {   // get a const reference to an element
        Myhash_multiset::const_reference cref = *cit;
        System::Console::Write("{0} ", cref);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="const_reverse_iterator"></a> hash_multiset:: const_reverse_iterator (STL/CLR)

제어 되는 시퀀스의 상수 역방향 반복기의 형식...

### <a name="syntax"></a>구문

```cpp
typedef T4 const_reverse_iterator;
```

### <a name="remarks"></a>설명

이 형식은 지정 되지 않은 형식의 개체를 설명 `T4` 제어 되는 시퀀스의 상수 역방향 반복기로 사용할 수 있는 합니다.

### <a name="example"></a>예제

```cpp
// cliext_hash_multiset_const_reverse_iterator.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_multiset<wchar_t> Myhash_multiset;
int main()
    {
    Myhash_multiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display contents " a b c" reversed
    Myhash_multiset::const_reverse_iterator crit = c1.rbegin();
    for (; crit != c1.rend(); ++crit)
        System::Console::Write("{0} ", *crit);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c b a
```

## <a name="count"></a> hash_multiset:: count (STL/CLR)

지정한 키와 일치하는 요소의 수를 찾습니다.

### <a name="syntax"></a>구문

```cpp
size_type count(key_type key);
```

#### <a name="parameters"></a>매개 변수

*key*<br/>
검색할 키 값입니다.

### <a name="remarks"></a>설명

멤버 함수는 동일 하 게 정렬 된 제어 된 시퀀스의 요소 수를 반환 *키*합니다. 지정된 된 키와 일치 하는 현재 제어 된 시퀀스의에서 요소 수를 확인 하려면 사용 합니다.

### <a name="example"></a>예제

```cpp
// cliext_hash_multiset_count.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_multiset<wchar_t> Myhash_multiset;
int main()
    {
    Myhash_multiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    System::Console::WriteLine("count(L'A') = {0}", c1.count(L'A'));
    System::Console::WriteLine("count(L'b') = {0}", c1.count(L'b'));
    System::Console::WriteLine("count(L'C') = {0}", c1.count(L'C'));
    return (0);
    }
```

```Output
a b c
count(L'A') = 0
count(L'b') = 1
count(L'C') = 0
```

## <a name="difference_type"></a> hash_multiset:: difference_type (STL/CLR)

두 요소 사이의 부호가 있는 거리의 형식입니다.

### <a name="syntax"></a>구문

```cpp
typedef int difference_type;
```

### <a name="remarks"></a>설명

형식 음수 수 있는 요소 수를 설명합니다.

### <a name="example"></a>예제

```cpp
// cliext_hash_multiset_difference_type.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_multiset<wchar_t> Myhash_multiset;
int main()
    {
    Myhash_multiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // compute positive difference
    Myhash_multiset::difference_type diff = 0;
    for (Myhash_multiset::iterator it = c1.begin(); it != c1.end(); ++it)
        ++diff;
    System::Console::WriteLine("end()-begin() = {0}", diff);

    // compute negative difference
    diff = 0;
    for (Myhash_multiset::iterator it = c1.end(); it != c1.begin(); --it)
        --diff;
    System::Console::WriteLine("begin()-end() = {0}", diff);
    return (0);
    }
```

```Output
a b c
end()-begin() = 3
begin()-end() = -3
```

## <a name="empty"></a> hash_multiset:: empty (STL/CLR)

요소가 있는지 여부를 테스트합니다.

### <a name="syntax"></a>구문

```cpp
bool empty();
```

### <a name="remarks"></a>설명

멤버 함수는 빈 제어되는 시퀀스에 대해 true를 반환합니다. 에 해당 하는 것 [hash_multiset:: size (STL/CLR)](../dotnet/hash-multiset-size-stl-clr.md)`() == 0`합니다. Hash_multiset이 비어 있는지 여부를 테스트 하려면 사용 합니다.

### <a name="example"></a>예제

```cpp
// cliext_hash_multiset_empty.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_multiset<wchar_t> Myhash_multiset;
int main()
    {
    Myhash_multiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    System::Console::WriteLine("size() = {0}", c1.size());
    System::Console::WriteLine("empty() = {0}", c1.empty());

    // clear the container and reinspect
    c1.clear();
    System::Console::WriteLine("size() = {0}", c1.size());
    System::Console::WriteLine("empty() = {0}", c1.empty());
    return (0);
    }
```

```Output
a b c
size() = 3
empty() = False
size() = 0
empty() = True
```

## <a name="end"></a> hash_multiset:: end (STL/CLR)

제어되는 시퀀스의 끝을 지정합니다.

### <a name="syntax"></a>구문

```cpp
iterator end();
```

### <a name="remarks"></a>설명

멤버 함수는 제어 된 시퀀스의 끝 바로 다음을 가리키는 양방향 반복기를 반환합니다. 제어 된 시퀀스의 끝을 지정 하는 반복기를 사용 하면 해당 상태 만들어지고 제어 된 시퀀스의 길이가 변경 되 면 변경 되지 않습니다.

### <a name="example"></a>예제

```cpp
// cliext_hash_multiset_end.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_multiset<wchar_t> Myhash_multiset;
int main()
    {
    Myhash_multiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect last two items
    Myhash_multiset::iterator it = c1.end();
    --it;
    System::Console::WriteLine("*-- --end() = {0}", *--it);
    System::Console::WriteLine("*--end() = {0}", *++it);
    return (0);
    }
```

```Output
a b c
*-- --end() = b
*--end() = c
```

## <a name="equal_range"></a> hash_multiset:: equal_range (STL/CLR)

지정된 키와 일치하는 범위를 찾습니다.

### <a name="syntax"></a>구문

```cpp
cliext::pair<iterator, iterator> equal_range(key_type key);
```

#### <a name="parameters"></a>매개 변수

*key*<br/>
검색할 키 값입니다.

### <a name="remarks"></a>설명

반복기의 쌍을 반환 하는 멤버 함수 `cliext::pair<iterator, iterator>(` [hash_multiset:: lower_bound (STL/CLR)](../dotnet/hash-multiset-lower-bound-stl-clr.md) `(key),` [hash_multiset:: upper_bound (STL/CLR)](../dotnet/hash-multiset-upper-bound-stl-clr.md)`(key))`합니다. 지정된 된 키와 일치 하는 제어 되는 시퀀스에서 현재 요소의 범위를 확인 하려면 사용 합니다.

### <a name="example"></a>예제

```cpp
// cliext_hash_multiset_equal_range.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_multiset<wchar_t> Myhash_multiset;
typedef Myhash_multiset::pair_iter_iter Pairii;
int main()
    {
    Myhash_multiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // display results of failed search
    Pairii pair1 = c1.equal_range(L'x');
    System::Console::WriteLine("equal_range(L'x') empty = {0}",
        pair1.first == pair1.second);

    // display results of successful search
    pair1 = c1.equal_range(L'b');
    for (; pair1.first != pair1.second; ++pair1.first)
        System::Console::Write("{0} ", *pair1.first);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
equal_range(L'x') empty = True
b
```

## <a name="erase"></a> hash_multiset:: erase (STL/CLR)

지정된 위치에 있는 요소를 제거합니다.

### <a name="syntax"></a>구문

```cpp
iterator erase(iterator where);
iterator erase(iterator first, iterator last);
bool erase(key_type key)
```

#### <a name="parameters"></a>매개 변수

*first*<br/>
지울 범위의 시작입니다.

*key*<br/>
지울 키 값입니다.

*last*<br/>
지울 범위의 끝입니다.

*where*<br/>
지울 요소입니다.

### <a name="remarks"></a>설명

가 가리키는 제어 되는 시퀀스의 요소를 제거 하는 첫 번째 멤버 함수 *여기서*를 제거 하는 요소 뒤에 남은 첫 번째 요소를 지정 하는 반복기를 반환 합니다. 또는 [hash_multiset:: end ( STL/CLR)](../dotnet/hash-multiset-end-stl-clr.md) `()` 이러한 요소가 없는 경우. 단일 요소를 제거 하려면 사용 합니다.

두 번째 멤버 함수 범위에서 제어 된 시퀀스의 요소를 제거 합니다. [`first`, `last`), 제거 된 요소 뒤에 남은 첫 번째 요소를 지정 하는 반복기를 반환 합니다. 또는 `end()` 이러한 요소가 없는 경우 존재 하 고... 0 개 이상의 연속 요소를 제거 하려면 사용 합니다.

키에 동일한 순서 제어 된 시퀀스의 모든 요소를 제거 하는 세 번째 멤버 함수를 *키*, 제거 된 요소의 개수를 반환 합니다. 제거 하 고 지정된 된 키와 일치 하는 모든 요소를 계산 하는 데 사용할 수 있습니다.

각 요소 지우기 제어 되는 시퀀스의 요소 수 로그에 비례한 시간을 사용합니다.

### <a name="example"></a>예제

```cpp
// cliext_hash_multiset_erase.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_multiset<wchar_t> Myhash_multiset;
int main()
    {
    Myhash_multiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // erase an element and reinspect
    System::Console::WriteLine("erase(begin()) = {0}",
        *c1.erase(c1.begin()));

    // add elements and display " b c d e"
    c1.insert(L'd');
    c1.insert(L'e');
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // erase all but end
    Myhash_multiset::iterator it = c1.end();
    System::Console::WriteLine("erase(begin(), end()-1) = {0}",
        *c1.erase(c1.begin(), --it));
    System::Console::WriteLine("size() = {0}", c1.size());
    return (0);
    }
```

```Output
a b c
erase(begin()) = b
b c d e
erase(begin(), end()-1) = e
size() = 1
```

## <a name="find"></a> hash_multiset:: find (STL/CLR)

지정된 키와 일치하는 요소를 찾습니다.

### <a name="syntax"></a>구문

```cpp
iterator find(key_type key);
```

#### <a name="parameters"></a>매개 변수

*key*<br/>
검색할 키 값입니다.

### <a name="remarks"></a>설명

사용 하 여 해당 순서 제어 된 시퀀스의 요소를 하나 이상 있으면 *키*, 멤버 함수는 이러한 요소 중 하나를 지정 하는 반복기를 반환, 그렇지 않으면 반환 [hash_multiset:: end (STL/CLR) ](../dotnet/hash-multiset-end-stl-clr.md)`()`. 지정된 된 키와 일치 하는 제어 된 시퀀스의 요소를 현재 찾으려고 사용할 수 있습니다.

### <a name="example"></a>예제

```cpp
// cliext_hash_multiset_find.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_multiset<wchar_t> Myhash_multiset;
int main()
    {
    Myhash_multiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    System::Console::WriteLine("find {0} = {1}",
        L'A', c1.find(L'A') != c1.end());
    System::Console::WriteLine("find {0} = {1}",
        L'b', *c1.find(L'b'));
    System::Console::WriteLine("find {0} = {1}",
        L'C', c1.find(L'C') != c1.end());
    return (0);
    }
```

```Output
a b c
find A = False
find b = b
find C = False
```

## <a name="generic_container"></a> hash_multiset:: generic_container (STL/CLR)

컨테이너에 대 한 제네릭 인터페이스의 형식입니다.

### <a name="syntax"></a>구문

```cpp
typedef Microsoft::VisualC::StlClr::
    IHash<GKey, GValue>
    generic_container;
```

### <a name="remarks"></a>설명

형식은이 템플릿 컨테이너 클래스에 대 한 제네릭 인터페이스를 설명합니다.

### <a name="example"></a>예제

```cpp
// cliext_hash_multiset_generic_container.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_multiset<wchar_t> Myhash_multiset;
int main()
    {
    Myhash_multiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct a generic container
    Myhash_multiset::generic_container^ gc1 = %c1;
    for each (wchar_t elem in gc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // modify generic and display original
    gc1->insert(L'd');
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // modify original and display generic
    c1.insert(L'e');
    for each (wchar_t elem in gc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
a b c
a b c d
a b c d e
```

## <a name="generic_iterator"></a> hash_multiset:: generic_iterator (STL/CLR)

컨테이너에 대 한 제네릭 인터페이스를 사용 하 여 사용에 대 한 반복기의 형식입니다.

### <a name="syntax"></a>구문

```cpp
typedef Microsoft::VisualC::StlClr::Generic::
    ContainerBidirectionalIterator<generic_value>
    generic_iterator;
```

### <a name="remarks"></a>설명

형식에이 템플릿 컨테이너 클래스에 대 한 제네릭 인터페이스를 사용 하 여 사용할 수 있는 일반 반복기를 설명 합니다.

### <a name="example"></a>예제

```cpp
// cliext_hash_multiset_generic_iterator.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_multiset<wchar_t> Myhash_multiset;
int main()
    {
    Myhash_multiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct a generic container
    Myhash_multiset::generic_container^ gc1 = %c1;
    for each (wchar_t elem in gc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // get an element and display it
    Myhash_multiset::generic_iterator gcit = gc1->begin();
    Myhash_multiset::generic_value gcval = *gcit;
    System::Console::WriteLine("{0} ", gcval);
    return (0);
    }
```

```Output
a b c
a b c
a
```

## <a name="generic_reverse_iterator"></a> hash_multiset:: generic_reverse_iterator (STL/CLR)

컨테이너에 대 한 제네릭 인터페이스를 사용 하 여 사용에 대 한 역방향 반복기의 형식입니다.

### <a name="syntax"></a>구문

```cpp
typedef Microsoft::VisualC::StlClr::Generic::
    ReverseRandomAccessIterator<generic_value>
    generic_reverse_iterator;
```

### <a name="remarks"></a>설명

형식에는이 템플릿 컨테이너 클래스에 대 한 제네릭 인터페이스를 사용 하 여 사용할 수 있는 제네릭 역방향 반복기를 설명 합니다.

### <a name="example"></a>예제

```cpp
// cliext_hash_multiset_generic_reverse_iterator.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_multiset<wchar_t> Myhash_multiset;
int main()
    {
    Myhash_multiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct a generic container
    Myhash_multiset::generic_container^ gc1 = %c1;
    for each (wchar_t elem in gc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // get an element and display it
    Myhash_multiset::generic_reverse_iterator gcit = gc1->rbegin();
    Myhash_multiset::generic_value gcval = *gcit;
    System::Console::WriteLine("{0} ", gcval);
    return (0);
    }
```

```Output
a b c
a b c
c
```

## <a name="generic_value"></a> hash_multiset:: generic_value (STL/CLR)

컨테이너에 대 한 제네릭 인터페이스를 사용 하 여 사용에 대 한 요소의 형식입니다.

### <a name="syntax"></a>구문

```cpp
typedef GValue generic_value;
```

### <a name="remarks"></a>설명

이 형식은 형식의 개체를 설명 `GValue` 는이 템플릿 컨테이너 클래스에 대 한 제네릭 인터페이스를 사용 하 여 사용 하 여 저장 된 요소 값에 설명 합니다.

### <a name="example"></a>예제

```cpp
// cliext_hash_multiset_generic_value.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_multiset<wchar_t> Myhash_multiset;
int main()
    {
    Myhash_multiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct a generic container
    Myhash_multiset::generic_container^ gc1 = %c1;
    for each (wchar_t elem in gc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // get an element and display it
    Myhash_multiset::generic_iterator gcit = gc1->begin();
    Myhash_multiset::generic_value gcval = *gcit;
    System::Console::WriteLine("{0} ", gcval);
    return (0);
    }
```

```Output
a b c
a b c
a
```

## <a name="hash_delegate"></a> hash_multiset:: hash_delegate (STL/CLR)

지정된 키와 일치하는 요소를 찾습니다.

### <a name="syntax"></a>구문

```cpp
hasher^ hash_delegate();
```

### <a name="remarks"></a>설명

멤버 함수는 키 값을 정수로 변환 하는 데 사용 하는 대리자를 반환 합니다. 키를 해시 하는 데 사용할 수 있습니다.

### <a name="example"></a>예제

```cpp
// cliext_hash_multiset_hash_delegate.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_multiset<wchar_t> Myhash_multiset;
int main()
    {
    Myhash_multiset c1;
    Myhash_multiset::hasher^ myhash = c1.hash_delegate();

    System::Console::WriteLine("hash(L'a') = {0}", myhash(L'a'));
    System::Console::WriteLine("hash(L'b') = {0}", myhash(L'b'));
    return (0);
    }
```

```Output
hash(L'a') = 1616896120
hash(L'b') = 570892832
```

## <a name="hash_multiset"></a> hash_multiset:: hash_multiset (STL/CLR)

컨테이너 개체를 만듭니다.

### <a name="syntax"></a>구문

```cpp
hash_multiset();
explicit hash_multiset(key_compare^ pred);
hash_multiset(key_compare^ pred, hasher^ hashfn);
hash_multiset(hash_multiset<Key>% right);
hash_multiset(hash_multiset<Key>^ right);
template<typename InIter>
    hash_multiset(InIter first, InIter last);
template<typename InIter>
    hash_multiset(InIter first, InIter last,
        key_compare^ pred);
template<typename InIter>
    hash_multiset(InIter first, InIter last,
        key_compare^ pred, hasher^ hashfn);
hash_multiset(System::Collections::Generic::IEnumerable<GValue>^ right);
hash_multiset(System::Collections::Generic::IEnumerable<GValue>^ right,
    key_compare^ pred);
hash_multiset(System::Collections::Generic::IEnumerable<GValue>^ right,
    key_compare^ pred, hasher^ hashfn);
```

#### <a name="parameters"></a>매개 변수

*first*<br/>
삽입할 범위의 시작입니다.

*hashfn*<br/>
해시 버킷에 매핑 키에 대 한 기능입니다.

*last*<br/>
삽입할 범위의 끝입니다.

*pred*<br/>
제어 되는 시퀀스에 대 한 조건자를 정렬 합니다.

*right*<br/>
삽입할 개체 또는 범위입니다.

### <a name="remarks"></a>설명

생성자:

`hash_multiset();`

조건자 순서 기본값을 사용 하 여 아무런 요소도 갖고 제어 되는 시퀀스 초기화 `key_compare()`, 및 기본 해시 함수를 사용 하 여 합니다. 기본 순서 조건자 및 해시 함수는 빈 초기 제어 되는 시퀀스를 지정 하는 데 사용할 수 있습니다.

생성자:

`explicit hash_multiset(key_compare^ pred);`

순서 지정 조건자를 사용 하 여 요소가 없는 제어 되는 시퀀스를 초기화 *pred*, 및 기본 해시 함수를 사용 하 여 합니다. 지정된 된 순서 지정 조건자와 기본 해시 함수는 빈 초기 제어 되는 시퀀스를 지정 하는 데 사용할 수 있습니다.

생성자:

`hash_multiset(key_compare^ pred, hasher^ hashfn);`

순서 지정 조건자를 사용 하 여 요소가 없는 제어 되는 시퀀스를 초기화 *pred*, 및 해시 함수를 사용 하 여 *hashfn*합니다. 지정 된 순서 지정 조건자 및 해시 함수를 사용 하 여 빈 초기 제어 된 시퀀스를 지정 하는 데 사용할 수 있습니다.

생성자:

`hash_multiset(hash_multiset<Key>% right);`

시퀀스를 사용 하 여 제어 되는 시퀀스를 초기화 합니다. [`right.begin()`, `right.end()`), 조건자에서 정렬 기본값 및 기본 해시 함수를 사용 하 여 합니다. Hash_multiset 개체에 의해 제어 되는 시퀀스의 복사본 인 초기 제어 된 시퀀스를 지정 하려면 사용할 *오른쪽*, 기본 순서 지정 조건자와 해시 함수입니다.

생성자:

`hash_multiset(hash_multiset<Key>^ right);`

시퀀스를 사용 하 여 제어 되는 시퀀스를 초기화 합니다. [`right->begin()`, `right->end()`), 조건자에서 정렬 기본값 및 기본 해시 함수를 사용 하 여 합니다. Hash_multiset 개체에 의해 제어 되는 시퀀스의 복사본 인 초기 제어 된 시퀀스를 지정 하려면 사용할 *오른쪽*, 기본 순서 지정 조건자와 해시 함수입니다.

생성자:

`template<typename InIter> hash_multiset(InIter first, InIter last);`

시퀀스를 사용 하 여 제어 되는 시퀀스를 초기화 합니다. [`first`, `last`), 조건자에서 정렬 기본값 및 기본 해시 함수를 사용 하 여 합니다. 사용 하 여 조건자 및 해시 함수를 정렬 기본값을 사용 하 여 제어 되는 시퀀스를 다른 시퀀스의 복사본을 만듭니다.

생성자:

`template<typename InIter> hash_multiset(InIter first, InIter last, key_compare^ pred);`

시퀀스를 사용 하 여 제어 되는 시퀀스를 초기화 합니다. [`first`, `last`), 순서 지정 조건자를 사용 하 여 *pred*, 및 기본 해시 함수를 사용 하 여 합니다. 사용 하 여이 제어 되는 지정된 된 순서 지정 조건자 및 기본 해시 함수를 사용 하 여 다른 시퀀스의 복사본을 만듭니다.

생성자:

`template<typename InIter> hash_multiset(InIter first, InIter last, key_compare^ pred, hasher^ hashfn);`

시퀀스를 사용 하 여 제어 되는 시퀀스를 초기화 합니다. [`first`, `last`), 순서 지정 조건자를 사용 하 여 *pred*, 및 해시 함수를 사용 하 여 *hashfn*합니다. 사용 하 여이 제어 되는 지정 된 순서 지정 조건자 및 해시 함수를 사용 하 여 다른 시퀀스의 복사본을 만듭니다.

생성자:

`hash_multiset(System::Collections::Generic::IEnumerable<Key>^ right);`

열거자에서 지정 된 시퀀스를 사용 하 여 제어 되는 시퀀스를 초기화 *오른쪽*, 조건자에서 정렬 기본값 및 기본 해시 함수를 사용 하 여 합니다. 사용 하 여 제어 되는 기본 순서 조건자 및 해시 함수를 사용 하 여 열거자를 설명 하는 다른 시퀀스의 복사본을 만듭니다.

생성자:

`hash_multiset(System::Collections::Generic::IEnumerable<Key>^ right, key_compare^ pred);`

열거자에서 지정 된 시퀀스를 사용 하 여 제어 되는 시퀀스를 초기화 *오른쪽*, 순서 지정 조건자를 사용 하 여 *pred*, 및 기본 해시 함수를 사용 하 여 합니다. 사용 하 여 제어 되는 시퀀스에서 지정 된 순서 지정 조건자 및 기본 해시 함수를 사용 하 여 열거자를 설명 하는 다른 시퀀스의 복사본을 만듭니다.

생성자:

`hash_multiset(System::Collections::Generic::IEnumerable<Key>^ right, key_compare^ pred, hasher^ hashfn);`

열거자에서 지정 된 시퀀스를 사용 하 여 제어 되는 시퀀스를 초기화 *오른쪽*, 순서 지정 조건자를 사용 하 여 *pred*, 및 해시 함수를 사용 하 여 *hashfn*합니다. 사용 하 여 제어 되는 시퀀스에서 지정 된 순서 지정 조건자 및 해시 함수를 사용 하 여 열거자를 설명 하는 다른 시퀀스의 복사본을 만듭니다.

### <a name="example"></a>예제

```cpp
// cliext_hash_multiset_construct.cpp
// compile with: /clr
#include <cliext/hash_set>

int myfun(wchar_t key)
    { // hash a key
    return (key ^ 0xdeadbeef);
    }

typedef cliext::hash_multiset<wchar_t> Myhash_multiset;
int main()
    {
// construct an empty container
    Myhash_multiset c1;
    System::Console::WriteLine("size() = {0}", c1.size());

    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct with an ordering rule
    Myhash_multiset c2 = cliext::greater_equal<wchar_t>();
    System::Console::WriteLine("size() = {0}", c2.size());

    c2.insert(c1.begin(), c1.end());
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct with an ordering rule and hash function
    Myhash_multiset c2h(cliext::greater_equal<wchar_t>(),
        gcnew Myhash_multiset::hasher(&myfun));
    System::Console::WriteLine("size() = {0}", c2h.size());

    c2h.insert(c1.begin(), c1.end());
    for each (wchar_t elem in c2h)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    System::Console::WriteLine();

    // construct with an iterator range
    Myhash_multiset c3(c1.begin(), c1.end());
    for each (wchar_t elem in c3)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct with an iterator range and an ordering rule
    Myhash_multiset c4(c1.begin(), c1.end(),
        cliext::greater_equal<wchar_t>());
    for each (wchar_t elem in c4)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct with an iterator range and an ordering rule and hash function
    Myhash_multiset c4h(c1.begin(), c1.end(),
        cliext::greater_equal<wchar_t>(),
        gcnew Myhash_multiset::hasher(&myfun));
    for each (wchar_t elem in c4h)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    System::Console::WriteLine();

    // construct with an enumeration
    Myhash_multiset c5(   // NOTE: cast is not needed
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3);
    for each (wchar_t elem in c5)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct with an enumeration and an ordering rule
    Myhash_multiset c6(   // NOTE: cast is not needed
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3,
            cliext::greater_equal<wchar_t>());
    for each (wchar_t elem in c6)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct with an enumeration and an ordering rule and hash function
    Myhash_multiset c6h(   // NOTE: cast is not needed
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3,
            cliext::greater_equal<wchar_t>(),
                gcnew Myhash_multiset::hasher(&myfun));
    for each (wchar_t elem in c6h)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    System::Console::WriteLine();

    // construct from a generic container
    Myhash_multiset c7(c4);
    for each (wchar_t elem in c7)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct by copying another container
    Myhash_multiset c8(%c3);
    for each (wchar_t elem in c8)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
size() = 0
a b c
size() = 0
a b c
size() = 0
c b a

a b c
a b c
c b a

a b c
a b c
c b a

a b c
a b c
```

## <a name="hasher"></a> hash_multiset:: hasher (STL/CLR)

키의 해시 대리자입니다.

### <a name="syntax"></a>구문

```cpp
Microsoft::VisualC::StlClr::UnaryDelegate<GKey, int>
    hasher;
```

### <a name="remarks"></a>설명

이 형식은 키 값을 정수로 변환 하는 대리자를 설명 합니다.

### <a name="example"></a>예제

```cpp
// cliext_hash_multiset_hasher.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_multiset<wchar_t> Myhash_multiset;
int main()
    {
    Myhash_multiset c1;
    Myhash_multiset::hasher^ myhash = c1.hash_delegate();

    System::Console::WriteLine("hash(L'a') = {0}", myhash(L'a'));
    System::Console::WriteLine("hash(L'b') = {0}", myhash(L'b'));
    return (0);
    }
```

```Output
hash(L'a') = 1616896120
hash(L'b') = 570892832
```

## <a name="insert"></a> hash_multiset:: insert (STL/CLR)

요소를 추가합니다.

### <a name="syntax"></a>구문

```cpp
iterator insert(value_type val);
iterator insert(iterator where, value_type val);
template<typename InIter>
    void insert(InIter first, InIter last);
void insert(System::Collections::Generic::IEnumerable<value_type>^ right);
```

#### <a name="parameters"></a>매개 변수

*first*<br/>
삽입할 범위의 시작입니다.

*last*<br/>
삽입할 범위의 끝입니다.

*right*<br/>
삽입할 열거형입니다.

*val*<br/>
삽입할 키 값입니다.

*where*<br/>
(힌트에만 해당)를 삽입할 컨테이너에서 위치입니다.

### <a name="remarks"></a>설명

각 멤버 함수는 나머지 피연산자에서 지정 된 시퀀스를 삽입 합니다.

첫 번째 멤버 함수는 값을 사용 하 여 요소를 삽입 *val*, 새로 삽입된 된 요소를 지정 하는 반복기를 반환 합니다. 단일 요소를 삽입 하는 데 사용할 수 있습니다.

두 번째 멤버 함수는 값을 사용 하 여 요소를 삽입 *val*를 사용 하 여 *여기서* (성능을 향상 시키기 위해) 힌트를 새로 삽입된 된 요소를 지정 하는 반복기를 반환 합니다. 알고 있는 요소에 인접 한 될 수 있는 단일 요소를 삽입 하는 데 사용할 수 있습니다.

세 번째 멤버 함수는 시퀀스를 삽입 합니다. [`first`, `last`). 다른 시퀀스에서 복사 된 0 개 이상의 요소를 삽입 하는 데 사용할 수 있습니다.

로 지정 된 시퀀스를 삽입 하는 네 번째 멤버 함수는 *오른쪽*합니다. 열거자에서 설명 하는 시퀀스를 삽입 하는 데 사용할 수 있습니다.

제어 되는 시퀀스의 요소 수 로그에 비례한 시간을 사용 하는 각 요소를 삽입 합니다. 그러나 삽입에서에서 발생할 수 있습니다 분할 상환된 상수 시간 삽입 지점에 인접 한 요소를 지정 하는 힌트를 지정 합니다.

### <a name="example"></a>예제

```cpp
// cliext_hash_multiset_insert.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_multiset<wchar_t> Myhash_multiset;
int main()
    {
    Myhash_multiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // insert a single value, unique and duplicate
    System::Console::WriteLine("insert(L'x') = {0}",
        *c1.insert(L'x'));

    System::Console::WriteLine("insert(L'b') = {0}",
        *c1.insert(L'b'));

    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // insert a single value with hint
    System::Console::WriteLine("insert(begin(), L'y') = {0}",
        *c1.insert(c1.begin(), L'y'));
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // insert an iterator range
    Myhash_multiset c2;
    Myhash_multiset::iterator it = c1.end();
    c2.insert(c1.begin(), --it);
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // insert an enumeration
    Myhash_multiset c3;
    c3.insert(   // NOTE: cast is not needed
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c1);
    for each (wchar_t elem in c3)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
insert(L'x') = x
insert(L'b') = b
a b b c x
insert(begin(), L'y') = y
a b b c x y
a b b c x
a b b c x y
```

## <a name="iterator"></a> hash_multiset:: iterator (STL/CLR)

제어되는 시퀀스에 대한 반복기의 형식입니다.

### <a name="syntax"></a>구문

```cpp
typedef T1 iterator;
```

### <a name="remarks"></a>설명

이 형식은 지정 되지 않은 형식의 개체를 설명 `T1` 제어 되는 시퀀스는 양방향 반복기로 사용할 수 있는 합니다.

### <a name="example"></a>예제

```cpp
// cliext_hash_multiset_iterator.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_multiset<wchar_t> Myhash_multiset;
int main()
    {
    Myhash_multiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display contents " a b c"
    Myhash_multiset::iterator it = c1.begin();
    for (; it != c1.end(); ++it)
        System::Console::Write("{0} ", *it);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="key_comp"></a> hash_multiset:: key_comp (STL/CLR)

두 개의 키에 대 한 순서 지정 대리자를 복사합니다.

### <a name="syntax"></a>구문

```cpp
key_compare^key_comp();
```

### <a name="remarks"></a>설명

멤버 함수는 제어 되는 시퀀스를 정렬 하는 데 사용 하는 순서 지정 대리자를 반환 합니다. 두 키 비교에 사용할 수 있습니다.

### <a name="example"></a>예제

```cpp
// cliext_hash_multiset_key_comp.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_multiset<wchar_t> Myhash_multiset;
int main()
    {
    Myhash_multiset c1;
    Myhash_multiset::key_compare^ kcomp = c1.key_comp();

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        kcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        kcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        kcomp(L'b', L'a'));
    System::Console::WriteLine();

    // test a different ordering rule
    Myhash_multiset c2 = cliext::greater<wchar_t>();
    kcomp = c2.key_comp();

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        kcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        kcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        kcomp(L'b', L'a'));
    return (0);
    }
```

```Output
compare(L'a', L'a') = True
compare(L'a', L'b') = True
compare(L'b', L'a') = False

compare(L'a', L'a') = False
compare(L'a', L'b') = False
compare(L'b', L'a') = True
```

## <a name="key_compare"></a> hash_multiset:: key_compare (STL/CLR)

두 키의 순서 지정 대리자입니다.

### <a name="syntax"></a>구문

```cpp
Microsoft::VisualC::StlClr::BinaryDelegate<GKey, GKey, bool>
    key_compare;
```

### <a name="remarks"></a>설명

형식은 키 인수의 순서를 결정 하는 대리자에 대 한 동의어입니다.

### <a name="example"></a>예제

```cpp
// cliext_hash_multiset_key_compare.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_multiset<wchar_t> Myhash_multiset;
int main()
    {
    Myhash_multiset c1;
    Myhash_multiset::key_compare^ kcomp = c1.key_comp();

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        kcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        kcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        kcomp(L'b', L'a'));
    System::Console::WriteLine();

    // test a different ordering rule
    Myhash_multiset c2 = cliext::greater<wchar_t>();
    kcomp = c2.key_comp();

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        kcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        kcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        kcomp(L'b', L'a'));
    return (0);
    }
```

```Output
compare(L'a', L'a') = True
compare(L'a', L'b') = True
compare(L'b', L'a') = False

compare(L'a', L'a') = False
compare(L'a', L'b') = False
compare(L'b', L'a') = True
```

## <a name="key_type"></a> hash_multiset:: key_type (STL/CLR)

정렬 키의 형식입니다.

### <a name="syntax"></a>구문

```cpp
typedef Key key_type;
```

### <a name="remarks"></a>설명

형식은 템플릿 매개 변수에 대 한 동의어 *키*합니다.

### <a name="example"></a>예제

```cpp
// cliext_hash_multiset_key_type.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_multiset<wchar_t> Myhash_multiset;
int main()
    {
    Myhash_multiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display contents " a b c" using key_type
    for (Myhash_multiset::iterator it = c1.begin(); it != c1.end(); ++it)
        {   // store element in key_type object
        Myhash_multiset::key_type val = *it;

        System::Console::Write("{0} ", val);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="load_factor"></a> hash_multiset:: load_factor (STL/CLR)

버킷당 평균 요소 수를 계산합니다.

### <a name="syntax"></a>구문

```cpp
float load_factor();
```

### <a name="remarks"></a>설명

멤버 함수는 반환 `(float)` [hash_multiset:: size (STL/CLR)](../dotnet/hash-multiset-size-stl-clr.md) `() /` [hash_multiset:: bucket_count (STL/CLR)](../dotnet/hash-multiset-bucket-count-stl-clr.md)`()`합니다. 평균 버킷 크기를 결정 하는 데 사용할 수 있습니다.

### <a name="example"></a>예제

```cpp
// cliext_hash_multiset_load_factor.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_multiset<wchar_t> Myhash_multiset;
int main()
    {
    Myhash_multiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect current parameters
    System::Console::WriteLine("bucket_count() = {0}", c1.bucket_count());
    System::Console::WriteLine("load_factor() = {0}", c1.load_factor());
    System::Console::WriteLine("max_load_factor() = {0}",
        c1.max_load_factor());
    System::Console::WriteLine();

    // change max_load_factor and redisplay
    c1.max_load_factor(0.25f);
    System::Console::WriteLine("bucket_count() = {0}", c1.bucket_count());
    System::Console::WriteLine("load_factor() = {0}", c1.load_factor());
    System::Console::WriteLine("max_load_factor() = {0}",
        c1.max_load_factor());
    System::Console::WriteLine();

    // rehash and redisplay
    c1.rehash(100);
    System::Console::WriteLine("bucket_count() = {0}", c1.bucket_count());
    System::Console::WriteLine("load_factor() = {0}", c1.load_factor());
    System::Console::WriteLine("max_load_factor() = {0}",
        c1.max_load_factor());
    return (0);
    }
```

```Output
a b c
bucket_count() = 16
load_factor() = 0.1875
max_load_factor() = 4

bucket_count() = 16
load_factor() = 0.1875
max_load_factor() = 0.25

bucket_count() = 128
load_factor() = 0.0234375
max_load_factor() = 0.25
```

## <a name="lower_bound"></a> hash_multiset:: lower_bound (STL/CLR)

지정된 된 키와 일치 하는 범위의 시작 부분을 찾습니다.

### <a name="syntax"></a>구문

```cpp
iterator lower_bound(key_type key);
```

#### <a name="parameters"></a>매개 변수

*key*<br/>
검색할 키 값입니다.

### <a name="remarks"></a>설명

첫 번째 요소를 결정 하는 멤버 함수 `X` 동일한 버킷으로 해시 되는 제어 된 시퀀스의 *키* 과 순서가 있고 *키*합니다. 이러한 요소가 없으면 반환 [hash_multiset:: end (STL/CLR)](../dotnet/hash-multiset-end-stl-clr.md)`()`; 그렇지 않으면 지정 하는 반복기를 반환 `X`합니다. 지정된 된 키와 일치 하는 제어 된 시퀀스의 요소 시퀀스의 시작 부분을 현재 찾으려고 사용할 수 있습니다.

### <a name="example"></a>예제

```cpp
// cliext_hash_multiset_lower_bound.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_multiset<wchar_t> Myhash_multiset;
int main()
    {
    Myhash_multiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    System::Console::WriteLine("lower_bound(L'x')==end() = {0}",
        c1.lower_bound(L'x') == c1.end());

    System::Console::WriteLine("*lower_bound(L'a') = {0}",
        *c1.lower_bound(L'a'));
    System::Console::WriteLine("*lower_bound(L'b') = {0}",
        *c1.lower_bound(L'b'));
    return (0);
    }
```

```Output
a b c
lower_bound(L'x')==end() = True
*lower_bound(L'a') = a
*lower_bound(L'b') = b
```

## <a name="make_value"></a> hash_multiset:: make_value (STL/CLR)

값 개체를 생성합니다.

### <a name="syntax"></a>구문

```cpp
static value_type make_value(key_type key);
```

#### <a name="parameters"></a>매개 변수

*key*<br/>
사용할 키 값입니다.

### <a name="remarks"></a>설명

멤버 함수가 반환 하는 `value_type` 키를 가진 개체 *키*합니다. 적합 한 몇 가지 다른 멤버 함수를 사용 하 여 사용 하 여 개체를 작성 하는 데 사용할 수 있습니다.

### <a name="example"></a>예제

```cpp
// cliext_hash_multiset_make_value.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_multiset<wchar_t> Myhash_multiset;
int main()
    {
    Myhash_multiset c1;
    c1.insert(Myhash_multiset::make_value(L'a'));
    c1.insert(Myhash_multiset::make_value(L'b'));
    c1.insert(Myhash_multiset::make_value(L'c'));

    // display contents " a b c"
    for each (Myhash_multiset::value_type elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="max_load_factor"></a> hash_multiset:: max_load_factor (STL/CLR)

버킷당 최대 요소 수를 가져오거나 설정합니다.

### <a name="syntax"></a>구문

```cpp
float max_load_factor();
void max_load_factor(float new_factor);
```

#### <a name="parameters"></a>매개 변수

*new_factor*<br/>
새 최대값 저장 하는 요소를 로드 합니다.

### <a name="remarks"></a>설명

첫 번째 멤버 함수는 현재 저장 된 최대 로드 비율을 반환합니다. 최대 평균 버킷 크기를 결정 하는 데 사용할 수 있습니다.

두 번째 멤버 함수는 사용 하 여 저장소 최대 로드 비율을 대체 *new_factor*합니다. 자동 해싱하여 후속 삽입 될 때까지 발생합니다.

### <a name="example"></a>예제

```cpp
// cliext_hash_multiset_max_load_factor.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_multiset<wchar_t> Myhash_multiset;
int main()
    {
    Myhash_multiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect current parameters
    System::Console::WriteLine("bucket_count() = {0}", c1.bucket_count());
    System::Console::WriteLine("load_factor() = {0}", c1.load_factor());
    System::Console::WriteLine("max_load_factor() = {0}",
        c1.max_load_factor());
    System::Console::WriteLine();

    // change max_load_factor and redisplay
    c1.max_load_factor(0.25f);
    System::Console::WriteLine("bucket_count() = {0}", c1.bucket_count());
    System::Console::WriteLine("load_factor() = {0}", c1.load_factor());
    System::Console::WriteLine("max_load_factor() = {0}",
        c1.max_load_factor());
    System::Console::WriteLine();

    // rehash and redisplay
    c1.rehash(100);
    System::Console::WriteLine("bucket_count() = {0}", c1.bucket_count());
    System::Console::WriteLine("load_factor() = {0}", c1.load_factor());
    System::Console::WriteLine("max_load_factor() = {0}",
        c1.max_load_factor());
    return (0);
    }
```

```Output
a b c
bucket_count() = 16
load_factor() = 0.1875
max_load_factor() = 4

bucket_count() = 16
load_factor() = 0.1875
max_load_factor() = 0.25

bucket_count() = 128
load_factor() = 0.0234375
max_load_factor() = 0.25
```

## <a name="op"></a> hash_multiset:: operator = (STL/CLR)

제어되는 시퀀스를 바꿉니다.

### <a name="syntax"></a>구문

```cpp
hash_multiset<Key>% operator=(hash_multiset<Key>% right);
```

#### <a name="parameters"></a>매개 변수

*right*<br/>
복사할 컨테이너입니다.

### <a name="remarks"></a>설명

멤버 연산자 복사본 *오른쪽* 개체를 반환 `*this`합니다. 제어 되는 시퀀스에서 제어 된 시퀀스의 복사본으로 대체 하는 데 사용할 있습니다 *오른쪽*합니다.

### <a name="example"></a>예제

```cpp
// cliext_hash_multiset_operator_as.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_multiset<wchar_t> Myhash_multiset;
int main()
    {
    Myhash_multiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display contents " a b c"
    for each (Myhash_multiset::value_type elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // assign to a new container
    Myhash_multiset c2;
    c2 = c1;
// display contents " a b c"
    for each (Myhash_multiset::value_type elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
a b c
```

## <a name="rbegin"></a> hash_multiset:: rbegin (STL/CLR)

제어되는 역방향 시퀀스의 시작을 지정합니다.

### <a name="syntax"></a>구문

```cpp
reverse_iterator rbegin();
```

### <a name="remarks"></a>설명

멤버 함수는 제어 된 시퀀스 또는 빈 시퀀스의 시작 부분 바로 뒤의 마지막 요소를 지정 하는 역방향 반복기를 반환 합니다. 따라서 지정 된 `beginning` 역방향 시퀀스의 합니다. 지정 하는 반복기를 사용 하면는 `current` 제어 된 시퀀스를 역순으로 표시 되지만 해당 상태에 대 한 부분 제어 된 시퀀스의 길이가 변경 되 면 변경할 수 있습니다.

### <a name="example"></a>예제

```cpp
// cliext_hash_multiset_rbegin.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_multiset<wchar_t> Myhash_multiset;
int main()
    {
    Myhash_multiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect first two items in reversed sequence
    Myhash_multiset::reverse_iterator rit = c1.rbegin();
    System::Console::WriteLine("*rbegin() = {0}", *rit);
    System::Console::WriteLine("*++rbegin() = {0}", *++rit);
    return (0);
    }
```

```Output
a b c
*rbegin() = c
*++rbegin() = b
```

## <a name="reference"></a> hash_multiset:: reference (STL/CLR)

요소에 대한 참조의 형식입니다.

### <a name="syntax"></a>구문

```cpp
typedef value_type% reference;
```

### <a name="remarks"></a>설명

형식 요소에 대 한 참조를 설명합니다.

### <a name="example"></a>예제

```cpp
// cliext_hash_multiset_reference.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_multiset<wchar_t> Myhash_multiset;
int main()
    {
    Myhash_multiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    Myhash_multiset::iterator it = c1.begin();
    for (; it != c1.end(); ++it)
        {   // get a reference to an element
        Myhash_multiset::reference ref = *it;
        System::Console::Write("{0} ", ref);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="rehash"></a> hash_multiset:: rehash (STL/CLR)

해시 테이블을 다시 빌드합니다.

### <a name="syntax"></a>구문

```cpp
void rehash();
```

### <a name="remarks"></a>설명

멤버 함수는 해시 테이블을 다시 작성 [hash_multiset:: load_factor (STL/CLR)](../dotnet/hash-multiset-load-factor-stl-clr.md) `() <=` [hash_multiset:: max_load_factor (STL/CLR)](../dotnet/hash-multiset-max-load-factor-stl-clr.md)합니다. 이 고, 그렇지만 삽입 후 필요에 따라 해시 테이블 크기가 증가 합니다. (자동으로 감소 크기에서입니다.) 해시 테이블의 크기를 조정 하는 데 사용할 수 있습니다.

### <a name="example"></a>예제

```cpp
// cliext_hash_multiset_rehash.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_multiset<wchar_t> Myhash_multiset;
int main()
    {
    Myhash_multiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect current parameters
    System::Console::WriteLine("bucket_count() = {0}", c1.bucket_count());
    System::Console::WriteLine("load_factor() = {0}", c1.load_factor());
    System::Console::WriteLine("max_load_factor() = {0}",
        c1.max_load_factor());
    System::Console::WriteLine();

    // change max_load_factor and redisplay
    c1.max_load_factor(0.25f);
    System::Console::WriteLine("bucket_count() = {0}", c1.bucket_count());
    System::Console::WriteLine("load_factor() = {0}", c1.load_factor());
    System::Console::WriteLine("max_load_factor() = {0}",
        c1.max_load_factor());
    System::Console::WriteLine();

    // rehash and redisplay
    c1.rehash(100);
    System::Console::WriteLine("bucket_count() = {0}", c1.bucket_count());
    System::Console::WriteLine("load_factor() = {0}", c1.load_factor());
    System::Console::WriteLine("max_load_factor() = {0}",
        c1.max_load_factor());
    return (0);
    }
```

```Output
a b c
bucket_count() = 16
load_factor() = 0.1875
max_load_factor() = 4

bucket_count() = 16
load_factor() = 0.1875
max_load_factor() = 0.25

bucket_count() = 128
load_factor() = 0.0234375
max_load_factor() = 0.25
```

## <a name="rend"></a> hash_multiset:: rend (STL/CLR)

제어되는 역방향 시퀀스의 끝을 지정합니다.

### <a name="syntax"></a>구문

```cpp
reverse_iterator rend();
```

### <a name="remarks"></a>설명

멤버 함수는 제어 된 시퀀스의 시작 부분 바로 다음 가리키는 역방향 반복기를 반환합니다. 따라서 지정 된 `end` 역방향 시퀀스의 합니다. 지정 하는 반복기를 사용 하면는 `current` 제어 된 시퀀스를 역순으로 표시 되지만 해당 상태에 대 한 끝 제어 된 시퀀스의 길이가 변경 되 면 변경할 수 있습니다.

### <a name="example"></a>예제

```cpp
// cliext_hash_multiset_rend.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_multiset<wchar_t> Myhash_multiset;
int main()
    {
    Myhash_multiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect first two items
    Myhash_multiset::reverse_iterator rit = c1.rend();
    --rit;
    System::Console::WriteLine("*-- --rend() = {0}", *--rit);
    System::Console::WriteLine("*--rend() = {0}", *++rit);
    return (0);
    }
```

```Output
a b c
*-- --rend() = b
*--rend() = a
```

## <a name="reverse_iterator"></a> hash_multiset:: reverse_iterator (STL/CLR)

제어되는 시퀀스에 대한 반대 반복기의 형식입니다.

### <a name="syntax"></a>구문

```cpp
typedef T3 reverse_iterator;
```

### <a name="remarks"></a>설명

이 형식은 제어된 시퀀스에 대해 반대 반복기로 사용될 수 있는 지정되지 않은 `T3` 형식의 개체를 설명합니다.

### <a name="example"></a>예제

```cpp
// cliext_hash_multiset_reverse_iterator.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_multiset<wchar_t> Myhash_multiset;
int main()
    {
    Myhash_multiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display contents " a b c" reversed
    Myhash_multiset::reverse_iterator rit = c1.rbegin();
    for (; rit != c1.rend(); ++rit)
        System::Console::Write("{0} ", *rit);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c b a
```

## <a name="size"></a> hash_multiset:: size (STL/CLR)

요소 수를 계산합니다.

### <a name="syntax"></a>구문

```cpp
size_type size();
```

### <a name="remarks"></a>설명

멤버 함수는 제어되는 시퀀스의 길이를 반환합니다. 현재 제어 되는 시퀀스의에서 요소 수를 확인 하려면 사용 합니다. 모든 경우에 중요 한 여부 시퀀스 크기가 0이 아닌 참조 [hash_multiset:: empty (STL/CLR)](../dotnet/hash-multiset-empty-stl-clr.md)`()`합니다.

### <a name="example"></a>예제

```cpp
// cliext_hash_multiset_size.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_multiset<wchar_t> Myhash_multiset;
int main()
    {
    Myhash_multiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    System::Console::WriteLine("size() = {0} starting with 3", c1.size());

    // clear the container and reinspect
    c1.clear();
    System::Console::WriteLine("size() = {0} after clearing", c1.size());

    // add elements and clear again
    c1.insert(L'a');
    c1.insert(L'b');
    System::Console::WriteLine("size() = {0} after adding 2", c1.size());
    return (0);
    }
```

```Output
a b c
size() = 3 starting with 3
size() = 0 after clearing
size() = 2 after adding 2
```

## <a name="size_type"></a> hash_multiset:: size_type (STL/CLR)

두 요소 사이의 부호가 있는 거리의 형식입니다.

### <a name="syntax"></a>구문

```cpp
typedef int size_type;
```

### <a name="remarks"></a>설명

형식에는 음수가 아닌 요소 수를 설명합니다.

### <a name="example"></a>예제

```cpp
// cliext_hash_multiset_size_type.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_multiset<wchar_t> Myhash_multiset;
int main()
    {
    Myhash_multiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // compute positive difference
    Myhash_multiset::size_type diff = 0;
    for (Myhash_multiset::iterator it = c1.begin(); it != c1.end(); ++it)
        ++diff;
    System::Console::WriteLine("end()-begin() = {0}", diff);
    return (0);
    }
```

```Output
a b c
end()-begin() = 3
```

## <a name="swap"></a> hash_multiset:: swap (STL/CLR)

두 컨테이너의 내용을 바꿉니다.

### <a name="syntax"></a>구문

```cpp
void swap(hash_multiset<Key>% right);
```

#### <a name="parameters"></a>매개 변수

*right*<br/>
콘텐츠와 바꿀 컨테이너입니다.

### <a name="remarks"></a>설명

멤버 함수 간에 제어 된 시퀀스를 교환 `this` 하 고 *오른쪽*합니다. 일정 한 시간에 수행 하 고 예외가 throw 됩니다. 두 컨테이너의 콘텐츠를 교환 하는 빠른 방법으로 사용 합니다.

### <a name="example"></a>예제

```cpp
// cliext_hash_multiset_swap.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_multiset<wchar_t> Myhash_multiset;
int main()
    {
    Myhash_multiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct another container with repetition of values
    Myhash_multiset c2;
    c2.insert(L'd');
    c2.insert(L'e');
    c2.insert(L'f');
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // swap and redisplay
    c1.swap(c2);
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
d e f
d e f
a b c
```

## <a name="to_array"></a> hash_multiset:: to_array (STL/CLR)

제어 되는 시퀀스를 새 배열에 복사합니다.

### <a name="syntax"></a>구문

```cpp
cli::array<value_type>^ to_array();
```

### <a name="remarks"></a>설명

멤버 함수는 제어 되는 시퀀스를 포함 하는 배열을 반환 합니다. 배열 형식에서 제어 된 시퀀스의 복사본을 가져와야 사용할 수 있습니다.

### <a name="example"></a>예제

```cpp
// cliext_hash_multiset_to_array.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_multiset<wchar_t> Myhash_multiset;
int main()
    {
    Myhash_multiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // copy the container and modify it
    cli::array<wchar_t>^ a1 = c1.to_array();

    c1.insert(L'd');
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // display the earlier array copy
    for each (wchar_t elem in a1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c d
a b c
```

## <a name="upper_bound"></a> hash_multiset:: upper_bound (STL/CLR)

지정된 된 키와 일치 하는 범위의 끝을 찾습니다.

### <a name="syntax"></a>구문

```cpp
iterator upper_bound(key_type key);
```

#### <a name="parameters"></a>매개 변수

*key*<br/>
검색할 키 값입니다.

### <a name="remarks"></a>설명

마지막 요소를 결정 하는 멤버 함수 `X` 동일한 버킷으로 해시 되 제어 되는 시퀀스에서 *키* 과 순서가 있고 *키*합니다. 이러한 요소가 없으면 여부나 `X` 는 제어 된 시퀀스에서 마지막 요소 반환 [hash_multiset:: end (STL/CLR)](../dotnet/hash-multiset-end-stl-clr.md)`()`; 그렇지 않으면 있는 첫 번째 요소를 지정 하는 반복기를 반환 `X`. 지정된 된 키와 일치 하는 제어 된 시퀀스의 요소 시퀀스의 끝을 현재 찾으려고 사용할 수 있습니다.

### <a name="example"></a>예제

```cpp
// cliext_hash_multiset_upper_bound.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_multiset<wchar_t> Myhash_multiset;
int main()
    {
    Myhash_multiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    System::Console::WriteLine("upper_bound(L'x')==end() = {0}",
        c1.upper_bound(L'x') == c1.end());

    System::Console::WriteLine("*upper_bound(L'a') = {0}",
        *c1.upper_bound(L'a'));
    System::Console::WriteLine("*upper_bound(L'b') = {0}",
        *c1.upper_bound(L'b'));
    return (0);
    }
```

```Output
a b c
upper_bound(L'x')==end() = True
*upper_bound(L'a') = b
*upper_bound(L'b') = c
```

## <a name="value_comp"></a> hash_multiset:: value_comp (STL/CLR)

두 요소 값에 대 한 순서 지정 대리자를 복사합니다.

### <a name="syntax"></a>구문

```cpp
value_compare^ value_comp();
```

### <a name="remarks"></a>설명

멤버 함수는 제어 되는 시퀀스를 정렬 하는 데 사용 하는 순서 지정 대리자를 반환 합니다. 두 요소 값을 비교 하는 데 사용할 수 있습니다.

### <a name="example"></a>예제

```cpp
// cliext_hash_multiset_value_comp.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_multiset<wchar_t> Myhash_multiset;
int main()
    {
    Myhash_multiset c1;
    Myhash_multiset::value_compare^ kcomp = c1.value_comp();

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        kcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        kcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        kcomp(L'b', L'a'));
    System::Console::WriteLine();
    return (0);
    }
```

```Output
compare(L'a', L'a') = True
compare(L'a', L'b') = True
compare(L'b', L'a') = False
```

## <a name="value_compare"></a> hash_multiset:: value_compare (STL/CLR)

두 요소 값의 순서 지정 대리자입니다.

### <a name="syntax"></a>구문

```cpp
Microsoft::VisualC::StlClr::BinaryDelegate<generic_value, generic_value, bool>
    value_compare;
```

### <a name="remarks"></a>설명

형식 인수 값의 순서를 결정 하는 대리자에 대 한 동의어입니다.

### <a name="example"></a>예제

```cpp
// cliext_hash_multiset_value_compare.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_multiset<wchar_t> Myhash_multiset;
int main()
    {
    Myhash_multiset c1;
    Myhash_multiset::value_compare^ kcomp = c1.value_comp();

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        kcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        kcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        kcomp(L'b', L'a'));
    System::Console::WriteLine();
    return (0);
    }
```

```Output
compare(L'a', L'a') = True
compare(L'a', L'b') = True
compare(L'b', L'a') = False
```

## <a name="value_type"></a> hash_multiset:: value_type (STL/CLR)

요소의 형식입니다.

### <a name="syntax"></a>구문

```cpp
typedef generic_value value_type;
```

### <a name="remarks"></a>설명

이 형식은 `generic_value`의 동의어입니다.

### <a name="example"></a>예제

```cpp
// cliext_hash_multiset_value_type.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_multiset<wchar_t> Myhash_multiset;
int main()
    {
    Myhash_multiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display contents " a b c" using value_type
    for (Myhash_multiset::iterator it = c1.begin(); it != c1.end(); ++it)
        {   // store element in value_type object
        Myhash_multiset::value_type val = *it;

        System::Console::Write("{0} ", val);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```