---
title: map(STL/CLR)
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- cliext::map
- cliext::map::begin
- cliext::map::clear
- cliext::map::const_iterator
- cliext::map::const_reference
- cliext::map::const_reverse_iterator
- cliext::map::count
- cliext::map::difference_type
- cliext::map::empty
- cliext::map::end
- cliext::map::equal_range
- cliext::map::erase
- cliext::map::find
- cliext::map::generic_container
- cliext::map::generic_iterator
- cliext::map::generic_reverse_iterator
- cliext::map::generic_value
- cliext::map::insert
- cliext::map::iterator
- cliext::map::key_comp
- cliext::map::key_compare
- cliext::map::key_type
- cliext::map::lower_bound
- cliext::map::make_value
- cliext::map::map
- cliext::map::mapped_type
- cliext::map::operator=
- cliext::map::operator
- cliext::map::rbegin
- cliext::map::reference
- cliext::map::rend
- cliext::map::reverse_iterator
- cliext::map::size
- cliext::map::size_type
- cliext::map::swap
- cliext::map::to_array
- cliext::map::upper_bound
- cliext::map::value_comp
- cliext::map::value_compare
- cliext::map::value_type
- cliext::operator!= (map)
- cliext::operator< (map)
- cliext::operator<= (map)
- cliext::operator== (map)
- cliext::operator> (map)
- cliext::operator>= (map)
helpviewer_keywords:
- <map> header [STL/CLR]
- map class [STL/CLR]
- <cliext/map> header [STL/CLR]
- begin member [STL/CLR]
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
- insert member [STL/CLR]
- iterator member [STL/CLR]
- key_comp member [STL/CLR]
- key_compare member [STL/CLR]
- key_type member [STL/CLR]
- lower_bound member [STL/CLR]
- make_value member [STL/CLR]
- map member [STL/CLR]
- mapped_type member [STL/CLR]
- operator= member [STL/CLR]
- operator member [STL/CLR]
- rbegin member [STL/CLR]
- reference member [STL/CLR]
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
- operator!= (map) member [STL/CLR]
- operator< (map) member [STL/CLR]
- operator<= (map) member [STL/CLR]
- operator== (map) member [STL/CLR]
- operator> (map) member [STL/CLR]
- operator>= (map) member [STL/CLR]
ms.assetid: 8b0a7764-b5e4-4175-a802-82b72eb8662a
ms.openlocfilehash: 9150d603f67051df4a6f182366623935e59fe9ab
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62393716"
---
# <a name="map-stlclr"></a>map(STL/CLR)

템플릿 클래스는 요소의 양방향 액세스할 수 있는 다양 한 길이의 시퀀스를 제어 하는 개체를 설명 합니다. 컨테이너를 사용 하 `map` 각각 한 개의 요소 저장 노드 (거의) 분산 된 순서가 지정 된 트리로 요소의 시퀀스를 관리할 수 있습니다. 요소는 시퀀스 및 경험해를 따라 이동 하는 매핑된 값을 정렬 키가 구성 됩니다.

아래 설명에 `GValue` 와 같습니다.

`Microsoft::VisualC::StlClr::GenericPair<GKey, GMapped>`

다음은 각 문자에 대한 설명입니다.

`GKey` 동일 *키* 후자는 참조 형식, 하지 않는 한이 경우에서는 `Key^`

`GMapped` 동일 *매핑된* 후자는 참조 형식, 하지 않는 한이 경우에서는 `Mapped^`

## <a name="syntax"></a>구문

```cpp
template<typename Key,
    typename Mapped>
    ref class map
        :   public
        System::ICloneable,
        System::Collections::IEnumerable,
        System::Collections::ICollection,
        System::Collections::Generic::IEnumerable<GValue>,
        System::Collections::Generic::ICollection<GValue>,
        System::Collections::Generic::IList<GValue>,
        System::Collections::Generic::IDictionary<Gkey, GMapped>,
        Microsoft::VisualC::StlClr::ITree<Gkey, GValue>
    { ..... };
```

### <a name="parameters"></a>매개 변수

*키*<br/>
제어 된 시퀀스의 요소 키 구성 요소의 형식입니다.

*매핑된*<br/>
제어 된 시퀀스의 요소의 추가 구성 요소 형식입니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<cliext/맵을 >

**Namespace:** cliext

## <a name="declarations"></a>선언

|형식 정의|설명|
|---------------------|-----------------|
|[map::const_iterator(STL/CLR)](#const_iterator)|제어되는 시퀀스에 대한 상수 반복기의 형식입니다.|
|[map::const_reference(STL/CLR)](#const_reference)|요소에 대한 상수 참조의 형식입니다.|
|[map::const_reverse_iterator(STL/CLR)](#const_reverse_iterator)|제어되는 시퀀스에 대한 상수 역방향 반복기의 형식입니다.|
|[map::difference_type(STL/CLR)](#difference_type)|두 요소 사이의 (가능한 경우 부호 있는) 거리의 형식입니다.|
|[map::generic_container(STL/CLR)](#generic_container)|컨테이너에 대 한 제네릭 인터페이스의 형식입니다.|
|[map::generic_iterator(STL/CLR)](#generic_iterator)|컨테이너에 대 한 제네릭 인터페이스에 대 한 반복기의 형식입니다.|
|[map::generic_reverse_iterator(STL/CLR)](#generic_reverse_iterator)|컨테이너에 대 한 제네릭 인터페이스에 대 한 역방향 반복기의 형식입니다.|
|[map::generic_value(STL/CLR)](#generic_value)|제네릭 인터페이스에 대 한 컨테이너 요소 형식입니다.|
|[map::iterator(STL/CLR)](#iterator)|제어되는 시퀀스에 대한 반복기의 형식입니다.|
|[map::key_compare(STL/CLR)](#key_compare)|두 키의 순서 지정 대리자입니다.|
|[map::key_type(STL/CLR)](#key_type)|정렬 키의 형식입니다.|
|[map::mapped_type(STL/CLR)](#mapped_type)|각 키와 연결 된 매핑된 값의 형식입니다.|
|[map::reference(STL/CLR)](#reference)|요소에 대한 참조의 형식입니다.|
|[map::reverse_iterator(STL/CLR)](#reverse_iterator)|제어되는 시퀀스에 대한 반대 반복기의 형식입니다.|
|[map::size_type(STL/CLR)](#size_type)|두 요소 사이의 (음수가) 거리의 형식입니다.|
|[map::value_compare(STL/CLR)](#value_compare)|두 요소 값의 순서 지정 대리자입니다.|
|[map::value_type(STL/CLR)](#value_type)|요소의 형식입니다.|

|멤버 함수|설명|
|---------------------|-----------------|
|[map::begin(STL/CLR)](#begin)|제어되는 시퀀스의 시작을 지정합니다.|
|[map::clear(STL/CLR)](#clear)|모든 요소를 제거합니다.|
|[map::count(STL/CLR)](#count)|지정된 된 키와 일치 하는 요소를 계산 합니다.|
|[map::empty(STL/CLR)](#empty)|요소가 있는지 여부를 테스트합니다.|
|[map::end(STL/CLR)](#end)|제어되는 시퀀스의 끝을 지정합니다.|
|[map::equal_range(STL/CLR)](#equal_range)|지정된 키와 일치하는 범위를 찾습니다.|
|[map::erase(STL/CLR)](#erase)|지정된 위치에 있는 요소를 제거합니다.|
|[map::find(STL/CLR)](#find)|지정된 키와 일치하는 요소를 찾습니다.|
|[map::insert(STL/CLR)](#insert)|요소를 추가합니다.|
|[map::key_comp(STL/CLR)](#key_comp)|두 개의 키에 대 한 순서 지정 대리자를 복사합니다.|
|[map::lower_bound(STL/CLR)](#lower_bound)|지정된 된 키와 일치 하는 범위의 시작 부분을 찾습니다.|
|[map::make_value(STL/CLR)](#make_value)|값 개체를 생성합니다.|
|[map::map(STL/CLR)](#map)|컨테이너 개체를 만듭니다.|
|[map::rbegin(STL/CLR)](#rbegin)|제어되는 역방향 시퀀스의 시작을 지정합니다.|
|[map::rend(STL/CLR)](#rend)|제어되는 역방향 시퀀스의 끝을 지정합니다.|
|[map::size(STL/CLR)](#size)|요소 수를 계산합니다.|
|[map::swap(STL/CLR)](#swap)|두 컨테이너의 내용을 바꿉니다.|
|[map::to_array(STL/CLR)](#to_array)|제어 되는 시퀀스를 새 배열에 복사합니다.|
|[map::upper_bound(STL/CLR)](#upper_bound)|지정된 된 키와 일치 하는 범위의 끝을 찾습니다.|
|[map::value_comp(STL/CLR)](#value_comp)|두 요소 값에 대 한 순서 지정 대리자를 복사합니다.|

|연산자|설명|
|--------------|-----------------|
|[map::operator=(STL/CLR)](#op_as)|제어되는 시퀀스를 바꿉니다.|
|[map::operator(STL/CLR)](#op)|키가 관련된 매핑된 값에 매핑됩니다.|
|[operator!= (map)(STL/CLR)](#op_neq)|확인을 `map` 다른 개체가 같지 `map` 개체입니다.|
|[operator< (map)(STL/CLR)](#op_lt)|확인을 `map` 개체를 사용 하면 다른 노드보다 작은지 `map` 개체입니다.|
|[operator<= (map)(STL/CLR)](#op_lteq)|확인을 `map` 개체 보다 작거나 같으면 다른 `map` 개체입니다.|
|[operator== (map)(STL/CLR)](#op_eq)|확인을 `map` 다른 개체가 같은지 `map` 개체입니다.|
|[operator> (map)(STL/CLR)](#op_gt)|확인을 `map` 개체가 다른 인스턴스보다 큰지를 `map` 개체입니다.|
|[operator>= (map)(STL/CLR)](#op_gteq)|있는지 여부를 확인 한 `map` 보다 크거나 같은 다른 개체가 `map` 개체입니다.|

## <a name="interfaces"></a>인터페이스

|인터페이스|설명|
|---------------|-----------------|
|<xref:System.ICloneable>|개체를 복제 합니다.|
|<xref:System.Collections.IEnumerable>|요소 시퀀스입니다.|
|<xref:System.Collections.ICollection>|요소 그룹을 유지 합니다.|
|<xref:System.Collections.Generic.IEnumerable%601>|형식화 된 요소 시퀀스입니다.|
|<xref:System.Collections.Generic.ICollection%601>|형식화 된 요소 그룹을 유지 합니다.|
|<xref:System.Collections.Generic.IDictionary%602>|{0} 키, 값} 그룹을 유지 관리 쌍입니다.|
|ITree < 키, 값 >|제네릭 컨테이너를 유지 합니다.|

## <a name="remarks"></a>설명

개체를 할당 하 고 개별 노드로 제어 하는 시퀀스에 대 한 저장소를 해제 합니다. 유지 되지 다른 한 노드의 콘텐츠를 복사 하 여 노드 간 링크를 변경 하 여 정렬 된 트리를 균형된 (거의)에 요소를 삽입 합니다. 즉, 삽입 하 고 나머지 요소를 방해 하지 않고 자유롭게 요소를 제거할 수 있습니다.

개체 형식의 저장 된 대리자 개체를 호출 하 여 제어 하는 시퀀스를 정렬 [map:: key_compare (STL/CLR)](../dotnet/map-key-compare-stl-clr.md)합니다. 가 맵을 생성 하는 경우 저장 된 대리자 개체를 지정할 수 있습니다. 기본값은 비교 없는 대리자 개체를 지정 하면 `operator<(key_type, key_type)`합니다. 멤버 함수를 호출 하 여이 저장 된 개체를 액세스할 [map:: key_comp (STL/CLR)](../dotnet/map-key-comp-stl-clr.md)`()`합니다.

이러한 대리자 개체 형식의 키에 대해 엄밀히 약한 정렬을 적용 해야 합니다 [map:: key_type (STL/CLR)](../dotnet/map-key-type-stl-clr.md)합니다. 즉, 두 개의 키에 대 한 `X` 고 `Y`:

`key_comp()(X, Y)` 호출할 때마다 동일한 부울 결과 반환.

하는 경우 `key_comp()(X, Y)` 가 true 이면 `key_comp()(Y, X)` false 여야 합니다.

하는 경우 `key_comp()(X, Y)` 가 true 이면 `X` 앞에 정렬 되어 있다고는 `Y`합니다.

하는 경우 `!key_comp()(X, Y) && !key_comp()(Y, X)` 가 true 이면 `X` 및 `Y` 동일 하 게 정렬 하 라고 합니다.

모든 요소에 대 한 `X` 앞에 오는 `Y` 제어 된 시퀀스에서 `key_comp()(Y, X)` 은 false입니다. (기본 대리자 개체에 대 한 키 결코 감소 값입니다.) 템플릿 클래스와 달리 [지도](../dotnet/map-stl-clr.md)를 템플릿 클래스의 개체 `map` 모든 요소에 대 한 키가 고유한 지 필요 하지 않습니다. (두 개 이상의 키 수 동일 하 게 정렬 됩니다.)

각 요소는 별도 키 및 매핑된 값을 포함합니다. 시퀀스는 시퀀스 (로그 시간)를에서 조회, 삽입 및 임의 요소 수의 요소 수의 로그에 비례 하는 작업을 사용 하 여 제거를 허용 하는 방식으로 표시 됩니다. 또한, 요소를 삽입할 경우 어떤 반복기도 무효화되지 않으며, 요소를 제거할 경우 제거된 요소를 가리키고 있는 반복기만 무효화됩니다.

지도 제어 된 시퀀스의 요소를 지정 하는 반복기를 제공 하는 인접 요소를 실행할 수 있습니다 의미 있는 양방향 반복기를 지원 합니다. 반환 된 반복기에 해당 하는 특수 헤드 노드 [map:: end (STL/CLR)](../dotnet/map-end-stl-clr.md)`()`합니다. 있는 경우에 제어 된 시퀀스에서 마지막 요소를 연결할이 반복기를 감소 시킬 수 있습니다. 헤드 노드에 도달 하는 지도 반복기를 증가 시킬 수 있습니다 및 같음 비교 다음 `end()`합니다. 반환 된 반복기를 역 참조할 수 없습니다 있지만 `end()`합니다.

참조할 수 없습니다. 직접 임의 액세스 반복기를 필요로 하는 숫자 위치-지정 된 지도 요소는 참고 합니다.

지도 반복기에 연결 된 해당 컨테이너에 대 한 핸들을 저장 하는 해당 연결된 맵 노드에 대 한 핸들을 저장 합니다. 반복기는 연결 된 컨테이너 개체에만 사용할 수 있습니다. 지도 반복기도 해당 연결된 맵을 노드가 일부 맵과 사용 하 여 연결 된 유효한 상태로 유지 됩니다. 또한 유효한 반복기는 역-액세스 또는 같지 않은 하기만-지정 된 요소 값을 변경 하는 데 사용할 수 있습니다 `end()`합니다.

지우거 나 요소를 제거 합니다. 저장된 된 값에 대 한 소멸자를 호출 합니다. 모든 요소를 지웁니다 컨테이너를 제거 합니다. 따라서 요소 형식인 ref 클래스는 컨테이너 보다 수명이 길 컨테이너 요소가 있는지 확인 합니다. 단, 핸들의 컨테이너에는 *되지* 해당 요소를 제거 합니다.

## <a name="members"></a>멤버

## <a name="begin"></a> map:: begin (STL/CLR)

제어되는 시퀀스의 시작을 지정합니다.

### <a name="syntax"></a>구문

```cpp
iterator begin();
```

### <a name="remarks"></a>설명

멤버 함수는 제어 된 시퀀스 또는 빈 시퀀스의 끝 바로 다음 첫 번째 요소를 지정 하는 양방향 반복기를 반환 합니다. 지정 하는 반복기를 사용 하면는 `current` 상태가 제어 된 시퀀스의 시작 부분 제어 된 시퀀스의 길이가 변경 되 면 변경할 수 있습니다.

### <a name="example"></a>예제

```cpp
// cliext_map_begin.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // inspect first two items
    Mymap::iterator it = c1.begin();
    System::Console::WriteLine("*begin() = [{0} {1}]",
        it->first, it->second);
    ++it;
    System::Console::WriteLine("*++begin() = [{0} {1}]",
        it->first, it->second);
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
*begin() = [a 1]
*++begin() = [b 2]
```

## <a name="clear"></a> map:: clear (STL/CLR)

모든 요소를 제거합니다.

### <a name="syntax"></a>구문

```cpp
void clear();
```

### <a name="remarks"></a>설명

멤버 함수는 효과적으로 호출한 [map:: erase (STL/CLR)](../dotnet/map-erase-stl-clr.md) `(` [map:: begin (STL/CLR)](../dotnet/map-begin-stl-clr.md) `(),` [map:: end (STL/CLR)](../dotnet/map-end-stl-clr.md) `())`. 제어 되는 시퀀스 비어 있는지 확인 하는 데 사용할 수 있습니다.

### <a name="example"></a>예제

```cpp
// cliext_map_clear.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // clear the container and reinspect
    c1.clear();
    System::Console::WriteLine("size() = {0}", c1.size());

    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));

    // display contents " [a 1] [b 2]"
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();
    c1.clear();
    System::Console::WriteLine("size() = {0}", c1.size());
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
size() = 0
[a 1] [b 2]
size() = 0
```

## <a name="const_iterator"></a> map:: const_iterator (STL/CLR)

제어되는 시퀀스에 대한 상수 반복기의 형식입니다.

### <a name="syntax"></a>구문

```cpp
typedef T2 const_iterator;
```

### <a name="remarks"></a>설명

이 형식은 지정 되지 않은 형식의 개체를 설명 `T2` 제어 되는 시퀀스의 상수 양방향 반복기로 사용할 수 있는 합니다.

### <a name="example"></a>예제

```cpp
// cliext_map_const_iterator.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    Mymap::const_iterator cit = c1.begin();
    for (; cit != c1.end(); ++cit)
        System::Console::Write("[{0} {1}] ", cit->first, cit->second);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
```

## <a name="const_reference"></a> map:: const_reference (STL/CLR)

요소에 대한 상수 참조의 형식입니다.

### <a name="syntax"></a>구문

```cpp
typedef value_type% const_reference;
```

### <a name="remarks"></a>설명

형식 요소에 대 한 상수 참조를 설명합니다.

### <a name="example"></a>예제

```cpp
// cliext_map_const_reference.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    Mymap::const_iterator cit = c1.begin();
    for (; cit != c1.end(); ++cit)
        {   // get a const reference to an element
        Mymap::const_reference cref = *cit;
        System::Console::Write("[{0} {1}] ", cref->first, cref->second);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
```

## <a name="const_reverse_iterator"></a> map:: const_reverse_iterator (STL/CLR)

제어 되는 시퀀스의 상수 역방향 반복기의 형식...

### <a name="syntax"></a>구문

```cpp
typedef T4 const_reverse_iterator;
```

### <a name="remarks"></a>설명

이 형식은 지정 되지 않은 형식의 개체를 설명 `T4` 제어 되는 시퀀스의 상수 역방향 반복기로 사용할 수 있는 합니다.

### <a name="example"></a>예제

```cpp
// cliext_map_const_reverse_iterator.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]" reversed
    Mymap::const_reverse_iterator crit = c1.rbegin();
    for (; crit != c1.rend(); ++crit)
        System::Console::Write("[{0} {1}] ", crit->first, crit->second);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[c 3] [b 2] [a 1]
```

## <a name="count"></a> map:: count (STL/CLR)

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
// cliext_map_count.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    System::Console::WriteLine("count(L'A') = {0}", c1.count(L'A'));
    System::Console::WriteLine("count(L'b') = {0}", c1.count(L'b'));
    System::Console::WriteLine("count(L'C') = {0}", c1.count(L'C'));
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
count(L'A') = 0
count(L'b') = 1
count(L'C') = 0
```

## <a name="difference_type"></a> map:: difference_type (STL/CLR)

두 요소 사이의 부호가 있는 거리의 형식입니다.

### <a name="syntax"></a>구문

```cpp
typedef int difference_type;
```

### <a name="remarks"></a>설명

형식 음수 수 있는 요소 수를 설명합니다.

### <a name="example"></a>예제

```cpp
// cliext_map_difference_type.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // compute positive difference
    Mymap::difference_type diff = 0;
    for (Mymap::iterator it = c1.begin(); it != c1.end(); ++it)
        ++diff;
    System::Console::WriteLine("end()-begin() = {0}", diff);

    // compute negative difference
    diff = 0;
    for (Mymap::iterator it = c1.end(); it != c1.begin(); --it)
        --diff;
    System::Console::WriteLine("begin()-end() = {0}", diff);
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
end()-begin() = 3
begin()-end() = -3
```

## <a name="empty"></a> map:: empty (STL/CLR)

요소가 있는지 여부를 테스트합니다.

### <a name="syntax"></a>구문

```cpp
bool empty();
```

### <a name="remarks"></a>설명

멤버 함수는 빈 제어되는 시퀀스에 대해 true를 반환합니다. 에 해당 하는 것 [map:: size (STL/CLR)](../dotnet/map-size-stl-clr.md)`() == 0`합니다. Map이 비어 있는지 여부를 테스트 하려면 사용 합니다.

### <a name="example"></a>예제

```cpp
// cliext_map_empty.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
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
[a 1] [b 2] [c 3]
size() = 3
empty() = False
size() = 0
empty() = True
```

## <a name="end"></a> map:: end (STL/CLR)

제어되는 시퀀스의 끝을 지정합니다.

### <a name="syntax"></a>구문

```cpp
iterator end();
```

### <a name="remarks"></a>설명

멤버 함수는 제어 된 시퀀스의 끝 바로 다음을 가리키는 양방향 반복기를 반환합니다. 제어 된 시퀀스의 끝을 지정 하는 반복기를 사용 하면 해당 상태 만들어지고 제어 된 시퀀스의 길이가 변경 되 면 변경 되지 않습니다.

### <a name="example"></a>예제

```cpp
// cliext_map_end.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // inspect last two items
    Mymap::iterator it = c1.end();
    --it;
    --it;
    System::Console::WriteLine("*-- --end() = [{0} {1}]",
        it->first, it->second);
    ++it;
    System::Console::WriteLine("*--end() = [{0} {1}]",
        it->first, it->second);
    return (0);
    }
```

## <a name="equal_range"></a> map:: equal_range (STL/CLR)

지정된 키와 일치하는 범위를 찾습니다.

### <a name="syntax"></a>구문

```cpp
cliext::pair<iterator, iterator> equal_range(key_type key);
```

#### <a name="parameters"></a>매개 변수

*key*<br/>
검색할 키 값입니다.

### <a name="remarks"></a>설명

반복기의 쌍을 반환 하는 멤버 함수 `cliext::pair<iterator, iterator>(` [map:: lower_bound (STL/CLR)](../dotnet/map-lower-bound-stl-clr.md) `(key),` [map:: upper_bound (STL/CLR)](../dotnet/map-upper-bound-stl-clr.md)`(key))`합니다. 지정된 된 키와 일치 하는 제어 되는 시퀀스에서 현재 요소의 범위를 확인 하려면 사용 합니다.

### <a name="example"></a>예제

```cpp
// cliext_map_equal_range.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
typedef Mymap::pair_iter_iter Pairii;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // display results of failed search
    Pairii pair1 = c1.equal_range(L'x');
    System::Console::WriteLine("equal_range(L'x') empty = {0}",
        pair1.first == pair1.second);

    // display results of successful search
    pair1 = c1.equal_range(L'b');
    for (; pair1.first != pair1.second; ++pair1.first)
        System::Console::Write("[{0} {1}] ",
            pair1.first->first, pair1.first->second);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
equal_range(L'x') empty = True
[b 2]
```

## <a name="erase"></a> map:: erase (STL/CLR)

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

가 가리키는 제어 되는 시퀀스의 요소를 제거 하는 첫 번째 멤버 함수 *여기서*를 제거 하는 요소 뒤에 남은 첫 번째 요소를 지정 하는 반복기를 반환 합니다. 또는 [map:: end (STL/CLR) ](../dotnet/map-end-stl-clr.md) `()` 이러한 요소가 없는 경우. 단일 요소를 제거 하려면 사용 합니다.

두 번째 멤버 함수 범위에서 제어 된 시퀀스의 요소를 제거 합니다. [`first`, `last`), 제거 된 요소 뒤에 남은 첫 번째 요소를 지정 하는 반복기를 반환 합니다. 또는 `end()` 이러한 요소가 없는 경우 존재 하 고... 0 개 이상의 연속 요소를 제거 하려면 사용 합니다.

키에 동일한 순서 제어 된 시퀀스의 모든 요소를 제거 하는 세 번째 멤버 함수를 *키*, 제거 된 요소의 개수를 반환 합니다. 제거 하 고 지정된 된 키와 일치 하는 모든 요소를 계산 하는 데 사용할 수 있습니다.

각 요소 지우기 제어 되는 시퀀스의 요소 수 로그에 비례한 시간을 사용합니다.

### <a name="example"></a>예제

```cpp
// cliext_map_erase.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    cliext::map<wchar_t, int> c1;
    c1.insert(cliext::map<wchar_t, int>::make_value(L'a', 1));
    c1.insert(cliext::map<wchar_t, int>::make_value(L'b', 2));
    c1.insert(cliext::map<wchar_t, int>::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (cliext::map<wchar_t, int>::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // erase an element and reinspect
    cliext::map<wchar_t, int>::iterator it =
        c1.erase(c1.begin());
    System::Console::WriteLine("erase(begin()) = [{0} {1}]",
        it->first, it->second);

    // add elements and display " b c d e"
    c1.insert(cliext::map<wchar_t, int>::make_value(L'd', 4));
    c1.insert(cliext::map<wchar_t, int>::make_value(L'e', 5));
    for each (cliext::map<wchar_t, int>::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // erase all but end
    it = c1.end();
    it = c1.erase(c1.begin(), --it);
    System::Console::WriteLine("erase(begin(), end()-1) = [{0} {1}]",
        it->first, it->second);
    System::Console::WriteLine("size() = {0}", c1.size());

    // erase end
    System::Console::WriteLine("erase(L'x') = {0}", c1.erase(L'x'));
    System::Console::WriteLine("erase(L'e') = {0}", c1.erase(L'e'));
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
erase(begin()) = [b 2]
[b 2] [c 3] [d 4] [e 5]
erase(begin(), end()-1) = [e 5]
size() = 1
erase(L'x') = 0
erase(L'e') = 1
```

## <a name="find"></a> map:: find (STL/CLR)

지정된 키와 일치하는 요소를 찾습니다.

### <a name="syntax"></a>구문

```cpp
iterator find(key_type key);
```

#### <a name="parameters"></a>매개 변수

*key*<br/>
검색할 키 값입니다.

### <a name="remarks"></a>설명

사용 하 여 해당 순서 제어 된 시퀀스의 요소를 하나 이상 있으면 *키*, 멤버 함수는 이러한 요소 중 하나를 지정 하는 반복기를 반환, 그렇지 않으면 반환 [map:: end (STL/CLR)](../dotnet/map-end-stl-clr.md)`()`. 지정된 된 키와 일치 하는 제어 된 시퀀스의 요소를 현재 찾으려고 사용할 수 있습니다.

### <a name="example"></a>예제

```cpp
// cliext_map_find.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    System::Console::WriteLine("find {0} = {1}",
        L'A', c1.find(L'A') != c1.end());

    Mymap::iterator it = c1.find(L'b');
    System::Console::WriteLine("find {0} = [{1} {2}]",
        L'b', it->first, it->second);

    System::Console::WriteLine("find {0} = {1}",
        L'C', c1.find(L'C') != c1.end());
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
find A = False
find b = [b 2]
find C = False
```

## <a name="generic_container"></a> map:: generic_container (STL/CLR)

컨테이너에 대 한 제네릭 인터페이스의 형식입니다.

### <a name="syntax"></a>구문

```cpp
typedef Microsoft::VisualC::StlClr::
    ITree<GKey, GValue>
    generic_container;
```

### <a name="remarks"></a>설명

형식은이 템플릿 컨테이너 클래스에 대 한 제네릭 인터페이스를 설명합니다.

### <a name="example"></a>예제

```cpp
// cliext_map_generic_container.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // construct a generic container
    Mymap::generic_container^ gc1 = %c1;
    for each (Mymap::value_type elem in gc1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // modify generic and display original
    gc1->insert(Mymap::make_value(L'd', 4));
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // modify original and display generic
    c1.insert(Mymap::make_value(L'e', 5));
    for each (Mymap::value_type elem in gc1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
[a 1] [b 2] [c 3]
[a 1] [b 2] [c 3] [d 4]
[a 1] [b 2] [c 3] [d 4] [e 5]
```

## <a name="generic_iterator"></a> map:: generic_iterator (STL/CLR)

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
// cliext_map_generic_iterator.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // construct a generic container
    Mymap::generic_container^ gc1 = %c1;
    for each (Mymap::value_type elem in gc1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // get an element and display it
    Mymap::generic_iterator gcit = gc1->begin();
    Mymap::generic_value gcval = *gcit;
    System::Console::Write("[{0} {1}] ", gcval->first, gcval->second);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
[a 1] [b 2] [c 3]
[a 1]
```

## <a name="generic_reverse_iterator"></a> map:: generic_reverse_iterator (STL/CLR)

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
// cliext_map_generic_reverse_iterator.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // construct a generic container
    Mymap::generic_container^ gc1 = %c1;
    for each (Mymap::value_type elem in gc1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // get an element and display it
    Mymap::generic_reverse_iterator gcit = gc1->rbegin();
    Mymap::generic_value gcval = *gcit;
    System::Console::WriteLine("[{0} {1}] ", gcval->first, gcval->second);
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
[a 1] [b 2] [c 3]
[c 3]
```

## <a name="generic_value"></a> map:: generic_value (STL/CLR)

컨테이너에 대 한 제네릭 인터페이스를 사용 하 여 사용에 대 한 요소의 형식입니다.

### <a name="syntax"></a>구문

```cpp
typedef GValue generic_value;
```

### <a name="remarks"></a>설명

이 형식은 형식의 개체를 설명 `GValue` 는이 템플릿 컨테이너 클래스에 대 한 제네릭 인터페이스를 사용 하 여 사용 하 여 저장 된 요소 값에 설명 합니다.

### <a name="example"></a>예제

```cpp
// cliext_map_generic_value.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // construct a generic container
    Mymap::generic_container^ gc1 = %c1;
    for each (Mymap::value_type elem in gc1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // get an element and display it
    Mymap::generic_iterator gcit = gc1->begin();
    Mymap::generic_value gcval = *gcit;
    System::Console::WriteLine("[{0} {1}] ", gcval->first, gcval->second);
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
[a 1] [b 2] [c 3]
[a 1]
```

## <a name="insert"></a> map:: insert (STL/CLR)

요소를 추가합니다.

### <a name="syntax"></a>구문

```cpp
cliext::pair<iterator, bool> insert(value_type val);
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

첫 번째 멤버 함수에서 값을 사용 하 여 요소를 삽입 하려고 *val*, 한 쌍의 값을 반환 하 고 `X`입니다. 경우 `X.second` 가 true 이면 `X.first` 새로 삽입된 된 요소를 지정 하 고, 그렇지 않으면 `X.first` 지정 요소를 동일한 순서는 이미 존재 하며 새 요소가 삽입 되 합니다. 단일 요소를 삽입 하는 데 사용할 수 있습니다.

두 번째 멤버 함수는 값을 사용 하 여 요소를 삽입 *val*를 사용 하 여 *여기서* (성능을 향상 시키기 위해) 힌트를 새로 삽입된 된 요소를 지정 하는 반복기를 반환 합니다. 알고 있는 요소에 인접 한 될 수 있는 단일 요소를 삽입 하는 데 사용할 수 있습니다.

세 번째 멤버 함수는 시퀀스를 삽입 합니다. [`first`, `last`). 다른 시퀀스에서 복사 된 0 개 이상의 요소를 삽입 하는 데 사용할 수 있습니다.

로 지정 된 시퀀스를 삽입 하는 네 번째 멤버 함수는 *오른쪽*합니다. 열거자에서 설명 하는 시퀀스를 삽입 하는 데 사용할 수 있습니다.

제어 되는 시퀀스의 요소 수 로그에 비례한 시간을 사용 하는 각 요소를 삽입 합니다. 그러나 삽입에서에서 발생할 수 있습니다 분할 상환된 상수 시간 삽입 지점에 인접 한 요소를 지정 하는 힌트를 지정 합니다.

### <a name="example"></a>예제

```cpp
// cliext_map_insert.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
typedef Mymap::pair_iter_bool Pairib;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // insert a single value, unique and duplicate
// insert a single value, success and failure
    Pairib pair1 = c1.insert(Mymap::make_value(L'x', 24));
    System::Console::WriteLine("insert([L'x' 24]) = [[{0} {1}] {2}]",
        pair1.first->first, pair1.first->second, pair1.second);

    pair1 = c1.insert(Mymap::make_value(L'b', 2));
    System::Console::WriteLine("insert([L'b' 2]) = [[{0} {1}] {2}]",
        pair1.first->first, pair1.first->second, pair1.second);

    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // insert a single value with hint
    Mymap::iterator it =
        c1.insert(c1.begin(), Mymap::make_value(L'y', 25));
    System::Console::WriteLine("insert(begin(), [L'y' 25]) = [{0} {1}]",
        it->first, it->second);
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // insert an iterator range
    Mymap c2;
    it = c1.end();
    c2.insert(c1.begin(), --it);
    for each (Mymap::value_type elem in c2)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // insert an enumeration
    Mymap c3;
    c3.insert(   // NOTE: cast is not needed
        (System::Collections::Generic::
            IEnumerable<Mymap::value_type>^)%c1);
    for each (Mymap::value_type elem in c3)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
insert([L'x' 24]) = [[x 24] True]
insert([L'b' 2]) = [[b 2] False]
[a 1] [b 2] [c 3] [x 24]
insert(begin(), [L'y' 25]) = [y 25]
[a 1] [b 2] [c 3] [x 24] [y 25]
[a 1] [b 2] [c 3] [x 24]
[a 1] [b 2] [c 3] [x 24] [y 25]
```

## <a name="iterator"></a> map:: iterator (STL/CLR)

제어되는 시퀀스에 대한 반복기의 형식입니다.

### <a name="syntax"></a>구문

```cpp
typedef T1 iterator;
```

### <a name="remarks"></a>설명

이 형식은 지정 되지 않은 형식의 개체를 설명 `T1` 제어 되는 시퀀스는 양방향 반복기로 사용할 수 있는 합니다.

### <a name="example"></a>예제

```cpp
// cliext_map_iterator.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    Mymap::iterator it = c1.begin();
    for (; it != c1.end(); ++it)
        System::Console::Write("[{0} {1}] ", it->first, it->second);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
```

## <a name="key_comp"></a> map:: key_comp (STL/CLR)

두 개의 키에 대 한 순서 지정 대리자를 복사합니다.

### <a name="syntax"></a>구문

```cpp
key_compare^key_comp();
```

### <a name="remarks"></a>설명

멤버 함수는 제어 되는 시퀀스를 정렬 하는 데 사용 하는 순서 지정 대리자를 반환 합니다. 두 키 비교에 사용할 수 있습니다.

### <a name="example"></a>예제

```cpp
// cliext_map_key_comp.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    Mymap::key_compare^ kcomp = c1.key_comp();

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        kcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        kcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        kcomp(L'b', L'a'));
    System::Console::WriteLine();

    // test a different ordering rule
    Mymap c2 = cliext::greater<wchar_t>();
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
compare(L'a', L'a') = False
compare(L'a', L'b') = True
compare(L'b', L'a') = False

compare(L'a', L'a') = False
compare(L'a', L'b') = False
compare(L'b', L'a') = True
```

## <a name="key_compare"></a> map:: key_compare (STL/CLR)

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
// cliext_map_key_compare.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    Mymap::key_compare^ kcomp = c1.key_comp();

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        kcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        kcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        kcomp(L'b', L'a'));
    System::Console::WriteLine();

    // test a different ordering rule
    Mymap c2 = cliext::greater<wchar_t>();
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
compare(L'a', L'a') = False
compare(L'a', L'b') = True
compare(L'b', L'a') = False

compare(L'a', L'a') = False
compare(L'a', L'b') = False
compare(L'b', L'a') = True
```

## <a name="key_type"></a> map:: key_type (STL/CLR)

정렬 키의 형식입니다.

### <a name="syntax"></a>구문

```cpp
typedef Key key_type;
```

### <a name="remarks"></a>설명

형식은 템플릿 매개 변수에 대 한 동의어 *키*합니다.

### <a name="example"></a>예제

```cpp
// cliext_map_key_type.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]" using key_type
    for (Mymap::iterator it = c1.begin(); it != c1.end(); ++it)
        {   // store element in key_type object
        Mymap::key_type val = it->first;

        System::Console::Write("{0} ", val);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="lower_bound"></a> map:: lower_bound (STL/CLR)

지정된 된 키와 일치 하는 범위의 시작 부분을 찾습니다.

### <a name="syntax"></a>구문

```cpp
iterator lower_bound(key_type key);
```

#### <a name="parameters"></a>매개 변수

*key*<br/>
검색할 키 값입니다.

### <a name="remarks"></a>설명

첫 번째 요소를 결정 하는 멤버 함수 `X` 과 순서가 있는 제어 되는 시퀀스 *키*합니다. 이러한 요소가 없으면 반환 [map:: end (STL/CLR)](../dotnet/map-end-stl-clr.md)`()`; 그렇지 않으면 지정 하는 반복기를 반환 `X`합니다. 지정된 된 키와 일치 하는 제어 된 시퀀스의 요소 시퀀스의 시작 부분을 현재 찾으려고 사용할 수 있습니다.

### <a name="example"></a>예제

```cpp
// cliext_map_lower_bound.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    System::Console::WriteLine("lower_bound(L'x')==end() = {0}",
        c1.lower_bound(L'x') == c1.end());

    Mymap::iterator it = c1.lower_bound(L'a');
    System::Console::WriteLine("*lower_bound(L'a') = [{0} {1}]",
        it->first, it->second);
    it = c1.lower_bound(L'b');
    System::Console::WriteLine("*lower_bound(L'b') = [{0} {1}]",
        it->first, it->second);
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
lower_bound(L'x')==end() = True
*lower_bound(L'a') = [a 1]
*lower_bound(L'b') = [b 2]
```

## <a name="make_value"></a> map:: make_value (STL/CLR)

값 개체를 생성합니다.

### <a name="syntax"></a>구문

```cpp
static value_type make_value(key_type key, mapped_type mapped);
```

#### <a name="parameters"></a>매개 변수

*key*<br/>
사용할 키 값입니다.

*mapped*<br/>
검색할 매핑된 값입니다.

### <a name="remarks"></a>설명

멤버 함수가 반환 하는 `value_type` 키가 있는 개체 *키* 매핑된 값 이며 *매핑된*합니다. 적합 한 몇 가지 다른 멤버 함수를 사용 하 여 사용 하 여 개체를 작성 하는 데 사용할 수 있습니다.

### <a name="example"></a>예제

```cpp
// cliext_map_make_value.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
```

## <a name="map"></a> map:: map (STL/CLR)

컨테이너 개체를 만듭니다.

### <a name="syntax"></a>구문

```cpp
map();
explicit map(key_compare^ pred);
map(map<Key, Mapped>% right);
map(map<Key, Mapped>^ right);
template<typename InIter>
    mapmap(InIter first, InIter last);
template<typename InIter>
    map(InIter first, InIter last,
        key_compare^ pred);
map(System::Collections::Generic::IEnumerable<GValue>^ right);
map(System::Collections::Generic::IEnumerable<GValue>^ right,
    key_compare^ pred);
```

#### <a name="parameters"></a>매개 변수

*first*<br/>
삽입할 범위의 시작입니다.

*last*<br/>
삽입할 범위의 끝입니다.

*pred*<br/>
제어 되는 시퀀스에 대 한 조건자를 정렬 합니다.

*right*<br/>
삽입할 개체 또는 범위입니다.

### <a name="remarks"></a>설명

생성자:

`map();`

조건자 순서 기본값을 사용 하 여 아무런 요소도 갖고 제어 되는 시퀀스 초기화 `key_compare()`합니다. 기본값은 조건자를 순서는 빈 초기 제어 되는 시퀀스를 지정 하려면 사용할 수 있습니다.

생성자:

`explicit map(key_compare^ pred);`

순서 지정 조건자를 사용 하 여 요소가 없는 제어 되는 시퀀스를 초기화 *pred*합니다. 지정된 된 순서 지정 조건자를 사용 하 여 빈 초기 제어 된 시퀀스를 지정 하는 데 사용할 수 있습니다.

생성자:

`map(map<Key, Mapped>% right);`

시퀀스를 사용 하 여 제어 되는 시퀀스를 초기화 합니다. [`right.begin()`, `right.end()`), 조건자 정렬 기본값을 사용 하 여 합니다. Map 개체에 의해 제어 되는 시퀀스의 복사본 인 초기 제어 된 시퀀스를 지정 하려면 사용할 *오른쪽*, 조건자 정렬 기본값을 사용 하 여 합니다.

생성자:

`map(map<Key, Mapped>^ right);`

시퀀스를 사용 하 여 제어 되는 시퀀스를 초기화 합니다. [`right->begin()`, `right->end()`), 조건자 정렬 기본값을 사용 하 여 합니다. Map 개체에 의해 제어 되는 시퀀스의 복사본 인 초기 제어 된 시퀀스를 지정 하려면 사용할 *오른쪽*, 조건자 정렬 기본값을 사용 하 여 합니다.

생성자:

`template<typename InIter> map(InIter first, InIter last);`

시퀀스를 사용 하 여 제어 되는 시퀀스를 초기화 합니다. [`first`, `last`), 조건자 정렬 기본값을 사용 하 여 합니다. 사용 하 여 조건자 정렬 기본값을 사용 하 여 제어 되는 다른 시퀀스의 복사본을 만듭니다.

생성자:

`template<typename InIter> map(InIter first, InIter last, key_compare^ pred);`

시퀀스를 사용 하 여 제어 되는 시퀀스를 초기화 합니다. [`first`, `last`), 순서 지정 조건자를 사용 하 여 *pred*합니다. 사용 하 여이 제어 되는 지정된 된 순서 지정 조건자를 사용 하 여 다른 시퀀스의 복사본을 만듭니다.

생성자:

`map(System::Collections::Generic::IEnumerable<Key>^ right);`

열거자에서 지정 된 시퀀스를 사용 하 여 제어 되는 시퀀스를 초기화 *오른쪽*, 조건자 정렬 기본값을 사용 하 여 합니다. 제어 되는 시퀀스의 복사본 조건자 정렬 기본값을 사용 하 여 열거자를 설명 하는 다른 순서를 사용 합니다.

생성자:

`map(System::Collections::Generic::IEnumerable<Key>^ right, key_compare^ pred);`

열거자에서 지정 된 시퀀스를 사용 하 여 제어 되는 시퀀스를 초기화 *오른쪽*, 순서 지정 조건자를 사용 하 여 *pred*합니다. 사용 하 여 제어 되는 시퀀스에서 지정된 된 순서 지정 조건자를 사용 하 여 열거자를 설명 하는 다른 시퀀스의 복사본을 만듭니다.

### <a name="example"></a>예제

```cpp
// cliext_map_construct.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
// construct an empty container
    Mymap c1;
    System::Console::WriteLine("size() = {0}", c1.size());

    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // construct with an ordering rule
    Mymap c2 = cliext::greater_equal<wchar_t>();
    System::Console::WriteLine("size() = {0}", c2.size());

    c2.insert(c1.begin(), c1.end());
    for each (Mymap::value_type elem in c2)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // construct with an iterator range
    Mymap c3(c1.begin(), c1.end());
    for each (Mymap::value_type elem in c3)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // construct with an iterator range and an ordering rule
    Mymap c4(c1.begin(), c1.end(),
        cliext::greater_equal<wchar_t>());
    for each (Mymap::value_type elem in c4)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // construct with an enumeration
    Mymap c5(   // NOTE: cast is not needed
        (System::Collections::Generic::IEnumerable<
            Mymap::value_type>^)%c3);
    for each (Mymap::value_type elem in c5)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // construct with an enumeration and an ordering rule
    Mymap c6(   // NOTE: cast is not needed
        (System::Collections::Generic::IEnumerable<
            Mymap::value_type>^)%c3,
                cliext::greater_equal<wchar_t>());
    for each (Mymap::value_type elem in c6)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // construct by copying another container
    Mymap c7(c4);
    for each (Mymap::value_type elem in c7)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // construct by copying a container handle
    Mymap c8(%c3);
    for each (Mymap::value_type elem in c8)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
size() = 0
[a 1] [b 2] [c 3]
size() = 0
[c 3] [b 2] [a 1]
[a 1] [b 2] [c 3]
[c 3] [b 2] [a 1]
[a 1] [b 2] [c 3]
[c 3] [b 2] [a 1]
[c 3] [b 2] [a 1]
[a 1] [b 2] [c 3]
```

## <a name="mapped_type"></a> map:: mapped_type (STL/CLR)

각 키와 연결된 매핑된 값의 형식입니다.

### <a name="syntax"></a>구문

```cpp
typedef Mapped mapped_type;
```

### <a name="remarks"></a>설명

형식은 템플릿 매개 변수에 대 한 동의어 *매핑된*합니다.

### <a name="example"></a>예제

```cpp
// cliext_map_mapped_type.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]" using mapped_type
    for (Mymap::iterator it = c1.begin(); it != c1.end(); ++it)
        {   // store element in mapped_type object
        Mymap::mapped_type val = it->second;

        System::Console::Write("{0} ", val);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
1 2 3
```

## <a name="op_as"></a> map:: operator = (STL/CLR)

제어되는 시퀀스를 바꿉니다.

### <a name="syntax"></a>구문

```cpp
map<Key, Mapped>% operator=(map<Key, Mapped>% right);
```

#### <a name="parameters"></a>매개 변수

*right*<br/>
복사할 컨테이너입니다.

### <a name="remarks"></a>설명

멤버 연산자 복사본 *오른쪽* 개체를 반환 `*this`합니다. 제어 되는 시퀀스에서 제어 된 시퀀스의 복사본으로 대체 하는 데 사용할 있습니다 *오른쪽*합니다.

### <a name="example"></a>예제

```cpp
// cliext_map_operator_as.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // assign to a new container
    Mymap c2;
    c2 = c1;
    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymap::value_type elem in c2)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
[a 1] [b 2] [c 3]
```

## <a name="op"></a> map::operator(STL/CLR)

키가 관련된 매핑된 값에 매핑됩니다.

### <a name="syntax"></a>구문

```cpp
mapped_type operator[](key_type key);
```

#### <a name="parameters"></a>매개 변수

*key*<br/>
검색할 키 값입니다.

### <a name="remarks"></a>설명

멤버 함수는 해당 순서를 가진 요소를 찾으려고 노력 *키*합니다. 를 찾으면 연결된 매핑된 값 반환 삽입이 고, 그렇지 `value_type(key, mapped_type())` 연결을 반환 합니다 (기본값) 매핑된 값입니다. 사용 하 여 것 연관 된 키를 지정 된 매핑된 값을 조회 하거나 찾을 수 없으면 키에 대 한 항목이 있는지 확인 합니다.

### <a name="example"></a>예제

```cpp
// cliext_map_operator_sub.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    System::Console::WriteLine("c1[{0}] = {1}",
        L'A', c1[L'A']);
    System::Console::WriteLine("c1[{0}] = {1}",
        L'b', c1[L'b']);

    // redisplay altered contents
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // alter mapped values and redisplay
    c1[L'A'] = 10;
    c1[L'c'] = 13;
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
c1[A] = 0
c1[b] = 2
[A 0] [a 1] [b 2] [c 3]
[A 10] [a 1] [b 2] [c 13]
```

## <a name="rbegin"></a> map:: rbegin (STL/CLR)

제어되는 역방향 시퀀스의 시작을 지정합니다.

### <a name="syntax"></a>구문

```cpp
reverse_iterator rbegin();
```

### <a name="remarks"></a>설명

멤버 함수는 제어 된 시퀀스 또는 빈 시퀀스의 시작 부분 바로 뒤의 마지막 요소를 지정 하는 역방향 반복기를 반환 합니다. 따라서 지정 된 `beginning` 역방향 시퀀스의 합니다. 지정 하는 반복기를 사용 하면는 `current` 제어 된 시퀀스를 역순으로 표시 되지만 해당 상태에 대 한 부분 제어 된 시퀀스의 길이가 변경 되 면 변경할 수 있습니다.

### <a name="example"></a>예제

```cpp
// cliext_map_rbegin.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // inspect first two items in reversed sequence
    Mymap::reverse_iterator rit = c1.rbegin();
    System::Console::WriteLine("*rbegin() = [{0} {1}]",
        rit->first, rit->second);
    ++rit;
    System::Console::WriteLine("*++rbegin() = [{0} {1}]",
        rit->first, rit->second);
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
*rbegin() = [c 3]
*++rbegin() = [b 2]
```

## <a name="reference"></a> map:: reference (STL/CLR)

요소에 대한 참조의 형식입니다.

### <a name="syntax"></a>구문

```cpp
typedef value_type% reference;
```

### <a name="remarks"></a>설명

형식 요소에 대 한 참조를 설명합니다.

### <a name="example"></a>예제

```cpp
// cliext_map_reference.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    Mymap::iterator it = c1.begin();
    for (; it != c1.end(); ++it)
        {   // get a reference to an element
        Mymap::reference ref = *it;
        System::Console::Write("[{0} {1}] ", ref->first, ref->second);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
```

## <a name="rend"></a> map:: rend (STL/CLR)

제어되는 역방향 시퀀스의 끝을 지정합니다.

### <a name="syntax"></a>구문

```cpp
reverse_iterator rend();
```

### <a name="remarks"></a>설명

멤버 함수는 제어 된 시퀀스의 시작 부분 바로 다음 가리키는 역방향 반복기를 반환합니다. 따라서 지정 된 `end` 역방향 시퀀스의 합니다. 지정 하는 반복기를 사용 하면는 `current` 제어 된 시퀀스를 역순으로 표시 되지만 해당 상태에 대 한 끝 제어 된 시퀀스의 길이가 변경 되 면 변경할 수 있습니다.

### <a name="example"></a>예제

```cpp
// cliext_map_rend.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // inspect first two items in reversed sequence
    Mymap::reverse_iterator rit = c1.rend();
    --rit;
    --rit;
    System::Console::WriteLine("*-- --rend() = [{0} {1}]",
        rit->first, rit->second);
    ++rit;
    System::Console::WriteLine("*--rend() = [{0} {1}]",
        rit->first, rit->second);
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
*-- --rend() = [b 2]
*--rend() = [a 1]
```

## <a name="reverse_iterator"></a> map:: reverse_iterator (STL/CLR)

제어되는 시퀀스에 대한 반대 반복기의 형식입니다.

### <a name="syntax"></a>구문

```
typedef T3 reverse_iterator;
```

### <a name="remarks"></a>설명

이 형식은 제어된 시퀀스에 대해 반대 반복기로 사용될 수 있는 지정되지 않은 `T3` 형식의 개체를 설명합니다.

### <a name="example"></a>예제

```cpp
// cliext_map_reverse_iterator.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]" reversed
    Mymap::reverse_iterator rit = c1.rbegin();
    for (; rit != c1.rend(); ++rit)
        System::Console::Write("[{0} {1}] ", rit->first, rit->second);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[c 3] [b 2] [a 1]
```

## <a name="size"></a> map:: size (STL/CLR)

요소 수를 계산합니다.

### <a name="syntax"></a>구문

```cpp
size_type size();
```

### <a name="remarks"></a>설명

멤버 함수는 제어되는 시퀀스의 길이를 반환합니다. 현재 제어 되는 시퀀스의에서 요소 수를 확인 하려면 사용 합니다. 모든 경우에 중요 한 여부 시퀀스 크기가 0이 아닌 참조 [map:: empty (STL/CLR)](../dotnet/map-empty-stl-clr.md)`()`합니다.

### <a name="example"></a>예제

```cpp
// cliext_map_size.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // clear the container and reinspect
    c1.clear();
    System::Console::WriteLine("size() = {0} after clearing", c1.size());

    // add elements and clear again
    c1.insert(Mymap::make_value(L'd', 4));
    c1.insert(Mymap::make_value(L'e', 5));
    System::Console::WriteLine("size() = {0} after adding 2", c1.size());
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
size() = 0 after clearing
size() = 2 after adding 2
```

## <a name="size_type"></a> map:: size_type (STL/CLR)

두 요소 사이의 부호가 있는 거리의 형식입니다.

### <a name="syntax"></a>구문

```cpp
typedef int size_type;
```

### <a name="remarks"></a>설명

형식에는 음수가 아닌 요소 수를 설명합니다.

### <a name="example"></a>예제

```cpp
// cliext_map_size_type.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // compute positive difference
    Mymap::size_type diff = 0;
    for (Mymap::iterator it = c1.begin(); it != c1.end(); ++it)
        ++diff;
    System::Console::WriteLine("end()-begin() = {0}", diff);
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
end()-begin() = 3
```

## <a name="swap"></a> map:: swap (STL/CLR)

두 컨테이너의 내용을 바꿉니다.

### <a name="syntax"></a>구문

```cpp
void swap(map<Key, Mapped>% right);
```

#### <a name="parameters"></a>매개 변수

*right*<br/>
콘텐츠와 바꿀 컨테이너입니다.

### <a name="remarks"></a>설명

멤버 함수 간에 제어 된 시퀀스를 교환 `this` 하 고 *오른쪽*합니다. 일정 한 시간에 수행 하 고 예외가 throw 됩니다. 두 컨테이너의 콘텐츠를 교환 하는 빠른 방법으로 사용 합니다.

### <a name="example"></a>예제

```cpp
// cliext_map_swap.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // construct another container with repetition of values
    Mymap c2;
    c2.insert(Mymap::make_value(L'd', 4));
    c2.insert(Mymap::make_value(L'e', 5));
    c2.insert(Mymap::make_value(L'f', 6));
    for each (Mymap::value_type elem in c2)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // swap and redisplay
    c1.swap(c2);
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    for each (Mymap::value_type elem in c2)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
[d 4] [e 5] [f 6]
[d 4] [e 5] [f 6]
[a 1] [b 2] [c 3]
```

## <a name="to_array"></a> map:: to_array (STL/CLR)

제어 되는 시퀀스를 새 배열에 복사합니다.

### <a name="syntax"></a>구문

```cpp
cli::array<value_type>^ to_array();
```

### <a name="remarks"></a>설명

멤버 함수는 제어 되는 시퀀스를 포함 하는 배열을 반환 합니다. 배열 형식에서 제어 된 시퀀스의 복사본을 가져와야 사용할 수 있습니다.

### <a name="example"></a>예제

```cpp
// cliext_map_to_array.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // copy the container and modify it
    cli::array<Mymap::value_type>^ a1 = c1.to_array();

    c1.insert(Mymap::make_value(L'd', 4));
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // display the earlier array copy
    for each (Mymap::value_type elem in a1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3] [d 4]
[a 1] [b 2] [c 3]
```

## <a name="upper_bound"></a> map:: upper_bound (STL/CLR)

지정된 된 키와 일치 하는 범위의 끝을 찾습니다.

### <a name="syntax"></a>구문

```cpp
iterator upper_bound(key_type key);
```

#### <a name="parameters"></a>매개 변수

*key*<br/>
검색할 키 값입니다.

### <a name="remarks"></a>설명

마지막 요소를 결정 하는 멤버 함수 `X` 과 순서가 있는 제어 되는 시퀀스 *키*합니다. 이러한 요소가 없으면 여부나 `X` 는 제어 된 시퀀스에서 마지막 요소 반환 [map:: end (STL/CLR)](../dotnet/map-end-stl-clr.md)`()`; 그렇지 않으면 의첫번째요소를지정하는반복기를반환`X`. 지정된 된 키와 일치 하는 제어 된 시퀀스의 요소 시퀀스의 끝을 현재 찾으려고 사용할 수 있습니다.

### <a name="example"></a>예제

```cpp
// cliext_map_upper_bound.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    System::Console::WriteLine("upper_bound(L'x')==end() = {0}",
        c1.upper_bound(L'x') == c1.end());

    Mymap::iterator it = c1.upper_bound(L'a');
    System::Console::WriteLine("*upper_bound(L'a') = [{0} {1}]",
        it->first, it->second);
    it = c1.upper_bound(L'b');
    System::Console::WriteLine("*upper_bound(L'b') = [{0} {1}]",
        it->first, it->second);
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
upper_bound(L'x')==end() = True
*upper_bound(L'a') = [b 2]
*upper_bound(L'b') = [c 3]
```

## <a name="value_comp"></a> map:: value_comp (STL/CLR)

두 요소 값에 대 한 순서 지정 대리자를 복사합니다.

### <a name="syntax"></a>구문

```cpp
value_compare^ value_comp();
```

### <a name="remarks"></a>설명

멤버 함수는 제어 되는 시퀀스를 정렬 하는 데 사용 하는 순서 지정 대리자를 반환 합니다. 두 요소 값을 비교 하는 데 사용할 수 있습니다.

### <a name="example"></a>예제

```cpp
// cliext_map_value_comp.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    Mymap::value_compare^ kcomp = c1.value_comp();

    System::Console::WriteLine("compare([L'a', 1], [L'a', 1]) = {0}",
        kcomp(Mymap::make_value(L'a', 1),
            Mymap::make_value(L'a', 1)));
    System::Console::WriteLine("compare([L'a', 1], [L'b', 2]) = {0}",
        kcomp(Mymap::make_value(L'a', 1),
            Mymap::make_value(L'b', 2)));
    System::Console::WriteLine("compare([L'b', 2], [L'a', 1]) = {0}",
        kcomp(Mymap::make_value(L'b', 2),
            Mymap::make_value(L'a', 1)));
    System::Console::WriteLine();
    return (0);
    }
```

```Output
compare([L'a', 1], [L'a', 1]) = False
compare([L'a', 1], [L'b', 2]) = True
compare([L'b', 2], [L'a', 1]) = False
```

## <a name="value_compare"></a> map:: value_compare (STL/CLR)

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
// cliext_map_value_compare.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    Mymap::value_compare^ kcomp = c1.value_comp();

    System::Console::WriteLine("compare([L'a', 1], [L'a', 1]) = {0}",
        kcomp(Mymap::make_value(L'a', 1),
            Mymap::make_value(L'a', 1)));
    System::Console::WriteLine("compare([L'a', 1], [L'b', 2]) = {0}",
        kcomp(Mymap::make_value(L'a', 1),
            Mymap::make_value(L'b', 2)));
    System::Console::WriteLine("compare([L'b', 2], [L'a', 1]) = {0}",
        kcomp(Mymap::make_value(L'b', 2),
            Mymap::make_value(L'a', 1)));
    System::Console::WriteLine();
    return (0);
    }
```

```Output
compare([L'a', 1], [L'a', 1]) = False
compare([L'a', 1], [L'b', 2]) = True
compare([L'b', 2], [L'a', 1]) = False
```

## <a name="value_type"></a> map:: value_type (STL/CLR)

요소의 형식입니다.

### <a name="syntax"></a>구문

```cpp
typedef generic_value value_type;
```

### <a name="remarks"></a>설명

이 형식은 `generic_value`의 동의어입니다.

### <a name="example"></a>예제

```cpp
// cliext_map_value_type.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]" using value_type
    for (Mymap::iterator it = c1.begin(); it != c1.end(); ++it)
        {   // store element in value_type object
        Mymap::value_type val = *it;
        System::Console::Write("[{0} {1}] ", val->first, val->second);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
```

## <a name="op_neq"></a> 연산자! = (map) (STL/CLR)

같지 않음 비교를 나열 합니다.

### <a name="syntax"></a>구문

```cpp
template<typename Key,
    typename Mapped>
    bool operator!=(map<Key, Mapped>% left,
        map<Key, Mapped>% right);
```

#### <a name="parameters"></a>매개 변수

*left*<br/>
비교할 왼쪽 컨테이너입니다.

*right*<br/>
비교할 오른쪽 컨테이너입니다.

### <a name="remarks"></a>설명

연산자 함수 반환 `!(left == right)`합니다. 테스트를 사용 하는지 여부를 *왼쪽* 동일 정렬 되지 않은 *오른쪽* 두 map의 요소 별로 비교 경우.

### <a name="example"></a>예제

```cpp
// cliext_map_operator_ne.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // assign to a new container
    Mymap c2;
    c2.insert(Mymap::make_value(L'a', 1));
    c2.insert(Mymap::make_value(L'b', 2));
    c2.insert(Mymap::make_value(L'd', 4));

    // display contents " [a 1] [b 2] [d 4]"
    for each (Mymap::value_type elem in c2)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    System::Console::WriteLine("[a b c] != [a b c] is {0}",
        c1 != c1);
    System::Console::WriteLine("[a b c] != [a b d] is {0}",
        c1 != c2);
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
[a 1] [b 2] [d 4]
[a b c] != [a b c] is False
[a b c] != [a b d] is True
```

## <a name="op_lt"></a> 연산자&lt; (map) (STL/CLR)

목록 비교 보다 작습니다.

### <a name="syntax"></a>구문

```cpp
template<typename Key,
    typename Mapped>
    bool operator<(map<Key, Mapped>% left,
        map<Key, Mapped>% right);
```

#### <a name="parameters"></a>매개 변수

*left*<br/>
비교할 왼쪽 컨테이너입니다.

*right*<br/>
비교할 오른쪽 컨테이너입니다.

### <a name="remarks"></a>설명

연산자 함수 경우 true를 반환, 가장 낮은 위치에 대 한 `i` 는 `!(right[i] < left[i])` 수도 있는 true는 `left[i] < right[i]`합니다. 를 반환 합니다 `left->size() < right->size()` 테스트에 사용할 여부 *왼쪽* 앞에 정렬 되 *오른쪽* 두 map의 요소 별로 비교 경우.

### <a name="example"></a>예제

```cpp
// cliext_map_operator_lt.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // assign to a new container
    Mymap c2;
    c2.insert(Mymap::make_value(L'a', 1));
    c2.insert(Mymap::make_value(L'b', 2));
    c2.insert(Mymap::make_value(L'd', 4));

    // display contents " [a 1] [b 2] [d 4]"
    for each (Mymap::value_type elem in c2)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    System::Console::WriteLine("[a b c] < [a b c] is {0}",
        c1 < c1);
    System::Console::WriteLine("[a b c] < [a b d] is {0}",
        c1 < c2);
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
[a 1] [b 2] [d 4]
[a b c] < [a b c] is False
[a b c] < [a b d] is True
```

## <a name="op_lteq"></a> 연산자&lt;= (map) (STL/CLR)

목록 보다 작거나 같은지 비교 합니다.

### <a name="syntax"></a>구문

```cpp
template<typename Key,
    typename Mapped>
    bool operator<=(map<Key, Mapped>% left,
        map<Key, Mapped>% right);
```

#### <a name="parameters"></a>매개 변수

*left*<br/>
비교할 왼쪽 컨테이너입니다.

*right*<br/>
비교할 오른쪽 컨테이너입니다.

### <a name="remarks"></a>설명

연산자 함수 반환 `!(right < left)`합니다. 테스트에 사용할 여부 *왼쪽* 후 정렬 되지 않은 *오른쪽* 두 map의 요소 별로 비교 경우.

### <a name="example"></a>예제

```cpp
// cliext_map_operator_le.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // assign to a new container
    Mymap c2;
    c2.insert(Mymap::make_value(L'a', 1));
    c2.insert(Mymap::make_value(L'b', 2));
    c2.insert(Mymap::make_value(L'd', 4));

    // display contents " [a 1] [b 2] [d 4]"
    for each (Mymap::value_type elem in c2)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    System::Console::WriteLine("[a b c] <= [a b c] is {0}",
        c1 <= c1);
    System::Console::WriteLine("[a b d] <= [a b c] is {0}",
        c2 <= c1);
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
[a 1] [b 2] [d 4]
[a b c] <= [a b c] is True
[a b d] <= [a b c] is False
```

## <a name="op_eq"></a> 연산자 = = (map) (STL/CLR)

같음 비교를 나열 합니다.

### <a name="syntax"></a>구문

```cpp
template<typename Key,
    typename Mapped>
    bool operator==(map<Key, Mapped>% left,
        map<Key, Mapped>% right);
```

#### <a name="parameters"></a>매개 변수

*left*<br/>
비교할 왼쪽 컨테이너입니다.

*right*<br/>
비교할 오른쪽 컨테이너입니다.

### <a name="remarks"></a>설명

연산자 함수는 시퀀스에 의해 제어 하는 경우에 true를 반환 *왼쪽* 하 고 *오른쪽* 동일한 길이 및 각 위치에 대 한 `i`, `left[i] ==` `right[i]`합니다. 테스트에 사용할 여부를 *왼쪽* 와 동일 하 게 정렬 됩니다 *오른쪽* 두 map 때 요소 별로 비교 합니다.

### <a name="example"></a>예제

```cpp
// cliext_map_operator_eq.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // assign to a new container
    Mymap c2;
    c2.insert(Mymap::make_value(L'a', 1));
    c2.insert(Mymap::make_value(L'b', 2));
    c2.insert(Mymap::make_value(L'd', 4));

    // display contents " [a 1] [b 2] [d 4]"
    for each (Mymap::value_type elem in c2)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    System::Console::WriteLine("[a b c] == [a b c] is {0}",
        c1 == c1);
    System::Console::WriteLine("[a b c] == [a b d] is {0}",
        c1 == c2);
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
[a 1] [b 2] [d 4]
[a b c] == [a b c] is True
[a b c] == [a b d] is False
```

## <a name="op_gt"></a> 연산자&gt; (map) (STL/CLR)

목록 보다 큰지 비교 합니다.

### <a name="syntax"></a>구문

```cpp
template<typename Key,
    typename Mapped>
    bool operator>(map<Key, Mapped>% left,
        map<Key, Mapped>% right);
```

#### <a name="parameters"></a>매개 변수

*left*<br/>
비교할 왼쪽 컨테이너입니다.

*right*<br/>
비교할 오른쪽 컨테이너입니다.

### <a name="remarks"></a>설명

연산자 함수 반환 `right` `<` `left`합니다. 테스트에 사용할 여부 *왼쪽* 후 정렬 되 *오른쪽* 두 map의 요소 별로 비교 경우.

### <a name="example"></a>예제

```cpp
// cliext_map_operator_gt.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // assign to a new container
    Mymap c2;
    c2.insert(Mymap::make_value(L'a', 1));
    c2.insert(Mymap::make_value(L'b', 2));
    c2.insert(Mymap::make_value(L'd', 4));

    // display contents " [a 1] [b 2] [d 4]"
    for each (Mymap::value_type elem in c2)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    System::Console::WriteLine("[a b c] > [a b c] is {0}",
        c1 > c1);
    System::Console::WriteLine("[a b d] > [a b c] is {0}",
        c2 > c1);
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
[a 1] [b 2] [d 4]
[a b c] > [a b c] is False
[a b d] > [a b c] is True
```

## <a name="op_gteq"></a> 연산자&gt;= (map) (STL/CLR)

보다 큰 목록 또는 같은지 비교 합니다.

### <a name="syntax"></a>구문

```cpp
template<typename Key,
    typename Mapped>
    bool operator>=(map<Key, Mapped>% left,
        map<Key, Mapped>% right);
```

#### <a name="parameters"></a>매개 변수

*left*<br/>
비교할 왼쪽 컨테이너입니다.

*right*<br/>
비교할 오른쪽 컨테이너입니다.

### <a name="remarks"></a>설명

연산자 함수 반환 `!(left` `<` `right)`합니다. 테스트에 사용할 여부를 *왼쪽* 하기 전에 정렬 되지 않은 *오른쪽* 두 map 때 요소 별로 비교 합니다.

### <a name="example"></a>예제

```cpp
// cliext_map_operator_ge.cpp
// compile with: /clr
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
int main()
    {
    Mymap c1;
    c1.insert(Mymap::make_value(L'a', 1));
    c1.insert(Mymap::make_value(L'b', 2));
    c1.insert(Mymap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Mymap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // assign to a new container
    Mymap c2;
    c2.insert(Mymap::make_value(L'a', 1));
    c2.insert(Mymap::make_value(L'b', 2));
    c2.insert(Mymap::make_value(L'd', 4));

    // display contents " [a 1] [b 2] [d 4]"
    for each (Mymap::value_type elem in c2)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    System::Console::WriteLine("[a b c] >= [a b c] is {0}",
        c1 >= c1);
    System::Console::WriteLine("[a b c] >= [a b d] is {0}",
        c1 >= c2);
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
[a 1] [b 2] [d 4]
[a b c] >= [a b c] is True
[a b c] >= [a b d] is False
```