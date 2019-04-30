---
title: /RAWDATA
ms.date: 11/04/2016
f1_keywords:
- /rawdata
helpviewer_keywords:
- RAWDATA dumpbin option
- raw data
- -RAWDATA dumpbin option
- /RAWDATA dumpbin option
ms.assetid: 41cba845-5e1f-415e-9fe4-604a52235983
ms.openlocfilehash: 02af8df04d80c20c5d7629b51abab6295a21f5e5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62319515"
---
# <a name="rawdata"></a>/RAWDATA

```
/RAWDATA[:{1|2|4|8|NONE[,number]]
```

## <a name="remarks"></a>설명

이 옵션 파일에서 각 섹션의 원시 콘텐츠를 표시합니다. 아래와 같이 표시의 형식을 제어 하는 인수:

|인수|결과|
|--------------|------------|
|1|기본값입니다. 인쇄 된 표현이 있는 경우 16 진수 바이트 및 ASCII 문자 내용이 표시 됩니다.|
|2|콘텐츠는 2 바이트의 16 진수 값으로 표시 됩니다.|
|4|콘텐츠는 16 진수 4 바이트 값으로 표시 됩니다.|
|8|콘텐츠는 16 진수 8 바이트 값으로 표시 됩니다.|
|없음|원시 데이터 표시 되지 않습니다. 이 인수는 출력을 제어 하는 데 유용/모든 합니다.|
|*숫자*|표시 된 줄의 너비를 설정 `number` 줄 값입니다.|

[/HEADERS](headers.md) DUMPBIN 옵션은 [/GL](gl-whole-program-optimization.md) 컴파일러 옵션으로 만든 파일에만 사용할 수 있습니다.

## <a name="see-also"></a>참고자료

[DUMPBIN 옵션](dumpbin-options.md)
