---
title: hash_compare 클래스
ms.date: 11/04/2016
f1_keywords:
- hash_set/stdext::hash_compare
helpviewer_keywords:
- hash_compare class
ms.assetid: d502bb59-de57-4585-beb9-00e3a998c0af
ms.openlocfilehash: 399b412c41128f513cf01d1e034bad2bbc5ef79f
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68448804"
---
# <a name="hashcompare-class"></a>hash_compare 클래스

이 템플릿 클래스는 해시 연관 컨테이너(hash_map, hash_multimap, hash_set 또는 hash_multiset) 중 하나에서 기본 **Traits** 매개 변수 개체로 사용하여 포함된 요소의 순서를 지정하고 해시할 수 있는 개체를 설명합니다.

## <a name="syntax"></a>구문

class hash_compare { Traits comp; public: const size_t bucket_size = 4; const size_t min_buckets = 8; hash_compare(); hash_compare(Traits pred); size_t operator()(const Key& key) const; bool operator()( const Key& key1, const Key& key2) const; };

## <a name="remarks"></a>설명

각 해시 연관 컨테이너는 (템플릿 매개 변수) 형식의 `Traits` 해시 특성 개체를 저장 합니다. hash_compare 특수화에서 클래스를 파생시켜 특정 함수 및 개체를 선택적으로 재정의하거나, 최소한의 특정 요구를 충족하는 경우 이 클래스의 고유한 버전을 제공할 수 있습니다. 특히 hash_comp `hash_compare<Key, Traits>`개체의 경우 위의 컨테이너에서 다음과 같은 동작을 수행 해야 합니다.

- 형식의 `key` `size_t` `key`모든 값에 대해 hash_comp () 호출은 형식의 값 분포를 생성 하는 해시 함수 역할을 합니다. `Key` hash_compare에서 제공하는 함수는 `key`를 반환합니다.

- 시퀀스에서 앞 `key1` 에 오고 `Key` `key2` 동일한 해시 값 (해시 함수에서 반환 된 값)을 가진 형식의 값에 대해 **hash_comp**(`key2`, `key1`)는 false입니다. 함수는 형식의 `Key`값에 대 한 전체 순서 지정을 적용 해야 합니다. Hash_compare에서 제공 하는 함수 는 comp`key2`( `key1`, `,` )를 반환 합니다. 여기서 *comp* 는 `Traits` hash_comp 개체를 생성할 때 지정할 수 있는 형식의 저장 된 개체입니다. 기본 `Traits` 매개 변수 형식의 `less<Key>`경우 정렬 키가 값을 감소 시 키 지 않습니다.

- 정수 상수 `bucket_size` 는 컨테이너가 초과 하지 않아야 하는 "버킷" (해시 테이블 항목) 당 평균 요소 수를 지정 합니다. 0보다 커야 합니다. hash_compare에서 제공하는 값은 4입니다.

- 정수 상수 `min_buckets` 는 해시 테이블에서 유지할 최소 버킷 수를 지정 합니다. 0보다 큰 2의 거듭제곱이어야 합니다. hash_compare에서 제공하는 값은 8입니다.

## <a name="example"></a>예제

hash_compare를 선언 및 사용하는 방법의 예제는 [hash_map::hash_map](../standard-library/hash-map-class.md#hash_map), [hash_multimap::hash_multimap](../standard-library/hash-multimap-class.md#hash_multimap), [hash_set::hash_set](../standard-library/hash-set-class.md#hash_set) 및 [hash_multiset::hash_multiset](../standard-library/hash-multiset-class.md#hash_multiset)에 대한 예제를 참조하세요.

## <a name="requirements"></a>요구 사항

**헤더:** \<hash_map>

**네임스페이스:** stdext

## <a name="see-also"></a>참고자료

[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ 표준 라이브러리 참조](../standard-library/cpp-standard-library-reference.md)
