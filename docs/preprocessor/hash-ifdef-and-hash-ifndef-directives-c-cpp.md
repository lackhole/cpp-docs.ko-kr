---
title: '#ifdef 및 #ifndef 지시문 (C/c + +)'
ms.date: 11/04/2016
f1_keywords:
- '#ifndef'
- '#ifdef'
helpviewer_keywords:
- '#ifdef directive'
- preprocessor, directives
- ifdef directive (#ifdef)
- ifndef directive (#ifndef)
- '#ifndef directive'
ms.assetid: 2b0be69d-9e72-45d8-8e24-e4130fb2455b
ms.openlocfilehash: d7a6a1604df03f0607f33e42880270cbdcd62e8b
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59027232"
---
# <a name="ifdef-and-ifndef-directives-cc"></a>#ifdef 및 #ifndef 지시문 (C/C++)
**#ifdef** 하 고 **#ifndef** 지시문으로 동일한 작업을 수행 합니다 `#if` 지시문에 사용 되는 경우 **정의**( *식별자* ).

## <a name="syntax"></a>구문

```
#ifdef identifier
#ifndef identifier

// equivalent to
#if defined identifier
#if !defined identifier
```

## <a name="remarks"></a>설명

사용할 수는 **#ifdef** 하 고 **#ifndef** 지시문을 아무 곳 이나 `#if` 사용할 수 있습니다. 합니다 **#ifdef** *식별자* 문과 동일 `#if 1` 때 *식별자* 정의한 이며에 해당 `#if 0` 때 *식별자* 정의 되지 않았습니다. 또는 사용 하 여 않은 `#undef` 지시문입니다. 이러한 지시문은 C 또는 C++ 소스 코드에서 선언된 식별자가 아니라 `#define`으로 정의된 식별자가 있는지 여부만 검사합니다.

이러한 지시문은 이전 버전 언어와의 호환성을 위해서만 제공됩니다. **정의 (** *식별자* **)** 사용 하는 상수 식의 `#if` 지시문은 것이 좋습니다.

합니다 **#ifndef** 으로 선택 하는 조건의 반대 조건을 확인 지시문 **#ifdef**합니다. 식별자가 정의되지 않았거나 해당 정의가 `#undef`를 통해 제거된 경우 조건은 true(0이 아닌 값)입니다. 그렇지 않으면 조건은 false(0)입니다.

**Microsoft 전용**

합니다 *식별자* 사용 하 여 명령줄에서 전달할 수는 `/D` 옵션입니다. 최대 30 개의 매크로 사용 하 여 지정할 수 있습니다 `/D`합니다.

정의는 명령줄에서 전달될 수 있으므로 정의가 존재하는지 여부를 확인하는 데 유용합니다. 예를 들어:

```cpp
// ifdef_ifndef.CPP
// compile with: /Dtest /c
#ifndef test
#define final
#endif
```

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[전처리기 지시문](../preprocessor/preprocessor-directives.md)