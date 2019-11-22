---
title: 명령 매크로와 옵션 매크로
description: 빌드 도구 및 해당 옵션에 대해 미리 정의 된 NMAKE 매크로를 설명 합니다.
ms.date: 11/20/2019
helpviewer_keywords:
- options macros
- command macros in NMAKE
- macros, options macros
- macros, command macros
ms.assetid: 50dff03c-0dc3-4a8a-9a17-57e0e4ea9bac
no-loc:
- AS
- AFLAGS
- CC
- CFLAGS
- CPP
- CPPFLAGS
- CXX
- CXXFLAGS
- RC
- RFLAGS
- ias
- ml
- ml64
- cl
- rc
ms.openlocfilehash: d5c4477fd97e2a6c48dbac4d0ce83f7fd5f12ad6
ms.sourcegitcommit: 069e3833bd821e7d64f5c98d0ea41fc0c5d22e53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2019
ms.locfileid: "74303170"
---
# <a name="command-macros-and-options-macros"></a>명령 매크로와 옵션 매크로

명령 매크로는 Microsoft 제품에 대해 미리 정의 되어 있습니다. 옵션 매크로는 이러한 제품에 대 한 옵션을 나타내며 기본적으로 정의 되어 있지 않습니다. 두 가지 모두 미리 정의 된 유추 규칙에 사용 되며 설명 블록이 나 사용자 정의 유추 규칙에서 사용할 수 있습니다. 명령 매크로를 재정의 하 여 옵션을 비롯 한 명령줄의 일부 또는 전체를 나타낼 수 있습니다. 옵션 매크로를 정의 하지 않으면 null 문자열이 생성 됩니다.

|Microsoft 제품|Command 매크로|정의 됨|Options 매크로|
|-----------------------|-------------------|----------------|-------------------|
|매크로 어셈블러|**AS**|ml, ias또는 ml64|**AFLAGS**|
|C 컴파일러|**CC**|cl|**CFLAGS**|
|C++ 컴파일러|**CPP**|cl|**CPPFLAGS**|
|C++ 컴파일러|**CXX**|cl|**CXXFLAGS**|
|리소스 컴파일러|**RC**|rc|**RFLAGS**|

## <a name="see-also"></a>참고 항목

[특수 NMake 매크로](special-nmake-macros.md)
