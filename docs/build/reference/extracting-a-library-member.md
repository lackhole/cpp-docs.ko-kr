---
title: 라이브러리 멤버 추출
ms.date: 11/04/2016
f1_keywords:
- Lib
helpviewer_keywords:
- LIB [C++], extracting library members
- EXTRACT library manager option
- libraries, extracting members
- -EXTRACT library manager option
- extracting library members
- /EXTRACT library manager option
ms.assetid: a2c5c2a1-9b7e-489a-a9a4-1dec694e1fc5
ms.openlocfilehash: 6c577300f747d6f546b7caa3c66bddd6a516e16b
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57818065"
---
# <a name="extracting-a-library-member"></a>라이브러리 멤버 추출

기존 라이브러리 멤버의 복사본을 포함 하는 개체 (.obj) 파일을 만들려면 LIB를 사용할 수 있습니다. 멤버의 복사본을 추출 하려면 다음 구문을 사용 합니다.

```
LIB library /EXTRACT:member /OUT:objectfile
```

이 명령은 호출.obj 파일을 만듭니다 *objectfile* 의 복사본을 포함 하는 `member` 의 *라이브러리*합니다. `member` 이름은 대/소문자 구분 합니다. 단일 명령으로 한 멤버를 추출할 수 있습니다. /OUT 옵션을 지정 해야 합니다. 기본 출력 이름이 없습니다. 파일을 호출 하면 *objectfile* 지정된 된 디렉터리에 이미 있습니다 (또는 현재 디렉터리에 디렉터리가 지정 된 경우 *objectfile*)를 추출한 *objectfile*기존 파일을 대체 합니다.

## <a name="see-also"></a>참고자료

[LIB 참조](lib-reference.md)
