---
title: Platform::STAThreadAttribute 클래스
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- COLLECTION/Platform::Platform
- COLLECTION/Platform::Platform::STAThreadAttribute constructor 1
- COLLECTION/Platform::Platform::STAThreadAttribute::Equals
- COLLECTION/Platform::Platform::STAThreadAttribute::GetHashCode
- COLLECTION/Platform::Platform::STAThreadAttribute::ToString
helpviewer_keywords:
- Platform::STAThreadAttribute Class
ms.assetid: f97960fc-e673-4d9e-910a-54c8415411c4
ms.openlocfilehash: 05fb2879839c504f49f56e25ffe28329aa969c69
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62183381"
---
# <a name="platformstathreadattribute-class"></a>Platform::STAThreadAttribute 클래스

애플리케이션에 대한 스레딩 모델이 STA(단일 스레드 아파트)임을 나타냅니다.

## <a name="syntax"></a>구문

```
public ref class STAThreadAttribute sealed : Attribute
```

### <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[STAThreadAttribute 생성자 1](#ctor)|클래스의 새 인스턴스를 초기화합니다.|

### <a name="public-methods"></a>Public 메서드

STAThreadAttribute 특성에서 상속 [platform:: object 클래스](../cppcx/platform-object-class.md)합니다. STAThreadAttribute도 다음 멤버를 오버로드하거나 포함합니다.

|이름|설명|
|----------|-----------------|
|[STAThreadAttribute::Equals](#equals)|지정한 개체와 현재 개체가 같은지 여부를 확인합니다.|
|[STAThreadAttribute::GetHashCode](#gethashcode)|이 인스턴스의 해시 코드를 반환합니다.|
|[STAThreadAttribute::ToString](#tostring)|현재 개체를 나타내는 문자열을 반환합니다.|

## <a name="inheritance-hierarchy"></a>상속 계층

`Platform`

### <a name="requirements"></a>요구 사항

**헤더:** collection.h

**네임스페이스:** 플랫폼

## <a name="ctor"></a> STAThreadAttribute constructor

STAThreadAttribute 클래스의 새 인스턴스를 초기화합니다.

### <a name="syntax"></a>구문

```cpp
public:STAThreadAttribute();
```

## <a name="equals"></a> STAThreadAttribute::Equals

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

## <a name="gethashcode"></a> STAThreadAttribute::GetHashCode

이 인스턴스의 해시 코드를 반환합니다.

### <a name="syntax"></a>구문

```cpp
public:int GetHashCode();
```

### <a name="return-value"></a>반환 값

이 인스턴스의 해시 코드입니다.

## <a name="tostring"></a> STAThreadAttribute::ToString

현재 개체를 나타내는 문자열을 반환합니다.

### <a name="syntax"></a>구문

```cpp
public:String^ ToString();
```

### <a name="return-value"></a>반환 값

현재 개체를 나타내는 문자열입니다.

## <a name="see-also"></a>참고자료

[플랫폼 Namespace](platform-namespace-c-cx.md)
