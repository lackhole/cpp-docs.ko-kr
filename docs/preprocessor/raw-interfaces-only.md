---
title: raw_interfaces_only import 특성
ms.date: 08/29/2019
f1_keywords:
- raw_interfaces_only
helpviewer_keywords:
- raw_interfaces_only attribute
ms.assetid: 87056c6d-3f34-4248-af58-f5775a35bfb7
ms.openlocfilehash: 4b79aa4dbafa204d84f4d6ed7ec78fdec1b81fa7
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70216216"
---
# <a name="raw_interfaces_only-import-attribute"></a>raw_interfaces_only import 특성

**C++컴퓨터별**

오류 처리 래퍼 함수와 이러한 래퍼 함수를 사용 하는 [속성](../cpp/property-cpp.md) 선언을 생성 하지 않습니다.

## <a name="syntax"></a>구문

> **#import** *형식 라이브러리* **raw_interfaces_only**

## <a name="remarks"></a>설명

**Raw_interfaces_only** 특성을 사용 하면 비 속성 함수의 이름을 지정할 때 사용 되는 기본 접두사를 제거할 수도 있습니다. 일반적으로 접두사 `raw_`는입니다. 이 특성을 지정 하는 경우 함수 이름은 형식 라이브러리에서 직접 가져옵니다.

이 특성을 사용하면 형식 라이브러리의 하위 내용만 노출할 수 있습니다.

**끝 C++ 특정**

## <a name="see-also"></a>참고자료

[#import 특성](../preprocessor/hash-import-attributes-cpp.md)\
[#import 지시문](../preprocessor/hash-import-directive-cpp.md)
