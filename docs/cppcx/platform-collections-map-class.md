---
title: Platform::Collections::Map 클래스
ms.date: 01/18/2018
ms.topic: reference
f1_keywords:
- COLLECTION/Platform::Collections::Map::Map
- COLLECTION/Platform::Collections::Map::Clear
- COLLECTION/Platform::Collections::Map::First
- COLLECTION/Platform::Collections::Map::GetView
- COLLECTION/Platform::Collections::Map::HasKey
- COLLECTION/Platform::Collections::Map::Insert
- COLLECTION/Platform::Collections::Map::Lookup
- COLLECTION/Platform::Collections::Map::Remove
- COLLECTION/Platform::Collections::Map::Size
helpviewer_keywords:
- Map Class (C++/Cx)
ms.assetid: 2b8cf968-1167-4898-a149-1195b32c1785
ms.openlocfilehash: cbe0b5e422c05cee46bff85e816ecc726c667749
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57745170"
---
# <a name="platformcollectionsmap-class"></a>Platform::Collections::Map 클래스

키/값 쌍의 컬렉션인 *맵*을 나타냅니다.

## <a name="syntax"></a>구문

```cpp
template <
   typename K,
   typename V,
   typename C = std::less<K>>
ref class Map sealed;
```

### <a name="parameters"></a>매개 변수

*K*<br/>
키/값 쌍의 키 형식입니다.

*V*<br/>
키/값 쌍의 값 형식입니다.

*C*<br/>
두 요소 값을 정렬 키로 비교하여 맵에서 해당 상대 순서를 확인할 수 있는 함수 개체를 제공하는 형식입니다. 기본적으로 [std:: less\<K >](../standard-library/less-struct.md)합니다.

*__is_valid_winrt_type()* 형식의 유효성을 검사 하는 컴파일러에서 생성 된 함수 *K* 하 고 *V* 형식을 Map에 저장할 수 없을 경우 친숙 한 오류 메시지를 제공 합니다.

### <a name="remarks"></a>설명

허용되는 형식은 다음과 같습니다.

- 정수

- 인터페이스 클래스 ^

- public ref 클래스 ^

- value struct

- public enum 클래스

Map은 기본적으로 [std::map](../standard-library/map-class.md)에 대한 래퍼입니다. 구체적인 c + + 구현 된 [Windows::Foundation::Collections::IMap < Windows::Foundation::Collections::IKeyValuePair\<K, V >>](/uwp/api/Windows.Foundation.Collections.IMap_K_V_) 하 고 [IObservableMap](/uwp/api/Windows.Foundation.Collections.IObservableMap_K_V_) Windows 런타임 인터페이스를 공용 전반에서 전달 되는 형식입니다. 공용 반환 값 또는 매개 변수에서 `Platform::Collections::Map` 형식을 사용하려고 하면 컴파일러 오류 C3986이 발생합니다. 매개 변수 또는 반환 값의 형식을 변경 하 여 오류를 해결할 수 있습니다 [Windows::Foundation::Collections::IMap\<K, V >](/uwp/api/Windows.Foundation.Collections.IMap_K_V_)합니다.

자세한 내용은 [컬렉션](../cppcx/collections-c-cx.md)합니다.

### <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[Map::Map](#ctor)|Map 클래스의 새 인스턴스를 초기화합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[Map::Clear](#clear)|현재 Map 개체에서 모든 키/값 쌍을 제거합니다.|
|[Map::First](#first)|맵의 첫 번째 요소를 지정하는 반복기를 반환합니다.|
|[Map::GetView](#getview)|현재 Map의 읽기 전용 보기, 즉 [Platform::Collections::MapView Class](../cppcx/platform-collections-mapview-class.md)를 반환합니다.|
|[Map::HasKey](#haskey)|현재 Map에 지정한 키가 들어 있는지 여부를 확인합니다.|
|[Map::Insert](#insert)|지정한 키/값 쌍을 현재 Map 개체에 추가합니다.|
|[Map::Lookup](#lookup)|현재 Map 개체의 지정된 키에 있는 요소를 검색합니다.|
|[Map::Remove](#remove)|지정한 키/값 쌍을 현재 Map 개체에서 삭제합니다.|
|[Map::Size](#size)|현재 Map 개체의 요소 수를 반환합니다.|

### <a name="events"></a>이벤트

|||
|-|-|
|이름|설명|
|[Map::MapChanged](#mapchanged-event.md) `event`|Map이 변경될 때 발생합니다.|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`Map`

### <a name="requirements"></a>요구 사항

**헤더:** collection.h

**네임스페이스:** Platform::Collections

## <a name="clear"></a>  Map:: clear 메서드

현재 Map 개체에서 모든 키/값 쌍을 제거합니다.

### <a name="syntax"></a>구문

```cpp
virtual void Clear();
```

## <a name="first"></a>  Map:: first 메서드

맵의 첫 번째 요소를 지정하는 반복기 또는 `nullptr`(맵이 비어 있는 경우)을 반환합니다.

### <a name="syntax"></a>구문

```cpp
virtual Windows::Foundation::Collections::IIterator<
Windows::Foundation::Collections::IKeyValuePair<K, V>^>^ First();
```

### <a name="return-value"></a>반환 값

맵의 첫 번째 요소를 지정하는 반복기입니다.

### <a name="remarks"></a>설명

First ()에서 반환 된 반복기를 보유 하는 편리한 방법을 사용 하 여 선언 된 변수에 반환 값을 할당 하는 것은 **자동** 형식 추론 키워드입니다. 예를 들어, `auto x = myMap->First();`을 입력합니다.

## <a name="getview"></a>  Map:: getview 메서드

현재 Map의 읽기 전용 보기를 반환합니다. 즉,을 [Platform::Collections::MapView 클래스](../cppcx/platform-collections-mapview-class.md)를 구현 하는 합니다 [Windows::Foundation::Collections::IMapView\<K, V >] / uwp/api/Windows.Foundation.Collections.IMapView_K_V_) 인터페이스입니다.

### <a name="syntax"></a>구문

```cpp
Windows::Foundation::Collections::IMapView<K, V>^ GetView();
```

### <a name="return-value"></a>반환 값

`MapView` 개체입니다.

## <a name="haskey"></a>  Map:: haskey 메서드

현재 Map에 지정한 키가 들어 있는지 여부를 확인합니다.

### <a name="syntax"></a>구문

```cpp
bool HasKey(K key);
```

### <a name="parameters"></a>매개 변수

*key*<br/>
Map 요소를 찾는 데 사용되는 키입니다. 유형의 *키* 형식 이름 *K*합니다.

### <a name="return-value"></a>반환 값

**true 이면** 이 고, 그렇지 않으면 키가 없으면 **false**합니다.

## <a name="insert"></a>  Map:: insert 메서드

지정한 키/값 쌍을 현재 Map 개체에 추가합니다.

### <a name="syntax"></a>구문

```cpp
virtual bool Insert(K key, V value);
```

### <a name="parameters"></a>매개 변수

*key*<br/>
키-값 쌍의 키 부분입니다. 유형의 *키* 형식 이름 *K*합니다.

*값*<br/>
키-값 쌍의 값 부분입니다. 유형의 *값* 형식 이름 *V*합니다.

### <a name="return-value"></a>반환 값

**true** 현재 Map의 기존 요소 키와 일치 하는 경우 *키* 로 설정 되어 해당 요소의 값 부분이 *값*합니다. **false** 일치 하는 현재 Map의 기존 요소가 *키* 하며 *키* 및 *값* 매개 변수는 키-값 쌍으로 수행 되며 그런 다음에 추가 합니다 현재 Map입니다.

## <a name="lookup"></a>  Map:: lookup 메서드

K 형식의 지정된 키(해당 키가 있는 경우)와 연결된 V 형식의 값을 검색합니다.

### <a name="syntax"></a>구문

```cpp
V Lookup(K key);
```

### <a name="parameters"></a>매개 변수

*key*<br/>
지도에서 요소를 찾는 데 사용되는 키입니다. 유형의 *키* 형식 이름 *K*합니다.

### <a name="return-value"></a>반환 값

함께 사용 되는 값을 *키*합니다. 반환 값의 형식은 typename *V*합니다.

### <a name="remarks"></a>설명

키가 없으면 다음을 [platform:: outofboundsexception](../cppcx/platform-outofboundsexception-class.md) throw 됩니다.

## <a name="ctor"></a>  Map:: map 생성자

Map 클래스의 새 인스턴스를 초기화합니다.

### <a name="syntax"></a>구문

```cpp
explicit Map(const C& comp = C());
explicit Map(const StdMap& m);
explicit Map(StdMap&& m ;
template <typename InIt>
Map(
   InItfirst,
   InItlast,
   const C& comp = C());
```

### <a name="parameters"></a>매개 변수

*InIt*<br/>
현재 Map의 형식 이름입니다.

*comp*<br/>
두 요소 값을 정렬 키로 비교하여 맵에서 해당 상대 순서를 확인할 수 있는 함수 개체를 제공하는 형식입니다.

*m*<br/>
참조 또는 [Lvalue 및 Rvalue](../cpp/lvalues-and-rvalues-visual-cpp.md) 에 `map Class` 현재 Map를 초기화 하는 데 사용 되는 합니다.

*first*<br/>
현재 Map를 초기화하는 데 사용되는 요소 범위에서 첫 번째 요소의 입력 반복기입니다.

*last*<br/>
현재 Map를 초기화하는 데 사용되는 요소 범위 다음의 첫 번째 요소의 입력 반복기입니다.

## <a name="mapchanged"></a>  Map::MapChanged Event

맵에서 항목이 삽입되거나 제거될 때 발생합니다.

### <a name="syntax"></a>구문

```cpp
event Windows::Foundation::Collections::MapChangedEventHandler<K,V>^ MapChanged;
```

### <a name="property-valuereturn-value"></a>속성 값/반환 값

A [MapChangedEventHandler\<K, V >](/uwp/api/windows.foundation.collections.mapchangedeventhandler) 발생 한 변경 내용 유형의 이벤트를 발생 시킨 개체에 대 한 정보를 포함 하는 합니다. 참고 항목 [IMapChangedEventArgs\<K >](/uwp/api/Windows.Foundation.Collections.IMapChangedEventArgs_K_) 하 고 [CollectionChange 열거형](/uwp/api/windows.foundation.collections.collectionchange)합니다.

## <a name="net-framework-equivalent"></a>.NET Framework의 해당 값

C# 또는 Visual Basic을 사용 하는 Windows 런타임 앱 프로젝트 IMap\<K, V > IDictionary로\<K, V >.

## <a name="remove"></a>  Map:: remove 메서드

지정한 키/값 쌍을 현재 Map 개체에서 삭제합니다.

### <a name="syntax"></a>구문

```cpp
virtual void Remove(K key);
```

### <a name="parameters"></a>매개 변수

*key*<br/>
키-값 쌍의 키 부분입니다. 유형의 *키* 형식 이름 *K*합니다.

## <a name="size"></a>  Map:: size 메서드

개수를 반환 [Windows::Foundation::Collections::IKeyValuePair\<K, V >](/uwp/api/Windows.Foundation.Collections.IKeyValuePair_K_V_) Map의 요소입니다.

### <a name="syntax"></a>구문

```cpp
virtual property unsigned int Size;
```

### <a name="return-value"></a>반환 값

Map의 요소 수입니다.

## <a name="see-also"></a>참고자료

[플랫폼 Namespace](platform-namespace-c-cx.md)<br/>
[C++로 Windows Runtime 구성 요소 만들기](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)
