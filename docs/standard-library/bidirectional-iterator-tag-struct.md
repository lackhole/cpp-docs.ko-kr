---
title: bidirectional_iterator_tag 구조체
ms.date: 11/04/2016
f1_keywords:
- xutility/std::bidirectional_iterator_tag
helpviewer_keywords:
- bidirectional_iterator_tag class
- bidirectional_iterator_tag struct
ms.assetid: 9ac06066-b8ae-44b6-bee4-b05855f6a31a
ms.openlocfilehash: c8296ddf30c0e2a3d34e69cbf079c0477e0e8b7a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62414084"
---
# <a name="bidirectionaliteratortag-struct"></a>bidirectional_iterator_tag 구조체

에 대 한 반환 형식을 제공 하는 클래스 `iterator_category` 양방향 반복기를 나타내는 함수입니다.

## <a name="syntax"></a>구문

```cpp
struct bidirectional_iterator_tag    : public forward_iterator_tag {};
```

## <a name="remarks"></a>설명

범주 태그 클래스는 알고리즘 선택을 위한 컴파일 태그로 사용됩니다. 템플릿 함수는 컴파일 시 가장 효율적인 알고리즘을 사용할 수 있도록 해당 반복기 인수의 가장 구체적인 범주를 찾아야 합니다. `Iterator` 형식의 모든 반복기에 대해 `iterator_traits`< `Iterator`>:: **iterator_category**는 반복기 동작을 설명하는 가장 구체적인 범주 태그로 정의되어야 합니다.

형식은 동일 **반복기** \< **Iter**>:: **iterator_category** 때 `Iter` 에 양방향으로 사용할 수 있는 개체에 설명 합니다. 반복기입니다.

## <a name="example"></a>예제

`bidirectional_iterator_tag` 사용 방법의 예는 [random_access_iterator_tag](../standard-library/random-access-iterator-tag-struct.md)를 참조하세요.

## <a name="requirements"></a>요구 사항

**헤더:** \<iterator>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[forward_iterator_tag 구조체](../standard-library/forward-iterator-tag-struct.md)<br/>
[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ 표준 라이브러리 참조](../standard-library/cpp-standard-library-reference.md)<br/>
