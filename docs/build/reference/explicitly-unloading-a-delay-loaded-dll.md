---
title: 지연 로드된 DLL의 명시적 언로드
ms.date: 11/04/2016
helpviewer_keywords:
- /DELAY:UNLOAD linker option
- DELAY:UNLOAD linker option
- __FUnloadDelayLoadedDLL2
- delayed loading of DLLs, unloading
ms.assetid: 1c4c5172-fd06-45d3-9e4f-f12343176b3c
ms.openlocfilehash: 9909a3e179aa6c0af3a622c7bf1b545326f90bbd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62293461"
---
# <a name="explicitly-unloading-a-delay-loaded-dll"></a>지연 로드된 DLL의 명시적 언로드

합니다 [/delay](delay-delay-load-import-settings.md): unload 링커 옵션을 사용 하면 지연 로드 된 DLL을 언로드할 수 있습니다. 기본적으로 코드 DLL을 언로드할 때 (/delay: unload를 사용 하 여 및 **__FUnloadDelayLoadedDLL2**)를 지연 로드 가져오기 (IAT) 가져오기 주소 테이블을 유지 합니다. 그러나 /delay: unload를 사용 하 여 링커 명령줄에는 도우미 함수가 지원 됩니다 원래 형태로; IAT를 다시 설정 하는 DLL의 명시적 언로드 이제 잘못 된 포인터를 덮어쓰게 됩니다. IAT는 필드를 [ImgDelayDescr](calling-conventions-parameters-and-return-type.md) 포함 하는 원래 IAT 복사본의 주소 (있는 경우).

## <a name="example"></a>예제

### <a name="code"></a>코드

```
// link with /link /DELAYLOAD:MyDLL.dll /DELAY:UNLOAD
#include <windows.h>
#include <delayimp.h>
#include "MyDll.h"
#include <stdio.h>

#pragma comment(lib, "delayimp")
#pragma comment(lib, "MyDll")
int main()
{
    BOOL TestReturn;
    // MyDLL.DLL will load at this point
    fnMyDll();

    //MyDLL.dll will unload at this point
    TestReturn = __FUnloadDelayLoadedDLL2("MyDll.dll");

    if (TestReturn)
        printf_s("\nDLL was unloaded");
    else
        printf_s("\nDLL was not unloaded");
}
```

### <a name="comments"></a>설명

지연 로드 된 DLL 언로드에 중요 한 참고 사항:

- 구현을 찾을 수 있습니다 합니다 **__FUnloadDelayLoadedDLL2** 파일에서 함수 \VC7\INCLUDE\DELAYHLP 합니다. CPP 합니다.

- name 매개 변수를 **__FUnloadDelayLoadedDLL2** 함수 정확히 일치 해야 합니다 (대/소문자) 포함 내용 가져오기 라이브러리에 포함 된 (문자열에에서 있는 이미지에서 가져오기 테이블). 사용 하 여 가져오기 라이브러리의 내용을 볼 수 있습니다 [/DEPENDENTS DUMPBIN](dependents.md)합니다. 원하는 것이 대/소문자 구분 문자열 일치를 사용 하는 경우 업데이트할 수 있습니다 **__FUnloadDelayLoadedDLL2** CRT 문자열 함수 또는 Windows API 호출 중 하나를 사용 합니다.

참조 [지연 로드 된 DLL 언로드](unloading-a-delay-loaded-dll.md) 자세한 내용은 합니다.

## <a name="see-also"></a>참고자료

[링커의 지연 로드된 DLL 지원](linker-support-for-delay-loaded-dlls.md)
