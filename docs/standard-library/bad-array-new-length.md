---
title: bad_array_new_length 클래스
ms.date: 11/04/2016
f1_keywords:
- new/std::bad_alloc
helpviewer_keywords:
- bad_alloc class
ms.assetid: 6429a8e6-5a49-4907-8d56-f4a4ec8131d0
ms.openlocfilehash: 823da1555119735e9aa1c46aa4db2e3a47affdec
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68268695"
---
# <a name="badarraynewlength-class"></a>bad_array_new_length 클래스

클래스 제한 보다 크거나 0 보다 작거나 배열 크기로 인해 할당 요청이 실패 했습니다 나타내기 위해 throw 된 예외를 설명 합니다.

## <a name="syntax"></a>구문

```cpp
class bad_array_new_length : public bad_alloc {
    public: bad_array_new_length() noexcept;
    const char* what() const noexcept override;
};
```

## <a name="remarks"></a>설명

반환한 값 `what` 은 구현 시 정의 된 C 문자열입니다. 멤버 함수는 예외를 발생시키지 않습니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<new>

## <a name="see-also"></a>참고자료

[exception 클래스](../standard-library/exception-class.md)<br/>
[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)
