---
title: Platform::ValueType 클래스
ms.date: 02/03/2017
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::ValueType::ToString
helpviewer_keywords:
- Platform::ValueType Class
ms.assetid: 79aa8754-b140-4974-a5b1-be046938a10a
ms.openlocfilehash: 889cf3a53468491517d37978ca09472756ad9b7e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62182953"
---
# <a name="platformvaluetype-class"></a>Platform::ValueType 클래스

값 형식 인스턴스의 기본 클래스입니다.

## <a name="syntax"></a>구문

```cpp
public ref class ValueType : Object
```

## <a name="public-methods"></a>public 메서드

|||
|-|-|
|[ValueType::ToString](#tostring)|개체의 문자열 표현을 반환 합니다. 상속 [platform:: object](../cppcx/platform-object-class.md)합니다.|

### <a name="remarks"></a>설명

ValueType 클래스는 값 형식을 생성하는 데 사용됩니다. ValueType은 기본 멤버인 Object에서 파생됩니다. 그러나 컴파일러는 해당 기본 멤버를 ValueType 클래스에서 파생된 값 형식에서 분리합니다. 컴파일러는 값 형식이 boxing될 때 해당 기본 멤버를 다시 연결합니다.

### <a name="requirements"></a>요구 사항

**지원 되는 최소 클라이언트:** Windows 8

**지원 되는 최소 서버:** Windows Server 2012

**네임스페이스:** 플랫폼

**메타데이터:** platform.winmd

## <a name="tostring"></a> Valuetype:: Tostring 메서드

개체의 문자열 표현을 반환 합니다.

### <a name="syntax"></a>구문

```cpp
Platform::String ToString();
```

### <a name="return-value"></a>반환 값

platform:: string 값을 나타내는입니다.

## <a name="see-also"></a>참고자료

[Platform 네임스페이스](../cppcx/platform-namespace-c-cx.md)
