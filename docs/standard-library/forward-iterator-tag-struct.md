---
title: forward_iterator_tag 구조체
ms.date: 11/04/2016
f1_keywords:
- xutility/std::forward_iterator_tag
helpviewer_keywords:
- forward_iterator_tag struct
- forward_iterator_tag class
ms.assetid: 68b633ac-b135-4e9e-837d-14248a262ec5
ms.openlocfilehash: 04d526e7778dc219a8d9a49db40751b4418cc82d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62159797"
---
# <a name="forwarditeratortag-struct"></a>forward_iterator_tag 구조체

정방향 반복기를 나타내는 **iterator category** 함수에 반환 형식을 제공하는 클래스입니다.

## <a name="syntax"></a>구문

```cpp
struct forward_iterator_tag    : public input_iterator_tag {};
```

## <a name="remarks"></a>설명

범주 태그 클래스는 알고리즘 선택을 위한 컴파일 태그로 사용됩니다. 템플릿 함수는 컴파일 시 가장 효율적인 알고리즘을 사용할 수 있도록 해당 반복기 인수의 가장 구체적인 범주가 무엇인지 찾아야 합니다. `Iterator` 형식의 모든 반복기에 대해 `iterator_traits`< `Iterator`> **::iterator_category**는 반복기 동작을 설명하는 가장 구체적인 범주 태그로 정의되어야 합니다.

**Iter**가 정방향 반복기로 사용될 수 있는 개체를 설명할 경우 형식은 **iterator**\< **Iter**> **::iterator_category**와 같습니다.

## <a name="example"></a>예제

**iterator_tag** 사용 방법의 예제는 [iterator_traits](../standard-library/iterator-traits-struct.md) 또는 [random_access_iterator_tag](../standard-library/random-access-iterator-tag-struct.md)를 참조하세요.

## <a name="requirements"></a>요구 사항

**헤더:** \<iterator>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[input_iterator_tag 구조체](../standard-library/input-iterator-tag-struct.md)<br/>
[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ 표준 라이브러리 참조](../standard-library/cpp-standard-library-reference.md)<br/>
