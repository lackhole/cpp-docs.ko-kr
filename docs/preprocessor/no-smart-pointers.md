---
title: no_smart_pointers import 특성
ms.date: 08/29/2019
f1_keywords:
- no_smart_pointers
helpviewer_keywords:
- no_smart_pointers attribute
ms.assetid: d69dd71e-08a8-4446-a3d0-a062dc29cb17
ms.openlocfilehash: 1fca3eb486ff3cfc7403c38e91855b799a698782
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70220695"
---
# <a name="no_smart_pointers-import-attribute"></a>no_smart_pointers import 특성

**C++컴퓨터별**

형식 라이브러리의 모든 인터페이스에 대한 스마트 포인터를 만들지 않습니다.

## <a name="syntax"></a>구문

> **#import** *형식 라이브러리* **no_smart_pointers**

## <a name="remarks"></a>설명

`#import`를 사용하는 경우 기본적으로 형식 라이브러리에 있는 모든 인터페이스에 대한 스마트 포인터 선언을 가져옵니다. 이러한 스마트 포인터는 [_com_ptr_t](../cpp/com-ptr-t-class.md)형식입니다.

**끝 C++ 특정**

## <a name="see-also"></a>참고자료

[#import 특성](../preprocessor/hash-import-attributes-cpp.md)\
[#import 지시문](../preprocessor/hash-import-directive-cpp.md)
