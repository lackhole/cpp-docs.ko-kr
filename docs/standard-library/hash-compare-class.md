---
title: hash_compare 클래스
ms.date: 11/04/2016
f1_keywords:
- hash_set/stdext::hash_compare
helpviewer_keywords:
- hash_compare class
ms.assetid: d502bb59-de57-4585-beb9-00e3a998c0af
ms.openlocfilehash: f535122b67f854b8b204664b829ce9da5fe3c6a6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62159823"
---
# <a name="hashcompare-class"></a>hash_compare 클래스

이 템플릿 클래스는 해시 연관 컨테이너(hash_map, hash_multimap, hash_set 또는 hash_multiset) 중 하나에서 기본 **Traits** 매개 변수 개체로 사용하여 포함된 요소의 순서를 지정하고 해시할 수 있는 개체를 설명합니다.

## <a name="syntax"></a>구문

class hash_compare { Traits comp; public: const size_t bucket_size = 4; const size_t min_buckets = 8; hash_compare(); hash_compare(Traits pred); size_t operator()(const Key& key) const; bool operator()( const Key& key1, const Key& key2) const; };

## <a name="remarks"></a>설명

각 해시 연관 컨테이너 형식의 해시 특성 개체를 저장 `Traits` (템플릿 매개 변수). hash_compare 특수화에서 클래스를 파생시켜 특정 함수 및 개체를 선택적으로 재정의하거나, 최소한의 특정 요구를 충족하는 경우 이 클래스의 고유한 버전을 제공할 수 있습니다. 형식의 개체 hash_comp에 대 한 특히 `hash_compare<Key, Traits>`, 위의 컨테이너에 다음과 같은 동작이 필요 합니다.

- 모든 값에 대 한 `key` 형식의 `Key`를 호출 **hash_comp**(`key`) 형식의 값 분포를 생성 하는 해시 함수로 `size_t`합니다. hash_compare에서 제공하는 함수는 `key`를 반환합니다.

- 모든 값에 대 한 `key1` 형식의 `Key` 앞에 오는 `key2` 시퀀스의 동일 하 고 해시 값 (해시 함수에서 반환 된 값)을 **hash_comp**(`key2`, `key1`)은 false입니다. 함수는 전체 형식의 값에 순서 지정을 적용 해야 합니다 `Key`합니다. Hash_compare에서 제공 하는 함수 반환 *comp*(`key2`, `key1`) `,` 여기서 *comp* 형식의 저장된 된 개체는 `Traits` 시기를 지정할 수 있습니다 개체 hash_comp를 생성 합니다. 기본 `Traits` 매개 변수 형식 `less<Key>`, 정렬 키 값 결코 감소 합니다.

- 정수 상수 `bucket_size` "버킷 당" (해시 테이블 항목) 컨테이너를 초과 하지는 요소의 평균 수를 지정 합니다. 0보다 커야 합니다. hash_compare에서 제공하는 값은 4입니다.

- 정수 상수 `min_buckets` 해시 테이블을 유지 하기 위해 버킷 최소 수를 지정 합니다. 0보다 큰 2의 거듭제곱이어야 합니다. hash_compare에서 제공하는 값은 8입니다.

## <a name="example"></a>예제

hash_compare를 선언 및 사용하는 방법의 예제는 [hash_map::hash_map](../standard-library/hash-map-class.md#hash_map), [hash_multimap::hash_multimap](../standard-library/hash-multimap-class.md#hash_multimap), [hash_set::hash_set](../standard-library/hash-set-class.md#hash_set) 및 [hash_multiset::hash_multiset](../standard-library/hash-multiset-class.md#hash_multiset)에 대한 예제를 참조하세요.

## <a name="requirements"></a>요구 사항

**헤더:** \<hash_map>

**네임스페이스:** stdext

## <a name="see-also"></a>참고자료

[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ 표준 라이브러리 참조](../standard-library/cpp-standard-library-reference.md)<br/>
