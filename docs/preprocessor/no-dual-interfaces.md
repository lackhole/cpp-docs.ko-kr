---
title: no_dual_interfaces import 특성
ms.date: 08/29/2019
f1_keywords:
- no_dual_interfaces
helpviewer_keywords:
- no_dual_interfaces attribute
ms.assetid: 9acd5d9d-4a49-4cdc-9470-73a2c23cf512
ms.openlocfilehash: 6270888f0d31e4fbe18fb3364995be8c73426b83
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70220755"
---
# <a name="no_dual_interfaces-import-attribute"></a>no_dual_interfaces import 특성

**C++컴퓨터별**

컴파일러가 이중 인터페이스 메서드에 대한 래퍼 함수를 생성하는 방법을 변경합니다.

## <a name="syntax"></a>구문

> **#import** *형식 라이브러리* **no_dual_interfaces**

## <a name="remarks"></a>설명

일반적으로 래퍼는 인터페이스에 대 한 가상 함수 테이블을 통해 메서드를 호출 합니다. **No_dual_interfaces**를 사용 하는 경우 래퍼 `IDispatch::Invoke` 는를 대신 호출 하 여 메서드를 호출 합니다.

**끝 C++ 특정**

## <a name="see-also"></a>참고자료

[#import 특성](../preprocessor/hash-import-attributes-cpp.md)\
[#import 지시문](../preprocessor/hash-import-directive-cpp.md)
