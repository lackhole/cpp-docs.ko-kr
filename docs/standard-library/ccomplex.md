---
title: '&lt;ccomplex&gt;'
ms.date: 07/11/2019
f1_keywords:
- <ccomplex>
- ccomplex
helpviewer_keywords:
- ccomplex header
ms.assetid: a9fcb5f0-88e3-464b-a5fd-d1afb8cd7e6f
ms.openlocfilehash: 5b5383b1eca4fda72f5f9e3a78637373acbcf7ab
ms.sourcegitcommit: 0867d648e0955ebad7260b5fbebfd6cd4d58f3c7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/19/2019
ms.locfileid: "68341133"
---
# <a name="ltccomplexgt"></a>&lt;ccomplex&gt;

표준 라이브러리 C++ 헤더 [\<complex>](complex.md)를 포함 합니다.

> [!NOTE]
> C 표준 라이브러리 \<complex.h> 헤더는 \<ccomplex>에 포함되지 않습니다. 그 이유는 \<complex>와 \<cmath>의 C++ 오버헤드가 효과적으로 대체되기 때문입니다. 하지만 이것은 \<ccomplex> 헤더를 중복하게 됩니다. \<complex.h> 헤더는 C++에서 더 이상 사용되지 않습니다. \<ccomplex> 헤더는 C++ 17 표준과 C++ 20 표준 초안에서 제거 되었습니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<ccomplex>

**네임스페이스:** std

## <a name="remarks"></a>설명

\<complex.h>에서 선언되어 있는 `clog`는 `std` 네임스페이스에 정의되어 있지 않습니다. [\<iostream>](iostream.md)에 선언되어 있는 `clog`와 충돌될 수 있기 때문입니다.

## <a name="see-also"></a>참고자료

[\<complex>](complex.md)\
[\<cmath>](cmath.md)\
[헤더 파일 참조](cpp-standard-library-header-files.md)\
[C++표준 라이브러리 개요](cpp-standard-library-overview.md)\
[C++ 표준 라이브러리의 스레드 보안](thread-safety-in-the-cpp-standard-library.md)
