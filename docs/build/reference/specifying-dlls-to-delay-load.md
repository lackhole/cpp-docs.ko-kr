---
title: 지연 로드할 DLL 지정
ms.date: 11/04/2016
helpviewer_keywords:
- DELAYLOAD linker option
- delayed loading of DLLs
- delayed loading of DLLs, specifying
- /DELAYLOAD linker option
ms.assetid: 94cbecfe-7a42-40d1-a618-9f2786bac0d8
ms.openlocfilehash: 2b6737abd76c03186881e83bbd2bf286be6ffe2f
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57813229"
---
# <a name="specifying-dlls-to-delay-load"></a>지연 로드할 DLL 지정

사용 하 여 지연 Dll 로드 지정할 수 있습니다 합니다 [/delayload](delayload-delay-load-import.md):`dllname` 링커 옵션입니다. 자체 버전의 도우미 함수를 사용하려는 경우가 아니면 delayimp.lib(데스크톱 응용 프로그램) 또는 dloadhelper.lib(스토어 앱)를 사용하여 프로그램을 연결해야 합니다.

다음은 DLL 지연 로드의 간단한 예입니다.

```
// cl t.cpp user32.lib delayimp.lib  /link /DELAYLOAD:user32.dll
#include <windows.h>
// uncomment these lines to remove .libs from command line
// #pragma comment(lib, "delayimp")
// #pragma comment(lib, "user32")

int main() {
   // user32.dll will load at this point
   MessageBox(NULL, "Hello", "Hello", MB_OK);
}
```

프로젝트의 디버그 버전을 빌드합니다. 디버거를 사용하여 코드를 단계별로 이동하면 user32.dll이 `MessageBox`를 호출할 때만 로드된다는 것을 알 수 있습니다.

## <a name="see-also"></a>참고자료

[링커의 지연 로드된 DLL 지원](linker-support-for-delay-loaded-dlls.md)
