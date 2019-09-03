---
title: no_registry import 특성
ms.date: 08/29/2019
f1_keywords:
- no_registry
helpviewer_keywords:
- no_registry attribute
ms.assetid: d30de4e2-551c-428c-98fd-951330d578d3
ms.openlocfilehash: 7c81cc2f570cb9ac4e977dac6d55cb69e491d3b2
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70220715"
---
# <a name="no_registry-import-attribute"></a>no_registry import 특성

**no_registry** 는로 `#import`가져온 형식 라이브러리에 대 한 레지스트리를 검색 하지 않도록 컴파일러에 지시 합니다.

## <a name="syntax"></a>구문

> **#import** *형식 라이브러리* **no_registry**

### <a name="parameters"></a>매개 변수

*형식 라이브러리*\
형식 라이브러리입니다.

## <a name="remarks"></a>설명

참조 된 형식 라이브러리를 포함 디렉터리에서 찾을 수 없는 경우 형식 라이브러리가 레지스트리에 있는 경우에도 컴파일이 실패 합니다.  **no_registry** 는로 `auto_search`암시적으로 가져온 다른 형식 라이브러리에 전파 됩니다.

컴파일러는 파일 이름으로 지정 되 고에 `#import`직접 전달 되는 형식 라이브러리에 대해 레지스트리를 검색 하지 않습니다.

이 `auto_search` 지정 된 경우 추가 `#import` 지시문은 초기 `#import`의 **no_registry** 설정을 사용 하 여 생성 됩니다. 초기 `#import` 지시문 `#import` 이 `auto_search`no_registry 인 경우 생성 된도 **no_registry**입니다.

**no_registry** 는 상호 참조 된 형식 라이브러리를 가져오려는 경우에 유용 합니다. 컴파일러가 레지스트리에서 파일의 이전 버전을 찾지 못하도록 합니다. **no_registry** 는 형식 라이브러리가 등록 되지 않은 경우에도 유용 합니다.

## <a name="see-also"></a>참고자료

[#import 특성](../preprocessor/hash-import-attributes-cpp.md)\
[#import 지시문](../preprocessor/hash-import-directive-cpp.md)
