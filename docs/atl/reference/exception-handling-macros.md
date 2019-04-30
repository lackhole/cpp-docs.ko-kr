---
title: 예외 처리 매크로
ms.date: 11/04/2016
f1_keywords:
- atldef/ATL::_ATLCATCH
- atldef/ATL::_ATLCATCHALL
- atldef/ATL::_ATLTRY
helpviewer_keywords:
- exception handling, macros
- C++ exception handling, macros
ms.assetid: a8385d34-3fb0-4006-a42a-de045cacf0f4
ms.openlocfilehash: 8afb2019e38f7548467e85d9a2c1c12c538cf744
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62276261"
---
# <a name="exception-handling-macros"></a>예외 처리 매크로

이러한 매크로 예외 처리에 대 한 지원을 제공합니다.

|||
|-|-|
|[_ATLCATCH](#_atlcatch)|연결에서 발생 하는 오류를 처리 하는 문 `_ATLTRY`합니다.|
|[_ATLCATCHALL](#_atlcatchall)|연결에서 발생 하는 오류를 처리 하는 문 `_ATLTRY`합니다.|
|[_ATLTRY](#_atltry)|오류가 발생할 수 있는 수 있는 보호 된 코드 섹션을 표시 합니다.|

## <a name="requirements"></a>요구 사항:

**헤더:** atldef.h

##  <a name="_atlcatch"></a>  _ATLCATCH

연결에서 발생 하는 오류를 처리 하는 문 `_ATLTRY`합니다.

```
_ATLCATCH(e)
```

### <a name="parameters"></a>매개 변수

*e*<br/>
예외 catch입니다.

### <a name="remarks"></a>설명

와 함께 사용할 `_ATLTRY`합니다. 확인 C++ [CAtlException e ()를 catch](../../cpp/try-throw-and-catch-statements-cpp.md) 처리의 지정된 된 형식에 대 한 C++ 예외입니다.

##  <a name="_atlcatchall"></a>  _ATLCATCHALL

연결에서 발생 하는 오류를 처리 하는 문 `_ATLTRY`합니다.

```
_ATLCATCHALL
```

### <a name="remarks"></a>설명

와 함께 사용할 `_ATLTRY`합니다. 확인 C++ [catch (...) ](../../cpp/try-throw-and-catch-statements-cpp.md) 모든 유형의 처리에 대 한 C++ 예외입니다.

##  <a name="_atltry"></a>  _ATLTRY

오류가 발생할 수 있는 수 있는 보호 된 코드 섹션을 표시 합니다.

```
_ATLTRY
```

### <a name="remarks"></a>설명

와 함께 사용할 [_ATLCATCH](#_atlcatch) 하거나 [_ATLCATCHALL](#_atlcatchall)합니다. 로 확인 되는 C++ 기호 [시도](../../cpp/try-throw-and-catch-statements-cpp.md)합니다.

## <a name="see-also"></a>참고자료

[매크로](../../atl/reference/atl-macros.md)
