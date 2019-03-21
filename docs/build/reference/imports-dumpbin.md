---
title: /IMPORTS(DUMPBIN)
ms.date: 11/04/2016
f1_keywords:
- /imports
helpviewer_keywords:
- IMPORTS dumpbin option
- /IMPORTS dumpbin option
- -IMPORTS dumpbin option
ms.assetid: 6a296216-2b1b-40f8-8736-cd4553a22456
ms.openlocfilehash: c8b0f88b38eb657fe4d3916ef0df13972e985cbe
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57810343"
---
# <a name="imports-dumpbin"></a>/IMPORTS(DUMPBIN)

```
/IMPORTS[:file]
```

이 옵션에는 Dll 목록을 표시 (정적 연결 모두 및 [지연 로드](linker-support-for-delay-loaded-dlls.md))에서 이러한 각 Dll 실행 파일 또는 DLL 및 모든 개별 가져오기도 가져올 수 있는 합니다.

선택적 `file` 사양을 사용 하면는 해당 DLL에 대 한 가져오기를 표시 되도록 지정할 수 있습니다. 예를 들어:

```
dumpbin /IMPORTS:msvcrt.dll
```

## <a name="remarks"></a>설명

이 옵션으로 표시 되는 출력은 비슷합니다는 [내보냅니다/](dash-exports.md) 출력 합니다.

[/HEADERS](headers.md) DUMPBIN 옵션은 [/GL](gl-whole-program-optimization.md) 컴파일러 옵션으로 만든 파일에만 사용할 수 있습니다.

## <a name="see-also"></a>참고자료

[DUMPBIN 옵션](dumpbin-options.md)
