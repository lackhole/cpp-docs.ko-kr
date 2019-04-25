---
title: '&lt;hash_set&gt;'
ms.date: 11/04/2016
f1_keywords:
- <hash_set>
- std::<hash_set>
helpviewer_keywords:
- hash_set header
ms.assetid: 6b556967-c808-4869-9b4d-f9e030864435
ms.openlocfilehash: ba7716c1c84e8a74495a67f10a78eeaad2a6c3d7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62159279"
---
# <a name="lthashsetgt"></a>&lt;hash_set&gt;

> [!NOTE]
> 이 헤더는 사용되지 않습니다. [<unordered_set>](../standard-library/unordered-set.md)을 대신 사용하는 것이 좋습니다.

컨테이너 템플릿 클래스 hash_set 및 hash_multiset와 각 클래스의 지원 템플릿을 정의합니다.

## <a name="syntax"></a>구문

```cpp
#include <hash_set>
```

## <a name="remarks"></a>설명

### <a name="operators"></a>연산자

|Hash_set 버전|Hash_multiset 버전|설명|
|-----------------------|----------------------------|-----------------|
|[operator!=(hash_set)](../standard-library/hash-set-operators.md#op_neq)|[operator!=(hash_multiset)](../standard-library/hash-set-operators.md#op_neq)|연산자의 좌변에 있는 hash_set 또는 hash_multiset 개체가 우변에 있는 hash_set 또는 hash_multiset 개체와 같지 않은지 테스트합니다.|
|[operator==(hash_set)](../standard-library/hash-set-operators.md#op_eq_eq)|[operator==(hash_multiset)](../standard-library/hash-set-operators.md#op_eq_eq)|연산자의 좌변에 있는 hash_set 또는 hash_multiset 개체가 우변에 있는 hash_set 또는 hash_multiset 개체와 같은지 테스트합니다.|

### <a name="specialized-template-functions"></a>특별 템플릿 함수

|Hash_set 버전|Hash_multiset 버전|설명|
|-----------------------|----------------------------|-----------------|
|[swap(hash_set)](../standard-library/hash-set-functions.md#swap)|[swap(hash_multiset)](../standard-library/hash-set-functions.md#swap_hash_multiset)|두 hash_set 또는 hash_multiset의 요소를 교환합니다.|

### <a name="classes"></a>클래스

|클래스|설명|
|-|-|
|[hash_compare 클래스](../standard-library/hash-compare-class.md)|해시 연관 컨테이너에서 사용할 수 있는 개체를 설명-hash_map, hash_multimap, hash_set 또는 hash_multiset-기본값으로 `Traits` 를 주문 하 고 포함 된 요소의 해시 매개 변수 개체입니다.|
|[hash_set 클래스](../standard-library/hash-set-class.md)|포함된 요소의 값이 고유하고 키 값으로 사용된 컬렉션의 데이터를 빠르게 검색하고 저장하는 데 사용됩니다.|
|[hash_multiset 클래스](../standard-library/hash-multiset-class.md)|포함된 요소의 값이 고유하고 키 값으로 사용된 컬렉션의 데이터를 빠르게 검색하고 저장하는 데 사용됩니다.|

## <a name="see-also"></a>참고자료

[헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ 표준 라이브러리 참조](../standard-library/cpp-standard-library-reference.md)<br/>
