---
title: 다중 스레드 프로그램 컴파일 및 링크
ms.date: 11/04/2016
helpviewer_keywords:
- compiling multithreaded programs
- multithreading [C++], linking programs
- threading [C++], linking programs
- multithreading [C++], compiled programs
- threading [C++], compiled programs
- compiling source code [C++], multithread programs
- linking [C++], multithread programs
ms.assetid: 27589afc-daf2-4f26-b868-a99de5c9dfec
ms.openlocfilehash: bc56c71c4c3c1367d35dd5995054b1d7371ae9de
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62236941"
---
# <a name="compiling-and-linking-multithread-programs"></a>다중 스레드 프로그램 컴파일 및 링크

Bounce.c 프로그램은 [샘플 다중 스레드 C 프로그램](sample-multithread-c-program.md)에서 설명합니다.

프로그램은 기본적으로 다중 스레드로 컴파일됩니다.

### <a name="to-compile-and-link-the-multithread-program-bouncec-from-within-the-development-environment"></a>개발 환경 내에서 Bounce.c 다중 스레드 프로그램을 컴파일하고 링크하려면

1. **파일** 메뉴에서 **새로 만들기**를 클릭한 다음 **프로젝트**를 클릭합니다.

1. **프로젝트 형식** 창에서 **Win32**를 클릭합니다.

1. **템플릿 창**에서 **Win32 콘솔 응용 프로그램**을 클릭한 다음 프로젝트의 이름을 지정합니다.

1. C 소스 코드를 포함하는 파일을 프로젝트에 추가합니다.

1. **빌드** 메뉴에서 **빌드** 명령을 클릭하여 프로젝트를 빌드합니다.

### <a name="to-compile-and-link-the-multithread-program-bouncec-from-the-command-line"></a>명령줄에서 Bounce.c 다중 스레드 프로그램을 컴파일하고 링크하려면

1. 다음 명령을 사용하여 프로그램을 컴파일하고 링크합니다.

    ```
    CL BOUNCE.C
    ```

## <a name="see-also"></a>참고자료

[C 및 Win32를 사용한 다중 스레딩](multithreading-with-c-and-win32.md)
