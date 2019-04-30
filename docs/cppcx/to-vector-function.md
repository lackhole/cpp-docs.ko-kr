---
title: to_vector 함수
ms.date: 12/30/2016
f1_keywords:
- collection/Windows::Foundation::Collections::to_vector
helpviewer_keywords:
- to_vector Function
ms.assetid: 9cdd5123-7243-4def-a1d3-162e0bf6219e
ms.openlocfilehash: 4fa4e9c620519cc6bb2f96d346ded88b6cc826ae
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62404626"
---
# <a name="tovector-function"></a>to_vector 함수

지정된 IVector 또는 IVectorView 매개 변수의 기본 컬렉션과 값이 같은 `std::vector` 를 반환합니다.

## <a name="syntax"></a>구문

```
template <typename T>
inline ::std::vector<T> to_vector(IVector<T>^ v);

template <typename T>
inline ::std::vector<T> to_vector(IVectorView<T>^ v);
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
템플릿 형식 매개 변수입니다.

*v*<br/>
기본 Vector 또는 VectorView 개체에 대한 액세스를 제공하는 IVector 또는 IVectorView 인터페이스입니다.

### <a name="return-value"></a>반환 값

### <a name="requirements"></a>요구 사항

**헤더:** collection.h

**네임스페이스:** Windows::Foundation::Collections

## <a name="see-also"></a>참고자료

[Windows::Foundation::Collections 네임스페이스](../cppcx/windows-foundation-collections-namespace-c-cx.md)
