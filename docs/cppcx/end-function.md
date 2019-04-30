---
title: end 함수
ms.date: 01/22/2017
f1_keywords:
- collection/Windows::Foundation::Collections::end
helpviewer_keywords:
- end Function
ms.assetid: fb837bff-fc76-4bae-9096-facf0e03041c
ms.openlocfilehash: c46c601be2b2ed78cf79641a7fcf5324e615a771
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62375810"
---
# <a name="end-function"></a>end 함수

지정된 인터페이스 매개 변수로 액세스되는 컬렉션 끝 너머를 가리키는 반복자를 반환합니다.

## <a name="syntax"></a>구문

```

template <typename T>
    ::Platform::Collections::VectorIterator<T>
    end(
        IVector<T>^ v       );

template <typename T>
    ::Platform::Collections::VectorViewIterator<T>
    end(
        IVectorView<T>^ v
       );
template <typename T>
    ::Platform::Collections::InputIterator<T>
    end(
        IIterable<T>^ i
       );
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
템플릿 형식 매개 변수입니다.

*v*<br/>
벡터의 컬렉션인\<T > 또는 VectorView\<T >를 IVector로 액세스할 수 있는 개체\<T >, 또는 IVectorView\<T > 인터페이스입니다.

*i*<br/>
개체는 IIterable 액세스 되는 Windows 런타임 arbitraty 컬렉션\<T > 인터페이스입니다.

### <a name="return-value"></a>반환 값

컬렉션 끝 너머를 가리키는 반복자입니다.

### <a name="remarks"></a>설명

처음 두 템플릿 함수는 반복기를 반환하고 세 번째 템플릿 함수는 입력 반복기를 반환합니다.

[에 의해 반환되는](../cppcx/platform-collections-vectorviewiterator-class.md) Platform::Collections::VectorViewIterator `end` 개체는 `VectorProxy<T>`형식의 요소를 저장하는 프록시 반복기입니다. 그러나 프록시 개체는 사용자 코드에 거의 표시되지 않습니다. 자세한 내용은 [컬렉션(C++/CX)](../cppcx/collections-c-cx.md)을 참조하세요.

### <a name="requirements"></a>요구 사항

**헤더:** collection.h

**네임스페이스:** Windows::Foundation::Collections

## <a name="see-also"></a>참고자료

[Windows::Foundation::Collections 네임스페이스](../cppcx/windows-foundation-collections-namespace-c-cx.md)
