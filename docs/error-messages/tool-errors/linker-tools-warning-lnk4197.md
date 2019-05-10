---
title: 링커 도구 경고 LNK4197
ms.date: 09/05/2018
f1_keywords:
- LNK4197
helpviewer_keywords:
- LNK4197
ms.assetid: 8a976fd7-a74b-4c83-ab66-a9e7d7073c4a
ms.openlocfilehash: 0abad1b98ff4782f077312752603ec17fd611c12
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62390362"
---
# <a name="linker-tools-warning-lnk4197"></a>링커 도구 경고 LNK4197

> 내보내기 '*exportname*' 첫 번째 사양을 사용 하 여 여러 번 지정

내보내기가 여러 번 지정 되었습니다 및 다양 한 방법입니다. 링커는 첫 번째 사양을 사용 하 고 나머지 부분을 무시 합니다.

C 런타임 라이브러리를 다시 작성 하는 경우에이 메시지를 무시할 수 있습니다.

내보내기가 정확히 동일한 방식으로 여러 번 지정 된 경우 링커는 경고를 발급 하지 않습니다.

예를 들어.def 파일의이 경고 발생:

```
EXPORTS
   functioname      NONAME
   functioname      @10
```

### <a name="to-fix-by-checking-the-following-possible-causes"></a>다음과 같은 가능한 원인을 확인하여 수정하려면

1. 동일한 내보내기를 지정 모두 명령줄에서 (export를 통해:) 및.def 파일입니다.

2. 동일한 내보내기는 서로 다른 특성을 사용 하 여.def 파일에 두 번 나열 됩니다.