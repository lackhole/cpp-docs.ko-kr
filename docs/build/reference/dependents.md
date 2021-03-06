---
title: /DEPENDENTS
ms.date: 07/15/2019
f1_keywords:
- /dependents
helpviewer_keywords:
- -DEPENDENTS dumpbin option
- /DEPENDENTS dumpbin option
- DEPENDENTS dumpbin option
ms.assetid: 9b31da2a-75ac-4bbf-a3f1-adf8b0ecbbb4
ms.openlocfilehash: 88f0062a6bbca3f9199a12f739c2ade5f9d912cd
ms.sourcegitcommit: 7f5b29e24e1be9b5985044a030977485fea0b50c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/17/2019
ms.locfileid: "68299743"
---
# <a name="dependents"></a>/DEPENDENTS

이미지에서 함수를 가져오는 Dll의 이름을 덤프 합니다. 목록을 사용 하 여 앱과 재배포할 Dll을 확인 하거나 누락 된 종속성의 이름을 찾을 수 있습니다.

## <a name="syntax"></a>구문

> **/DEPENDENTS**

이 옵션은 명령줄에 지정 된 모든 실행 파일에 적용 됩니다. 인수를 사용 하지 않습니다.

## <a name="remarks"></a>설명

**/종속** 항목 옵션은 이미지가 가져오는 함수를 출력에 추가 하는 dll의 이름을 추가 합니다. 이 옵션은 가져온 함수의 이름을 덤프 하지 않습니다. 가져온 함수의 이름을 보려면 [/IMPORTS](imports-dumpbin.md) 옵션을 사용 합니다.

[/HEADERS](headers.md) DUMPBIN 옵션은 [/GL](gl-whole-program-optimization.md) 컴파일러 옵션으로 만든 파일에만 사용할 수 있습니다.

## <a name="example"></a>예제

이 예제에서는 연습에서 [기본 제공 되는 클라이언트 실행 파일에 대 한 **/종속** 옵션의 DUMPBIN 출력을 보여 줍니다. 사용자 고유의 동적 링크 라이브러리](../walkthrough-creating-and-using-a-dynamic-link-library-cpp.md)를 만들고 사용 합니다.

```cmd
C:\Users\username\Source\Repos\MathClient\Debug>dumpbin /DEPENDENTS MathClient.exe
Microsoft (R) COFF/PE Dumper Version 14.16.27032.1
Copyright (C) Microsoft Corporation.  All rights reserved.


Dump of file MathClient1322.exe

File Type: EXECUTABLE IMAGE

  Image has the following dependencies:

    MathLibrary.dll
    MSVCP140D.dll
    VCRUNTIME140D.dll
    ucrtbased.dll
    KERNEL32.dll

  Summary

        1000 .00cfg
        1000 .data
        2000 .idata
        1000 .msvcjmc
        3000 .rdata
        1000 .reloc
        1000 .rsrc
        8000 .text
       10000 .textbss
```

## <a name="see-also"></a>참고자료

[DUMPBIN 옵션](dumpbin-options.md)
