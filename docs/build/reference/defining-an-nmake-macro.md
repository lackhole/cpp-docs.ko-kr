---
title: NMake 매크로 정의
ms.date: 11/04/2016
helpviewer_keywords:
- macros, NMAKE
- defining NMAKE macros
- NMAKE macros, defining
ms.assetid: 45aae451-9d33-4a3d-8799-2e0cae17070d
ms.openlocfilehash: b163c3dcbfb079a532bd1babca4ee881407bafc1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62272232"
---
# <a name="defining-an-nmake-macro"></a>NMake 매크로 정의

## <a name="syntax"></a>구문

```

macroname=string
```

## <a name="remarks"></a>설명

합니다 *매크로 이름* 는 문자, 숫자 및 밑줄 (_) 최대 1,024 자의의 조합이 며 경우 중요 합니다. 합니다 *매크로 이름* 호출된 매크로 포함할 수 있습니다. 하는 경우 *매크로 이름* 구성 매크로 호출된의 완전히 null 이거나 정의 되지 않은 호출 되는 매크로 일 수 없습니다.

`string` 0 개 이상의 문자 시퀀스를 수 있습니다. Null 문자열에는 0 개의 문자 또는 공백이 나 탭만 포함 되어 있습니다. `string` 매크로 호출을 포함할 수 있습니다.

## <a name="what-do-you-want-to-know-more-about"></a>추가 정보

[매크로의 특수 문자](special-characters-in-macros.md)

[Null 및 정의 되지 않은 매크로](null-and-undefined-macros.md)

[매크로를 정의할 위치](where-to-define-macros.md)

[매크로 정의의 우선 순위](precedence-in-macro-definitions.md)

## <a name="see-also"></a>참고자료

[매크로와 NMake](macros-and-nmake.md)
