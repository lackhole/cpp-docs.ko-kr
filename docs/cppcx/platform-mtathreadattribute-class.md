---
title: Platform::MTAThreadAttribute 클래스
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::MTAThreadAttribute::Equals
- VCCORLIB/Platform::MTAThreadAttribute::GetHashCode
- VCCORLIB/Platform::MTAThreadAttribute::ToString
helpviewer_keywords:
- Platform::MTAThreadAttribute Class
ms.assetid: bfc546a7-4333-4407-85b4-4721565e1f44
ms.openlocfilehash: 4564def412834ae0586292e8aa533d3b2bd0d679
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57745267"
---
# <a name="platformmtathreadattribute-class"></a>Platform::MTAThreadAttribute 클래스

애플리케이션의 스레딩 모델이 MTA(다중 스레드 아파트)임을 나타냅니다.

## <a name="syntax"></a>구문

```
public ref class MTAThreadAttribute sealed : Attribute
```

### <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[MTAThreadAttribute 생성자 1](#ctor) 생성자|클래스의 새 인스턴스를 초기화합니다.|

### <a name="public-methods"></a>Public 메서드

MTAThreadAttribute 특성에서 상속 [platform:: object 클래스](../cppcx/platform-object-class.md)합니다. MTAThreadAttribute도 다음 멤버를 오버로드하거나 포함합니다.

|이름|설명|
|----------|-----------------|
|[MTAThreadAttribute::Equals](#equals)|지정한 개체와 현재 개체가 같은지 여부를 확인합니다.|
|[MTAThreadAttribute::GetHashCode](#gethashcode)|이 인스턴스의 해시 코드를 반환합니다.|
|[MTAThreadAttribute::ToString](#tostring)|현재 개체를 나타내는 문자열을 반환합니다.|

## <a name="inheritance-hierarchy"></a>상속 계층

`Platform`

### <a name="requirements"></a>요구 사항

**메타데이터:** platform.winmd

**네임스페이스:** 플랫폼

## <a name="ctor"></a> MTAThreadAttribute 생성자

MTAThreadAttribute 클래스의 새 인스턴스를 초기화합니다.

### <a name="syntax"></a>구문

```cpp
public:MTAThreadAttribute();
```

## <a name="equals"></a> MTAThreadAttribute::Equals

지정한 개체와 현재 개체가 같은지 여부를 확인합니다.

### <a name="syntax"></a>구문

```cpp
public:virtual override bool Equals( Object^ obj );
```

### <a name="parameters"></a>매개 변수

*obj*<br/>
비교할 개체입니다.

### <a name="return-value"></a>반환 값

**true 이면** 개체가 같으면이 고, 그렇지 않으면 **false**합니다.

## <a name="gethashcode"></a> MTAThreadAttribute::GetHashCode

이 인스턴스의 해시 코드를 반환합니다.

### <a name="syntax"></a>구문

```cpp
public:int GetHashCode();
```

### <a name="return-value"></a>반환 값

이 인스턴스의 해시 코드입니다.

## <a name="tostring"></a> MTAThreadAttribute::ToString

현재 개체를 나타내는 문자열을 반환합니다.

### <a name="syntax"></a>구문

```cpp
public:String^ ToString();
```

### <a name="return-value"></a>반환 값

현재 개체를 나타내는 문자열입니다.

## <a name="see-also"></a>참고자료

[플랫폼 Namespace](platform-namespace-c-cx.md)
