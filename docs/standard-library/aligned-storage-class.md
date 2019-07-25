---
title: aligned_storage 클래스
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::aligned_storage
helpviewer_keywords:
- aligned_storage class
- aligned_storage
ms.assetid: f255e345-1f05-4d07-81e4-017f420839fb
ms.openlocfilehash: 8a4e907faa6175b9e03f5367d09501aaea388bce
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68456472"
---
# <a name="alignedstorage-class"></a>aligned_storage 클래스

적절하게 정렬된 형식을 만듭니다.

## <a name="syntax"></a>구문

```cpp
template <std::size_t Len, std::size_t Align>
struct aligned_storage;

template <std::size_t Len, std::size_t Align = alignment_of<max_align_t>::value>
using aligned_storage_t = typename aligned_storage<Len, Align>::type;
```

### <a name="parameters"></a>매개 변수

*길이가*\
개체 크기입니다.

*않아*\
개체 정렬입니다.

## <a name="remarks"></a>설명

템플릿 멤버 typedef `type` 는 맞춤 *정렬* 및 크기 *길이가*인 POD 형식의 동의어입니다. *Align* 은 일부 형식 `T`또는 `alignment_of<T>::value` 기본 맞춤에 대해와 같아야 합니다.

## <a name="example"></a>예제

```cpp
#include <type_traits>
#include <iostream>

typedef std::aligned_storage<sizeof (int),
    std::alignment_of<double>::value>::type New_type;
int main()
    {
    std::cout << "alignment_of<int> == "
        << std::alignment_of<int>::value << std::endl;
    std::cout << "aligned to double == "
        << std::alignment_of<New_type>::value << std::endl;

    return (0);
    }
```

```Output
alignment_of<int> == 4
aligned to double == 8
```

## <a name="requirements"></a>요구 사항

**헤더:** \<type_traits>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[<type_traits>](../standard-library/type-traits.md)\
[alignment_of 클래스](../standard-library/alignment-of-class.md)
