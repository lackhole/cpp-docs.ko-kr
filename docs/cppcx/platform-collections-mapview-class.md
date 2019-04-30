---
title: Platform::Collections::MapView 클래스
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- COLLECTION/Platform::Collections::MapView::MapView
- COLLECTION/Platform::Collections::MapView::First
- COLLECTION/Platform::Collections::MapView::HasKey
- COLLECTION/Platform::Collections::MapView::Lookup
- COLLECTION/Platform::Collections::MapView::Size
- COLLECTION/Platform::Collections::MapView::Split
helpviewer_keywords:
- MapView Class
ms.assetid: 9577dde7-f599-43c6-b1e4-7d653706fd62
ms.openlocfilehash: 1e38865f1d43edac4fc895052f1ea1b5a54a34ab
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62161714"
---
# <a name="platformcollectionsmapview-class"></a>Platform::Collections::MapView 클래스

읽기 전용 보기를 키/값 쌍의 컬렉션인 *맵*으로 나타냅니다.

## <a name="syntax"></a>구문

```
template <
   typename K,
   typename V,
   typename C = ::std::less<K>>
ref class MapView sealed;
```

#### <a name="parameters"></a>매개 변수

*K*<br/>
키/값 쌍의 키 형식입니다.

*V*<br/>
키/값 쌍의 값 형식입니다.

*C*<br/>
두 요소 값을 정렬 키로 비교하여 MapView에서 해당 상대 순서를 확인할 수 있는 함수 개체를 제공하는 형식입니다. 기본적으로 [std:: less\<K >](../standard-library/less-struct.md)합니다.

### <a name="remarks"></a>설명

MapView는 구체적인 C++ 구현의 합니다 [Windows::Foundation::Collections::IMapView \<K, V >](/uwp/api/Windows.Foundation.Collections.IMapView_K_V_) 응용 프로그램 이진 인터페이스 ABI ()를 통해 전달 되는 인터페이스입니다. 자세한 내용은 [컬렉션(C++/CX)](../cppcx/collections-c-cx.md)을 참조하세요.

### <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[MapView::MapView](#ctor)|MapView 클래스의 새 인스턴스를 초기화합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[MapView::First](#first)|맵 뷰의 첫 번째 요소로 초기화하는 반복기를 반환합니다.|
|[MapView::HasKey](#haskey)|현재 MapView에 지정한 키가 들어 있는지 여부를 확인합니다.|
|[MapView::Lookup](#lookup)|현재 MapView 개체의 지정된 키에 있는 요소를 검색합니다.|
|[MapView::Size](#size)|현재 MapView 개체의 요소 수를 반환합니다.|
|[MapView::Split](#split)|원래 MapView 개체를 두 개의 MapView 개체로 분할합니다.|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`MapView`

### <a name="requirements"></a>요구 사항

**헤더:** collection.h

**네임스페이스:** Platform::Collections

## <a name="first"></a> Mapview:: First 메서드

맵 뷰의 첫 번째 요소를 지정하는 반복기를 반환합니다.

### <a name="syntax"></a>구문

```
virtual Windows::Foundation::Collections::IIterator<
   Windows::Foundation::Collections::IKeyValuePair<K, V>^>^ First();
```

### <a name="return-value"></a>반환 값

맵 뷰의 첫 번째 요소를 지정하는 반복기입니다.

### <a name="remarks"></a>설명

First ()에서 반환 된 반복기를 보유 하는 편리한 방법을 사용 하 여 선언 된 변수에 반환 값을 할당 하는 것은 **자동** 형식 추론 키워드입니다. 예를 들어, `auto x = myMapView->First();`을 입력합니다.

## <a name="haskey"></a>  Mapview:: Haskey 메서드

현재 MapView에 지정한 키가 들어 있는지 여부를 확인합니다.

### <a name="syntax"></a>구문

```

bool HasKey(K key);
```

### <a name="parameters"></a>매개 변수

*key*<br/>
MapView 요소를 찾는 데 사용되는 키입니다. 유형의 *키* 형식 이름 *K*합니다.

### <a name="return-value"></a>반환 값

**true 이면** 이 고, 그렇지 않으면 키가 없으면 **false**합니다.

##  <a name="lookup"></a> Mapview:: Lookup 메서드

K 형식의 지정된 키와 연결된 V 형식의 값을 검색합니다.

### <a name="syntax"></a>구문

```
V Lookup(K key);
```

### <a name="parameters"></a>매개 변수

*key*<br/>
MapView에서 요소를 찾는 데 사용되는 키입니다. 유형의 `key` typename 됩니다 *K*합니다.

### <a name="return-value"></a>반환 값

`key`와 쌍을 이루는 값입니다. 반환 값의 형식은 typename *V*합니다.

##  <a name="ctor"></a> Mapview:: Mapview 생성자

MapView 클래스의 새 인스턴스를 초기화합니다.

### <a name="syntax"></a>구문

```cpp
explicit MapView(const C& comp = C());

explicit MapView(const ::std::map<K, V, C>& m);

explicit MapView(std::map<K, V, C>&& m);

template <typename InIt> MapView(
    InIt first,
    InIt last,
    const C& comp = C());

MapView(
    ::std::initializer_list<std::pair<const K, V>> il,
    const C& comp = C());
```

### <a name="parameters"></a>매개 변수

*InIt*<br/>
현재 MapView의 형식 이름입니다.

*comp*<br/>
두 요소 값을 정렬 키로 비교하여 MapView에서 해당 상대 순서를 확인할 수 있는 함수 개체입니다.

*m*<br/>
참조 또는 [Lvalue 및 Rvalue](../cpp/lvalues-and-rvalues-visual-cpp.md) 에 `map Class` 현재 MapView를 초기화 하는 데 사용 되는 합니다.

*first*<br/>
현재 MapView를 초기화하는 데 사용되는 요소 범위에서 첫 번째 요소의 입력 반복기입니다.

*last*<br/>
현재 MapView를 초기화하는 데 사용되는 요소 범위 다음의 첫 번째 요소의 입력 반복기입니다.

*il*<br/>
A [std:: initializer_list < std:: pair\<K, V >>](../standard-library/initializer-list-class.md) 요소가 MapView에 삽입 됩니다.

##  <a name="size"></a> Mapview:: Size 메서드

현재 MapView 개체의 요소 수를 반환합니다.

### <a name="syntax"></a>구문

```cpp
virtual property unsigned int Size;
```

### <a name="return-value"></a>반환 값

현재 MapView의 요소 수입니다.

##  <a name="split"></a> Mapview:: Split 메서드

현재 MapView 개체를 두 개의 MapView 개체로 분할합니다. 이 메서드는 작동하지 않습니다.

### <a name="syntax"></a>구문

```
void Split(
   Windows::Foundation::Collections::IMapView<
                         K, V>^ * firstPartition,
   Windows::Foundation::Collections::IMapView<
                         K, V>^ * secondPartition);
```

### <a name="parameters"></a>매개 변수

*firstPartition*<br/>
원래 MapView 개체의 첫 번째 부분입니다.

*secondPartition*<br/>
원래 MapView 개체의 두 번째 부분입니다.

### <a name="remarks"></a>설명

이 메서드는 작동하지 않으며, 아무 작업도 수행하지 않습니다.

## <a name="see-also"></a>참고자료

[플랫폼 Namespace](platform-namespace-c-cx.md)
