---
title: back_inserter 함수
ms.date: 12/30/2016
f1_keywords:
- collection/Windows::Foundation::Collections::back_inserter
helpviewer_keywords:
- back_inserter Function
ms.assetid: 91476338-5548-44b7-bc7e-2150f4fbe31a
ms.openlocfilehash: 82df6b06389fa9f1c3ab83fa7b1da3bab092c68d
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57750743"
---
# <a name="backinserter-function"></a>back_inserter 함수

지정된 컬렉션 끝에 요소를 삽입하는 데 사용되는 반복기를 반환합니다.

## <a name="syntax"></a>구문

```

template <typename T>
Platform::BackInsertIterator<T>
    back_inserter(IVector<T>^ v);

template<typename T>
Platform::BackInsertIterator<T>
   back_inserter(IObservableVector<T>^ v);
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
템플릿 형식 매개 변수입니다.

*v*<br/>
내부 컬렉션에 대한 액세스를 제공하는 인터페이스 포인터입니다.

### <a name="return-value"></a>반환 값

반복기입니다.

### <a name="requirements"></a>요구 사항

**헤더:** collection.h

**네임스페이스:** Windows::Foundation::Collections

## <a name="see-also"></a>참고자료

[Windows::Foundation::Collections Namespace](../cppcx/windows-foundation-collections-namespace-c-cx.md)
