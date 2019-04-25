---
title: Platform::Collections::UnorderedMap 클래스
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- collection/Platform::Collections::UnorderedMap
ms.assetid: dc84f261-b13c-4c0a-9b57-30dcb9e3065e
ms.openlocfilehash: 7790b363ef3f30b0ad0602568190ab443a2c1401
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62161734"
---
# <a name="platformcollectionsunorderedmap-class"></a>Platform::Collections::UnorderedMap 클래스

키-값 쌍의 컬렉션인 순서가 지정되지 않은 *맵*을 나타냅니다.

## <a name="syntax"></a>구문

```cpp
template <
   typename K,
   typename V,
   typename C = std::equal_to<K>
>
ref class Map sealed;
```

#### <a name="parameters"></a>매개 변수

*K*<br/>
키/값 쌍의 키 형식입니다.

*V*<br/>
키/값 쌍의 값 형식입니다.

*C*<br/>
두 요소 값을 정렬 키로 비교하여 맵에서 해당 상대 순서를 확인할 수 있는 함수 개체를 제공하는 형식입니다. 기본적으로 [std:: equal_to\<K >](../standard-library/equal-to-struct.md)합니다.

### <a name="remarks"></a>설명

허용되는 형식은 다음과 같습니다.

- 정수

- 인터페이스 클래스 ^

- public ref 클래스 ^

- value struct

- public enum 클래스

**UnorderedMap** 에 대 한 래퍼는 기본적으로 [std:: unordered_map](../standard-library/unordered-map-class.md) Windows 런타임 형식의 storage를 지 원하는 합니다. 것을의 구체적인 구현을 합니다 [Windows::Foundation::Collections::IMap](/uwp/api/Windows.Foundation.Collections.IMap_K_V_) 및 [IObservableMap](/uwp/api/Windows.Foundation.Collections.IObservableMap_K_V_) 공용 전반에서 전달 되는 Windows 런타임 인터페이스. 공용 반환 값 또는 매개 변수에서 `Platform::Collections::UnorderedMap` 형식을 사용하려고 하면 컴파일러 오류 C3986이 발생합니다. 매개 변수나 반환 값 형식을 [Windows::Foundation::Collections::IMap](/uwp/api/Windows.Foundation.Collections.IMap_K_V_)으로 변경하여 오류를 수정할 수 있습니다.

자세한 내용은 [컬렉션](../cppcx/collections-c-cx.md)합니다.

### <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[UnorderedMap::UnorderedMap](#ctor)|Map 클래스의 새 인스턴스를 초기화합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[UnorderedMap::Clear](#clear)|현재 Map 개체에서 모든 키/값 쌍을 제거합니다.|
|[UnorderedMap::First](#first)|맵의 첫 번째 요소를 지정하는 반복기를 반환합니다.|
|[UnorderedMap::GetView](#getview)|현재 Map의 읽기 전용 뷰, 즉 Platform::Collections::UnorderedMapView 클래스를 반환합니다.|
|[UnorderedMap::HasKey](#haskey)|현재 Map에 지정한 키가 들어 있는지 여부를 확인합니다.|
|[UnorderedMap::Insert](#insert)|지정한 키/값 쌍을 현재 Map 개체에 추가합니다.|
|[UnorderedMap::Lookup](#lookup)|현재 Map 개체의 지정된 키에 있는 요소를 검색합니다.|
|[UnorderedMap::Remove](#remove)|지정한 키/값 쌍을 현재 Map 개체에서 삭제합니다.|
|[UnorderedMap::Size](#size)|현재 Map 개체의 요소 수를 반환합니다.|

### <a name="events"></a>이벤트

|||
|-|-|
|이름|설명|
|[Map:: mapchanged](#mapchanged) 이벤트|Map이 변경될 때 발생합니다.|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`UnorderedMap`

### <a name="requirements"></a>요구 사항

**헤더:** collection.h

**네임스페이스:** Platform::Collections

## <a name="clear"></a>  Unorderedmap:: Clear 메서드

현재 UnorderedMap 개체에서 모든 키-값 쌍을 제거합니다.

### <a name="syntax"></a>구문

```cpp
virtual void Clear();
```

## <a name="first"></a>  Unorderedmap:: First 메서드

첫 번째를 지정 하는 반복기를 반환 [Windows::Foundation::Collections::IKeyValuePair\<K, V >](/uwp/api/Windows.Foundation.Collections.IKeyValuePair_K_V_) unordered map의 요소입니다.

### <a name="syntax"></a>구문

```cpp
virtual Windows::Foundation::Collections::IIterator<
   Windows::Foundation::Collections::IKeyValuePair<K, V>^>^
   First();
```

### <a name="return-value"></a>반환 값

맵의 첫 번째 요소를 지정하는 반복기입니다.

### <a name="remarks"></a>설명

First ()에서 반환 된 반복기를 보유 하는 편리한 방법을 사용 하 여 선언 된 변수에 반환 값을 할당 하는 것은 **자동** 형식 추론 키워드입니다. 예를 들어, `auto x = myUnorderedMap->First();`을 입력합니다.

## <a name="getview"></a>  Unorderedmap:: Getview 메서드

현재 UnorderedMap의 읽기 전용 보기를 반환합니다. 즉, 한 [Platform::Collections::UnorderedMapView 클래스](../cppcx/platform-collections-unorderedmapview-class.md) 구현 하는 [Windows::Foundation::Collections::IMapView::IMapView]/uwp/api/Windows.Foundation.Collections.IMapView_K_V_) 인터페이스입니다.

### <a name="syntax"></a>구문

```cpp
Windows::Foundation::Collections::IMapView<K, V>^ GetView();
```

### <a name="return-value"></a>반환 값

`UnorderedMapView` 개체입니다.

## <a name="haskey"></a>  Unorderedmap:: Haskey 메서드

현재 UnorderedMap에 지정한 키가 들어 있는지 여부를 확인합니다.

### <a name="syntax"></a>구문

```cpp
bool HasKey(
   K key
);
```

### <a name="parameters"></a>매개 변수

*key*<br/>
UnorderedMap 요소를 찾는 데 사용되는 키입니다. 유형의 *키* 형식 이름 *K*합니다.

### <a name="return-value"></a>반환 값

**true 이면** 이 고, 그렇지 않으면 키가 없으면 **false**합니다.

## <a name="insert"></a>  UnorderedMap::Insert Method

지정한 키-값 쌍을 현재 UnorderedMap 개체에 추가합니다.

### <a name="syntax"></a>구문

```cpp
virtual bool Insert(
   K key,
   V value
);
```

### <a name="parameters"></a>매개 변수

*key*<br/>
키-값 쌍의 키 부분입니다. 유형의 *키* 형식 이름 *K*합니다.

*값*<br/>
키-값 쌍의 값 부분입니다. 유형의 *값* 형식 이름 *V*합니다.

### <a name="return-value"></a>반환 값

**true** 현재 Map의 기존 요소 키와 일치 하는 경우 *키* 로 설정 되어 해당 요소의 값 부분이 *값*합니다. **false** 일치 하는 현재 Map의 기존 요소가 *키* 하며 *키* 및 *값* 매개 변수는 키-값 쌍으로 수행 되며 그런 다음에 추가 합니다 현재 UnorderedMap 합니다.

## <a name="lookup"></a>  Unorderedmap:: Lookup 메서드

K 형식의 지정된 키와 연결된 V 형식의 값을 검색합니다.

### <a name="syntax"></a>구문

```cpp
V Lookup(
   K key
);
```

### <a name="parameters"></a>매개 변수

*key*<br/>
UnorderedMap에서 요소를 찾는 데 사용되는 키입니다. 유형의 *키* 형식 이름 *K*합니다.

### <a name="return-value"></a>반환 값

함께 사용 되는 값을 *키*합니다. 반환 값의 형식은 typename *V*합니다.

## <a name="mapchanged"></a>  UnorderedMap::MapChanged

맵에서 항목이 삽입되거나 제거될 때 발생합니다.

### <a name="syntax"></a>구문

```cpp
event Windows::Foundation::Collections::MapChangedEventHandler<K,V>^ MapChanged;
```

### <a name="property-valuereturn-value"></a>속성 값/반환 값

A [MapChangedEventHandler\<K, V >](/uwp/api/windows.foundation.collections.mapchangedeventhandler) 발생 한 변경 내용 유형의 이벤트를 발생 시킨 개체에 대 한 정보를 포함 하는 합니다. 참고 항목 [IMapChangedEventArgs\<K >](/uwp/api/Windows.Foundation.Collections.IMapChangedEventArgs_K_) 하 고 [CollectionChange 열거형](/uwp/api/windows.foundation.collections.collectionchange)합니다.

## <a name="net-framework-equivalent"></a>.NET Framework의 해당 값

C# 또는 Visual Basic 프로젝트 IMap 하는 Windows 런타임 앱\<K, V > IDictionary로\<K, V >.

## <a name="remove"></a>  Unorderedmap:: Remove 메서드

지정한 키-값 쌍을 UnorderedMap 개체에서 삭제합니다.

### <a name="syntax"></a>구문

```cpp
virtual void Remove(
   K key);
```

### <a name="parameters"></a>매개 변수

*key*<br/>
키-값 쌍의 키 부분입니다. 유형의 *키* 형식 이름 *K*합니다.

## <a name="size"></a>  Unorderedmap:: Size 메서드

개수를 반환 [Windows::Foundation::Collections::IKeyValuePair\<K, V >](/uwp/api/Windows.Foundation.Collections.IKeyValuePair_K_V_) UnorderedMap에 있는 요소입니다.

### <a name="syntax"></a>구문

```cpp
virtual property unsigned int Size;
```

### <a name="return-value"></a>반환 값

UnorderedMap의 요소 수입니다.

## <a name="ctor"></a>  UnorderedMap::UnorderedMap 생성자

UnorderedMap 클래스의 새 인스턴스를 초기화합니다.

### <a name="syntax"></a>구문

```cpp
UnorderedMap();

explicit UnorderedMap(
    size_t n
    );

UnorderedMap(
    size_t n,
    const H& h
    );

UnorderedMap(
    size_t n,
    const H& h,
    const P& p
    );

explicit UnorderedMap(
    const std::unordered_map<K, V, H, P>& m
    );

explicit UnorderedMap(
    std::unordered_map<K, V, H, P>&& m
    );

template <typename InIt>
UnorderedMap(
    InIt first,
    InIt last
    );

template <typename InIt>
UnorderedMap(
    InIt first,
    InIt last,
    size_t n
    );

template <typename InIt>
UnorderedMap(
    InIt first,
    InIt last,
    size_t n,
    const H& h
    );

template <typename InIt>
UnorderedMap(
    InIt first,
    InIt last,
    size_t n,
    const H& h,
    const P& p
    );

UnorderedMap(
    std::initializer_list< std::pair<const K, V>> il
    );

UnorderedMap(
    std::initializer_list< std::pair<const K, V>> il,
    size_t n
    );

UnorderedMap(
    std::initializer_list< std::pair<const K, V>> il,
    size_t n,
    const H& h
    );

UnorderedMap(
    std::initializer_list< std::pair<const K, V>> il,
    size_t n,
    const H& h,
    const P& p
    );
```

### <a name="parameters"></a>매개 변수

*InIt*<br/>
현재 UnorderedMap의 형식 이름입니다.

*P*<br/>
같은지 여부를 확인하기 위해 두 키를 비교할 수 있는 함수 개체입니다. 이 매개 변수의 기본값은 [std:: equal_to\<K >](../standard-library/equal-to-struct.md)합니다.

*H*<br/>
키에 대한 해시 값을 생성하는 함수 개체입니다. 이 매개 변수의 기본값은 [해시 클래스 1](../standard-library/hash-class.md) 키 형식에 대 한 클래스를 지원 합니다.

*m*<br/>
참조 또는 [Lvalue 및 Rvalue](../cpp/lvalues-and-rvalues-visual-cpp.md) 에 [std:: unordered_map](../standard-library/unordered-map-class.md) 현재 UnorderedMap을 초기화 하는 데 사용 되는 합니다.

*il*<br/>
A [std:: initializer_list](../standard-library/initializer-list-class.md) 의 [std:: pair](../standard-library/pair-structure.md) map를 초기화 하는 데 사용 되는 개체입니다.

*first*<br/>
현재 UnorderedMap을 초기화하는 데 사용되는 요소 범위에서 첫 번째 요소의 입력 반복기입니다.

*last*<br/>
현재 UnorderedMap을 초기화하는 데 사용되는 요소 범위 다음의 첫 번째 요소의 입력 반복기입니다.

## <a name="see-also"></a>참고자료

[플랫폼 Namespace](platform-namespace-c-cx.md)<br/>
[Platform::Collections 네임스페이스](../cppcx/platform-collections-namespace.md)<br/>
[Platform::Collections::Map 클래스](../cppcx/platform-collections-map-class.md)<br/>
[Platform::Collections::UnorderedMapView 클래스](../cppcx/platform-collections-unorderedmapview-class.md)<br/>
[컬렉션](../cppcx/collections-c-cx.md)<br/>
[C++로 Windows Runtime 구성 요소 만들기](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)
