---
title: 설명 블록
ms.date: 11/04/2016
helpviewer_keywords:
- description blocks
- NMAKE program, description blocks
- blocks, description
ms.assetid: 1321f228-d389-40ac-b0cd-4f6e9293602b
ms.openlocfilehash: da9265d6b0026bb47496d3aa58847824b5d634d2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62293812"
---
# <a name="description-blocks"></a>설명 블록

설명 블록은 명령 블록에서 필요에 따라 종속성 줄:

```
targets... : dependents...
    commands...
```

종속 줄은 하나 이상의 대상 및 0 개 이상의 종속 항목을 지정합니다. 줄의 시작 부분에 대상 이어야 합니다. 종속 파일은 콜론 (:)에서 별도 대상 공백이 나 탭 허용 됩니다. 줄을 분할 하려면 대상 또는 종속 후 백슬래시 (\)를 사용 합니다. 대상이 존재 하지 않는 경우 종속 된 보다 이전의 타임 스탬프를 했거나은 [의사 대상](pseudotargets.md), NMAKE 명령을 실행 합니다. 종속 된 다른 곳에서 대상이 존재 하지 않거나 자체 종속 항목에 대해 오래 된, 경우 NMAKE 현재 종속성을 업데이트 하기 전에 종속 항목을 업데이트 합니다.

## <a name="what-do-you-want-to-know-more-about"></a>추가 정보

[대상](targets.md)

[종속 파일](dependents.md)

## <a name="see-also"></a>참고자료

[NMAKE 참조](nmake-reference.md)
