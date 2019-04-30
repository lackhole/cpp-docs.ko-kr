---
title: 링커 도구 오류 LNK2011
ms.date: 11/04/2016
f1_keywords:
- LNK2011
helpviewer_keywords:
- LNK2011
ms.assetid: 04991ef5-49d5-46c7-8eee-a9d1d3fc541e
ms.openlocfilehash: c8c62da6c1b4ea856f7a0854b998946893f2be63
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62299094"
---
# <a name="linker-tools-error-lnk2011"></a>링커 도구 오류 LNK2011

미리 컴파일된 개체가 링크 되지 않았습니다. 이미지를 실행할 수 없습니다.

미리 컴파일된 헤더를 사용 하는 경우 링크에 연결 합니다 미리 컴파일된 헤더를 사용 하 여 만든 개체 파일을 모두 필요 합니다. 다른 소스 파일을 사용 하 여 사용에 대 한 미리 컴파일된 헤더를 생성 하는 데 사용 하는 원본 파일이 있는 경우 미리 컴파일된 헤더와 함께 만든 개체 파일은 이제 포함 해야 합니다.

예를 들어 다른 소스 파일을 사용 하 여 사용에 대 한 미리 컴파일된 헤더를 만들려는 STUB.cpp 라는 파일을 컴파일하는 경우 stub.obj 연결 해야 합니다 또는이 오류가 표시 됩니다. 다음 명령줄에서 줄 하나 COMMON.pch 두세 줄에서 PROG1.cpp PROG2.cpp와 사용 되는 미리 컴파일된 헤더를 만드는 사용 됩니다. STUB.cpp만 포함 하는 파일 `#include` 줄 (동일한 `#include` PROG1.cpp 및 PROG2.cpp 줄)는 미리 컴파일된 헤더를 생성 하는 데에 사용 됩니다. 마지막 줄에서 LNK2011 하지 않으려면 STUB.obj에 연결 되어야 합니다.

```
cl /c /Yccommon.h stub.cpp
cl /c /Yucommon.h prog1.cpp
cl /c /Yucommon.h prog2.cpp
link /out:prog.exe stub.obj prog1.obj prog2.obj
```