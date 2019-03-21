---
title: 명령 매크로와 옵션 매크로
ms.date: 11/04/2016
helpviewer_keywords:
- options macros
- command macros in NMAKE
- macros, options macros
- macros, command macros
ms.assetid: 50dff03c-0dc3-4a8a-9a17-57e0e4ea9bac
ms.openlocfilehash: c6dad7b50d265a1460a98747665d48051078163a
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57827807"
---
# <a name="command-macros-and-options-macros"></a>명령 매크로와 옵션 매크로

명령 매크로 Microsoft 제품에 대 한 미리 정의 됩니다. 옵션 매크로 옵션 이러한 제품을 나타내고, 기본적으로 정의 되어 있지 않습니다. 모두 미리 정의 된 규칙에 사용 되 고 설명 블록 또는 사용자 정의 유추 규칙에서 사용할 수 있습니다. 명령 매크로를 나타내는 옵션을 포함 하 여 명령줄의 일부분 또는 전체가 다시 정의할 수 있습니다. 옵션 매크로 정의 하지 않으면 null 문자열을 생성 합니다.

|Microsoft 제품|명령 매크로|로 정의|옵션 매크로|
|-----------------------|-------------------|----------------|-------------------|
|매크로 어셈블러|**AS**|ml|**AFLAGS**|
|기본 컴파일러|**BC**|bc|**BFLAGS**|
|C 컴파일러|**CC**|cl|**CFLAGS**|
|C++ 컴파일러|**CPP**|cl|**CPPFLAGS**|
|C++ 컴파일러|**CXX**|cl|**CXXFLAGS**|
|리소스 컴파일러|**RC**|rc|**RFLAGS**|

## <a name="see-also"></a>참고자료

[특수 NMake 매크로](special-nmake-macros.md)
