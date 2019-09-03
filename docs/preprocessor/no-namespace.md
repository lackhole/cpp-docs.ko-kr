---
title: no_namespace import 특성
ms.date: 08/29/2019
f1_keywords:
- no_namespace
helpviewer_keywords:
- no_namespace attribute
ms.assetid: 5d81b741-a558-451b-b493-1f3b18967337
ms.openlocfilehash: ba52aed69cdbb46c135e6de5078d718e93f99c87
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70220729"
---
# <a name="no_namespace-import-attribute"></a>no_namespace import 특성

**C++컴퓨터별**

컴파일러가 네임 스페이스 이름을 생성 하지 않도록 지정 합니다.

## <a name="syntax"></a>구문

> **#import** *형식 라이브러리* **no_namespace**

## <a name="remarks"></a>설명

`#import` 헤더 파일의 형식 라이브러리 콘텐츠는 일반적으로 네임스페이스에 정의됩니다. 네임 스페이스 이름은 원래 IDL 파일의 `library` 문에 지정 됩니다. **No_namespace** 특성을 지정 하면 컴파일러에서이 네임 스페이스를 생성 하지 않습니다.

다른 네임 스페이스 이름을 사용 하려면 [rename_namespace](../preprocessor/rename-namespace.md) 특성을 대신 사용 합니다.

**끝 C++ 특정**

## <a name="see-also"></a>참고자료

[#import 특성](../preprocessor/hash-import-attributes-cpp.md)\
[#import 지시문](../preprocessor/hash-import-directive-cpp.md)
