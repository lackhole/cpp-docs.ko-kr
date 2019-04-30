---
title: 원시 네이티브 형식
ms.date: 11/04/2016
f1_keywords:
- raw_native_types
helpviewer_keywords:
- raw_native_types attribute
ms.assetid: 9f38daa8-8dc0-46a5-aff9-f1ff9c1e6f48
ms.openlocfilehash: 32b77905ef7025334e5101e76864da9a15c50cf6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62180481"
---
# <a name="rawnativetypes"></a>원시 네이티브 형식
**C++특정**

상위 수준의 래퍼 함수에서 COM 지원 클래스를 사용하지 않도록 설정하고 대신 하위 수준의 데이터 형식을 사용하도록 합니다.

## <a name="syntax"></a>구문

```
raw_native_types
```

## <a name="remarks"></a>설명

기본적으로 상위 수준 오류 처리 메서드는 COM 지원 클래스를 사용 [_bstr_t](../cpp/bstr-t-class.md) 하 고 [_variant_t](../cpp/variant-t-class.md) 대신 합니다 `BSTR` 및 `VARIANT` 데이터 형식 및 원시 COM 인터페이스 포인터입니다. 이 클래스는 이러한 데이터 형식의 메모리 저장소 할당 및 할당 해제에 대한 정보를 캡슐화합니다.

**최종 C++ 특정**

## <a name="see-also"></a>참고자료

[#import 특성](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import Directive](../preprocessor/hash-import-directive-cpp.md)