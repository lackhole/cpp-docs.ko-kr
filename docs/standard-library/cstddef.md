---
title: '&lt;cstddef&gt;'
ms.date: 11/04/2016
f1_keywords:
- <cstddef>
helpviewer_keywords:
- cstddef header
ms.assetid: be8d1e39-5974-41ee-b41d-eafa6c82ffce
ms.openlocfilehash: 15d13a3af35cb41950df8aeba0c86d779e701ddb
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68244440"
---
# <a name="ltcstddefgt"></a>&lt;cstddef&gt;

C 표준 라이브러리 헤더를 포함 \<stddef.h >에 연결 된 이름을 추가 합니다 `std` 네임 스페이스입니다. 외부 링크를 사용 하 여 C 표준 라이브러리 헤더에 선언 된 이름에 선언 되어 있는지 확인이 헤더를 포함 하는 `std` 네임 스페이스입니다.

> [!NOTE]
> \<cstddef > 형식 포함 **바이트** 형식을 포함 하지 않습니다 **wchar_t**합니다.

## <a name="syntax"></a>구문

```cpp
#include <cstddef>
```

## <a name="namespace-and-macros"></a>Namespace 및 매크로

```cpp
namespace std {
    using ptrdiff_t = see definition;
    using size_t = see definition;
    using max_align_t = see definition;
    using nullptr_t = decltype(nullptr);
}

#define NULL  // an implementation-defined null pointer constant
#define offsetof(type, member-designator)
```

### <a name="parameters"></a>매개 변수

*ptrdiff_t*\
부호 있는 정수 형식 배열 개체에 두 개의 아래 첨자의 차이 보유할 수 있는 구현 시 정의 하는 합니다.

*size_t*\
구현 시 정의 된 부호 없는 정수 형식 개체의 바이트 크기를 포함할 수 있는 크기입니다.

*max_align_t*\
해당 맞춤 요구 하는 모든 스칼라 형식의으로 유용한 이며 해당 맞춤 요구 사항이 모든 컨텍스트에서 사용할 수는 POD 형식입니다.

*nullptr_t*\
유형에 대 한 동의어는 **nullptr** 식입니다. 하지만 한 **nullptr** 주소도 사용할 수 없습니다, 다른 *nullptr_t* lvalue 개체를 가져올 수 있습니다.

## <a name="byte-class"></a>바이트 클래스

```cpp
enum class byte : unsigned char {};

template <class IntType>
    constexpr byte& operator<<=(byte& b, IntType shift) noexcept;
    constexpr byte operator<<(byte b, IntType shift) noexcept;
    constexpr byte& operator>>=(byte& b, IntType shift) noexcept;
    constexpr byte operator>>(byte b, IntType shift) noexcept;

constexpr byte& operator|=(byte& left, byte right) noexcept;
constexpr byte operator|(byte left, byte right) noexcept;
constexpr byte& operator&=(byte& left, byte right) noexcept;
constexpr byte operator&(byte left, byte right) noexcept;
constexpr byte& operator^=(byte& left, byte right) noexcept;
constexpr byte operator^(byte left, byte right) noexcept;
constexpr byte operator~(byte b) noexcept;

template <class IntType>
    IntType to_integer(byte b) noexcept;
```

## <a name="see-also"></a>참고자료

[헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ 표준 라이브러리 개요](../standard-library/cpp-standard-library-overview.md)<br/>
[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
