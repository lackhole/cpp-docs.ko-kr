---
title: Platform::ArrayReference 클래스
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::ArrayReference::ArrayReference
helpviewer_keywords:
- Platform::ArrayReference Class
ms.assetid: 9ab3b15e-8a60-4600-8fcb-7d6c86284f4b
ms.openlocfilehash: 923f60e90517e377b99d5e29f38c48b2633c3c46
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57742974"
---
# <a name="platformarrayreference-class"></a>Platform::ArrayReference 클래스

`ArrayReference` 는 C 스타일 배열을 입력 데이터로 채울 때 입력 매개 변수에서 [Platform::Array^](../cppcx/platform-array-class.md) 를 대체할 수 있는 최적화 형식입니다.

## <a name="syntax"></a>구문

```cpp
class ArrayReference
```

### <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[ArrayReference::ArrayReference](#ctor)|`ArrayReference` 클래스의 새 인스턴스를 초기화합니다.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[ArrayReference::operator() 연산자](#operator-call)|이 `ArrayReference` 를 `Platform::Array<T>^*`로 변환합니다.|
|[ArrayReference::operator= 연산자](#operator-assign)|다른 `ArrayReference` 의 내용을 이 인스턴스에 할당합니다.|

## <a name="exceptions"></a>예외

### <a name="remarks"></a>설명

`ArrayReference` 를 사용하여 C 스타일 배열을 채워서 먼저 `Platform::Array` 변수로 복사한 다음 C 스타일 배열로 복사하는 추가적인 복사 작업을 피합니다. `ArrayReference`를 사용하면 한 번의 복사 작업만 있습니다. 코드 예제를 참조 하세요 [Array 및 WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)합니다.

### <a name="requirements"></a>요구 사항

**지원 되는 최소 클라이언트:** Windows 8

**지원 되는 최소 서버:** Windows Server 2012

**네임스페이스:** 플랫폼

**헤더:** vccorlib.h

## <a name="ctor"></a>  Arrayreference:: Arrayreference 생성자

새 인스턴스를 초기화 합니다 [platform:: arrayreference](../cppcx/platform-arrayreference-class.md) 클래스입니다.

### <a name="syntax"></a>구문

```cpp
ArrayReference(TArg* ataArg, unsigned int sizeArg, bool needsInitArg = false);
ArrayReference(ArrayReference&& otherArg)
```

### <a name="parameters"></a>매개 변수

*dataArg*<br/>
배열 데이터에 대한 포인터입니다.

*sizeArg*<br/>
소스 배열의 요소 수입니다.

*otherArg*<br/>
새 인스턴스 초기화를 위해 해당 데이터가 이동될 `ArrayReference` 개체입니다.

### <a name="remarks"></a>설명

## <a name="operator-assign"></a>  Arrayreference:: Operator = 연산자

현재 지정된 된 개체를 할당 [platform:: arrayreference](../cppcx/platform-arrayreference-class.md) 이동 의미 체계를 사용 하 여 개체입니다.

### <a name="syntax"></a>구문

```cpp
ArrayReference& operator=(ArrayReference&& otherArg);
```

### <a name="parameters"></a>매개 변수

*otherArg*<br/>
현재 `ArrayReference` 개체로 이동되는 개체입니다.

### <a name="return-value"></a>반환 값


  `ArrayReference` 형식의 개체에 대한 참조입니다.

### <a name="remarks"></a>설명

`Platform::ArrayReference`는 ref 클래스가 아닌 표준 C++ 클래스 템플릿입니다.

## <a name="operator-call"></a>  ArrayReference::operator() Operator

현재 변환 [platform:: arrayreference](../cppcx/platform-arrayreference-class.md) 개체를 다시는 [platform:: array](../cppcx/platform-array-class.md) 클래스입니다.

### <a name="syntax"></a>구문

```cpp
Array<TArg>^ operator ();
```

### <a name="return-value"></a>반환 값

`Array<TArg>^` 형식의 개체 핸들입니다.

### <a name="remarks"></a>설명

[Platform:: arrayreference](../cppcx/platform-arrayreference-class.md) 하 고 [platform:: array](../cppcx/platform-array-class.md) 템플릿은 표준 c + + 클래스를 하지 ref 클래스입니다.

## <a name="see-also"></a>참고자료

[Platform 네임 스페이스](../cppcx/platform-namespace-c-cx.md)
