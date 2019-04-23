---
title: no_smart_pointers
ms.date: 11/04/2016
f1_keywords:
- no_search_pointers
helpviewer_keywords:
- no_smart_pointers attribute
ms.assetid: d69dd71e-08a8-4446-a3d0-a062dc29cb17
ms.openlocfilehash: ed4950b9e90ef968fcf0c42e4f0a9775c58ea7ec
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59030169"
---
# <a name="nosmartpointers"></a>no_smart_pointers
**C++특정**

형식 라이브러리의 모든 인터페이스에 대한 스마트 포인터를 만들지 않습니다.

## <a name="syntax"></a>구문

```
no_smart_pointers
```

## <a name="remarks"></a>설명

`#import`를 사용하는 경우 기본적으로 형식 라이브러리에 있는 모든 인터페이스에 대한 스마트 포인터 선언을 가져옵니다. 이러한 스마트 포인터는 형식이 [_com_ptr_t 클래스](../cpp/com-ptr-t-class.md)합니다.

**최종 C++ 특정**

## <a name="see-also"></a>참고자료

[#import 특성](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import Directive](../preprocessor/hash-import-directive-cpp.md)