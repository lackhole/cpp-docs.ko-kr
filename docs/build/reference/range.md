---
title: /RANGE
ms.date: 11/04/2016
f1_keywords:
- /RANGE
helpviewer_keywords:
- /RANGE dumpbin option
- -RANGE dumpbin option
ms.assetid: 7eeba266-32be-49cc-a350-96bdf541f98a
ms.openlocfilehash: c631057e47e1a52a58d2b1304133dfdfc008ae14
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57810967"
---
# <a name="range"></a>/RANGE

Dumpbin /RAWDATA 등 /DISASM dumpbin 옵션과 함께 사용할 경우의 출력을 수정 합니다.

## <a name="syntax"></a>구문

```
/RANGE:vaMin[,vaMax]
```

## <a name="parameters"></a>매개 변수

*vaMin*<br/>
Dumpbin 작업을 시작 하려는 가상 주소입니다.

*vaMax*<br/>
(선택 사항) Dumpbin 작업을 종료 하려는 가상 주소입니다. 지정 하지 않으면 dumpbin 파일의 끝으로 이동 됩니다.

## <a name="remarks"></a>설명

이미지에 대 한 가상 주소를 보려면 RVA + (기본), 이미지 맵 파일을 사용 합니다 **/DISASM** 또는 **/HEADERS** dumpbin, 또는 Visual Studio 디버거의 디스어셈블리 창의 옵션입니다.

## <a name="example"></a>예제

이 예에서 **/범위** 의 표시를 수정 하는 데 사용 되는 **/disasm** 옵션입니다. 이 예제에서는 시작 값이 10 진수 숫자로 표현 됩니다 하 고 끝 값을 16 진수 숫자로 지정 됩니다.

```
dumpbin /disasm /range:4219334,0x004061CD t.exe
```

## <a name="see-also"></a>참고자료

[DUMPBIN 옵션](dumpbin-options.md)
