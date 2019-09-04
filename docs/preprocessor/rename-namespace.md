---
title: rename_namespace import 특성
ms.date: 08/29/2019
f1_keywords:
- rename_namespace
helpviewer_keywords:
- rename_namespace attribute
ms.assetid: 45006d2b-36cd-4bec-98b9-3b8ec45299e3
ms.openlocfilehash: d319d7390e7c7dce070a35be44aad37c7a34e1a0
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70216647"
---
# <a name="rename_namespace-import-attribute"></a>rename_namespace import 특성

**C++컴퓨터별**

형식 라이브러리의 콘텐츠가 들어있는 네임스페이스의 이름을 바꿉니다.

## <a name="syntax"></a>구문

> **#import** *형식 라이브러리* **rename_namespace (** "*NewName*" **)**

### <a name="parameters"></a>매개 변수

*이름*\
네임스페이스의 새 이름입니다.

## <a name="remarks"></a>설명

**Rename_namespace** 특성은 네임 스페이스의 새 이름을 지정 하는 *NewName*인수 하나를 사용 합니다.

네임 스페이스를 제거 하려면 대신 [no_namespace](../preprocessor/no-namespace.md) 특성을 사용 합니다.

**끝 C++ 특정**

## <a name="see-also"></a>참고자료

[#import 특성](../preprocessor/hash-import-attributes-cpp.md)\
[#import 지시문](../preprocessor/hash-import-directive-cpp.md)
