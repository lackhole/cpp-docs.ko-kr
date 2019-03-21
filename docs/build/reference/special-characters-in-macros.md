---
title: 매크로의 특수 문자
ms.date: 11/04/2016
helpviewer_keywords:
- special characters, in NMAKE macros
ms.assetid: c0a06cfc-7103-4ee2-a585-e8f6e85dccd7
ms.openlocfilehash: aac7b07500d2a129194e7234210a590cb5d0f19a
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57826677"
---
# <a name="special-characters-in-macros"></a>매크로의 특수 문자

숫자 기호 (#) 후 정의 설명을 지정 합니다. 매크로의 리터럴 숫자 기호를 지정 하려면 사용 하 여 캐럿 (^) 에서처럼 ^ # 합니다.

달러 기호 ($) 매크로 호출을 지정합니다. $ 리터럴을 지정 하려면 $$를 사용 합니다.

새 줄으로 정의 확장 하려면 백슬래시를 사용 하 여 줄 끝 (\\). 매크로 호출 하면 백슬래시와 줄 바꿈 문자는 공백으로 바뀝니다. 줄의 끝에 백슬래시를 지정 하려면 앞에 캐럿 (^)을 사용 하거나 주석 지정자 뒤 (#).

리터럴 줄 바꿈 문자를 지정 하려면 다음과 같이 에서처럼 캐럿 (^)를 사용 하 여 줄 끝.

```
CMDS = cls^
dir
```

## <a name="see-also"></a>참고자료

[NMake 매크로 정의](defining-an-nmake-macro.md)
