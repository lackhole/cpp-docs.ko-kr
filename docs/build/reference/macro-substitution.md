---
title: 매크로 대체
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, macro substitution
- macros, NMAKE
- substitution macros in NMAKE
ms.assetid: 47465cfe-fd92-49db-aebe-7c2d7ecceb73
ms.openlocfilehash: 43dc9133c53b1c436c0df8c3db66ae8f18604222
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62321821"
---
# <a name="macro-substitution"></a>매크로 대체

때 *매크로 이름* 가 호출 됩니다 때마다 *string1* 의 정의에 문자열 바뀝니다 *string2*합니다.

## <a name="syntax"></a>구문

```
$(macroname:string1=string2)
```

## <a name="remarks"></a>설명

매크로 대체 대/소문자 구분 되며 리터럴; *string1* 하 고 *string2* 매크로 호출할 수 없습니다. 대체는 원래 정의 수정 하지 않습니다. 제외한 모든 미리 정의 된 매크로의 텍스트를 대체할 수 있습니다 [ $$@ ](filename-macros.md)합니다.

공백 또는 탭 앞에 콜론; 콜론 after 리터럴로 해석 됩니다. 하는 경우 *string2* 가 null 인 모든 *string1* 매크로 정의 문자열에서 삭제 됩니다.

## <a name="see-also"></a>참고자료

[NMAKE 매크로 사용](using-an-nmake-macro.md)
