---
title: raw_dispinterfaces import 특성
ms.date: 08/29/2019
f1_keywords:
- raw_dispinterfaces
helpviewer_keywords:
- raw_dispinterfaces attribute
ms.assetid: f762864d-29bf-445b-825a-ba7b29a95409
ms.openlocfilehash: 73c58b72b27de8dcf96e8ab9464d0fb6bce12b66
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70216217"
---
# <a name="raw_dispinterfaces-import-attribute"></a>raw_dispinterfaces import 특성

**C++컴퓨터별**

는 대상 메서드에 대 한 하위 수준 래퍼 함수를 생성 하 고를 호출 `IDispatch::Invoke` 하 고 HRESULT 오류 코드를 반환 하는 속성에 대해 컴파일러에 지시 합니다.

## <a name="syntax"></a>구문

> **#import** *형식 라이브러리* **raw_dispinterfaces**

## <a name="remarks"></a>설명

이 특성이 지정 되지 않은 경우에는 오류 발생 시 예외를 throw C++ 하는 상위 수준 래퍼로 생성 됩니다.

**끝 C++ 특정**

## <a name="see-also"></a>참고자료

[#import 특성](../preprocessor/hash-import-attributes-cpp.md)\
[#import 지시문](../preprocessor/hash-import-directive-cpp.md)
