---
title: raw_native_types import 특성
ms.date: 08/29/2019
f1_keywords:
- raw_native_types
helpviewer_keywords:
- raw_native_types attribute
ms.assetid: 9f38daa8-8dc0-46a5-aff9-f1ff9c1e6f48
ms.openlocfilehash: eb08a8e7cb081bd7a470c3c1ecf1492a7a65f833
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70216061"
---
# <a name="raw_native_types-import-attribute"></a>raw_native_types import 특성

**C++컴퓨터별**

상위 수준 래퍼 함수에서 COM 지원 클래스를 사용 하지 않도록 설정 하 고 대신 하위 수준 데이터 형식을 사용 하도록 합니다.

## <a name="syntax"></a>구문

> **#import** *형식 라이브러리* **raw_native_types**

## <a name="remarks"></a>설명

기본적으로 상위 수준 오류 처리 메서드는 `BSTR` 및 `VARIANT` 데이터 형식 및 원시 com 인터페이스 포인터 대신에 COM 지원 클래스 [_bstr_t](../cpp/bstr-t-class.md) 및 [_variant_t](../cpp/variant-t-class.md) 를 사용 합니다. 이 클래스는 이러한 데이터 형식의 메모리 스토리지 할당 및 할당 해제에 대한 정보를 캡슐화합니다.

**끝 C++ 특정**

## <a name="see-also"></a>참고자료

[#import 특성](../preprocessor/hash-import-attributes-cpp.md)\
[#import 지시문](../preprocessor/hash-import-directive-cpp.md)
