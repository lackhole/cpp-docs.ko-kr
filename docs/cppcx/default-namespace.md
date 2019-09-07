---
title: default 네임스페이스
ms.date: 12/30/2016
ms.assetid: 4712e9dc-57ba-43cc-811e-022e1dae4de8
ms.openlocfilehash: b67aedc791ed41e93268d9e9f44492781940d55e
ms.sourcegitcommit: 180f63704f6ddd07a4172a93b179cf0733fd952d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70740512"
---
# <a name="default-namespace"></a>default 네임스페이스

네임 `default` 스페이스는/cx에서 C++지 원하는 기본 제공 형식의 범위를 구성 합니다.

## <a name="syntax"></a>구문

```
namespace default;
```

### <a name="members"></a>멤버

모든 기본 제공 형식은 다음 멤버를 상속합니다.

|||
|-|-|
|[default::(type_name)::Equals](../cppcx/default-type-name-equals-method.md)|지정한 개체와 현재 개체가 같은지 여부를 확인합니다.|
|[default::(type_name)::GetHashCode](../cppcx/default-type-name-gethashcode-method.md)|이 인스턴스의 해시 코드를 반환합니다.|
|[default::(type_name)::GetType](../cppcx/default-type-name-gettype-method.md)|현재 형식을 나타내는 문자열을 반환합니다.|
|[default::(type_name)::ToString](../cppcx/default-type-name-tostring-method.md)|현재 형식을 나타내는 문자열을 반환합니다.|

### <a name="built-in-types"></a>기본 제공 형식

|이름|Description|
|----------|-----------------|
|`char16`|유니코드(UTF-16) 코드 포인트를 나타내는 숫자가 아닌 16비트 값입니다.|
|`float32`|32비트 IEEE 754 부동 소수점 숫자입니다.|
|`float64`|64비트 IEEE 754 부동 소수점 숫자입니다.|
|`int16`|16비트 부호 있는 정수입니다.|
|`int32`|32비트 부호 있는 정수입니다.|
|`int64`|부호 있는 64비트 정수입니다.|
|`int8`|8비트 부호 있는 숫자 값입니다.|
|`uint16`|16비트 부호 없는 정수입니다.|
|`uint32`|32비트 부호 없는 정수입니다.|
|`uint64`|64비트 부호 없는 정수입니다.|
|`uint8`|8비트 부호 없는 숫자 값입니다.|

### <a name="requirements"></a>요구 사항

**헤더:** vccorlib.h

## <a name="see-also"></a>참고자료

[C++/CX 언어 참조](../cppcx/visual-c-language-reference-c-cx.md)
