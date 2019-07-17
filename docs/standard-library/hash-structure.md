---
title: hash 구조체
ms.date: 11/04/2016
f1_keywords:
- typeindex/std::hash
ms.assetid: e5a41202-ef3b-45d0-b3a7-4c2dbdc0487a
ms.openlocfilehash: ef620867a5c31c7bd2030803edd6eaea6bbb5726
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68243717"
---
# <a name="hash-structure"></a>hash 구조체

템플릿 클래스는 `val.hash_code()`를 반환할 때의 메서드를 정의합니다. 메서드는 [type_index](../standard-library/type-index-class.md) 형식의 맵 값을 인덱스 값의 분포로 매핑하는 데 사용하는 해시 함수를 정의합니다.

## <a name="syntax"></a>구문

```cpp
template <> struct hash<type_index>
: public unary_function<type_index, size_t>
{ // hashes a typeinfo object
    size_t operator()(type_index val) const;
};
```

## <a name="specialized-types"></a>특수 형식

### <a name="system_error"></a> \<system_error >

```cpp
template <class T> struct hash;
template <> struct hash<error_code>;
template <> struct hash<error_condition>;
```

## <a name="see-also"></a>참고자료

[\<typeindex>](../standard-library/typeindex.md)<br/>
