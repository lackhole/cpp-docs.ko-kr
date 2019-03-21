---
title: 규칙 정의
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, inference rules
- defining inference rules
ms.assetid: 071cd092-3f2e-4065-b0fb-36a9d393cfa8
ms.openlocfilehash: cd82dc5b0693e563fd3d75a0215265089ff57913
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57827182"
---
# <a name="defining-a-rule"></a>규칙 정의

합니다 *fromext* 종속 파일의 확장명을 나타내는 및 *toext* 대상 파일의 확장명을 나타냅니다.

```
.fromext.toext:
   commands
```

## <a name="remarks"></a>설명

확장은 대/소문자 구분 되지 않았습니다. 나타내는 매크로 호출할 수 있습니다 *fromext* 하 고 *toext*; 전처리 중 매크로 확장 됩니다. 마침표 (.) 앞 *fromext* 줄의 시작 부분에 표시 되어야 합니다. 콜론 (:) 0 개 이상의 공백 또는 탭 앞에 있습니다. 공백 또는 탭, 명령을 지정 하려면 세미콜론 (;), 메모를 지정 하려면 숫자 기호 (#) 또는 줄 바꿈 문자에 의해서만 올 수 있습니다. 다른 공백이 허용 됩니다. 명령 설명 블록와 같이 지정 됩니다.

## <a name="what-do-you-want-to-know-more-about"></a>추가 정보

[규칙에서 경로 검색](search-paths-in-rules.md)

## <a name="see-also"></a>참고자료

[유추 규칙](inference-rules.md)
