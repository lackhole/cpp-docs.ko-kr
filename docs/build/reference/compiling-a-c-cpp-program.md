---
title: MSVC C /C++ 컴파일러 참조-Visual Studio
description: MSVC 컴파일러 도구 집합 옵션입니다.
ms.date: 12/10/2018
helpviewer_keywords:
- cl.exe compiler
- cl.exe compiler, setting options
ms.assetid: f3eef5ab-d0be-4fb2-90f9-927e6ed58736
ms.openlocfilehash: 2269ba69cea2702ff190c791eb6753acb3619f7d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62294150"
---
# <a name="compiling-a-cc-project"></a>컴파일 C /C++ 프로젝트

C 및 C++ Visual Studio IDE 또는 명령줄에서 컴파일러 옵션을 설정할 수 있습니다. 

## <a name="in-visual-studio"></a>Visual Studio

해당 Visual Studio에서 각 프로젝트에 대 한 컴파일러 옵션을 설정할 수 있습니다 **속성 페이지** 대화 상자. 왼쪽된 창에서 선택 **구성 속성**를 **C/C++** 컴파일러 옵션 범주를 선택 합니다. 각 컴파일러 옵션에 대한 항목에서는 설정하는 방법과 개발 환경의 어느 부분에 있는지 설명합니다. 참조 [MSVC 컴파일러 옵션](compiler-options.md) 목록은 합니다.

## <a name="from-the-command-line"></a>명령줄에서

컴파일러(CL.exe) 옵션을 설정할 수 있습니다.

- [명령줄에서](compiler-command-line-syntax.md)

- [명령 파일](cl-command-files.md)

- [CL 환경 변수](cl-environment-variables.md)

CL 환경 변수에서 지정한 옵션은 CL을 실행할 때마다 사용됩니다. CL 환경 변수나 명령줄에서 명령 파일의 이름을 지정하면 명령줄에서 지정한 옵션이 사용됩니다. 명령줄이나 CL 환경 변수와는 달리 명령 파일을 사용하면 여러 줄로 구성된 옵션과 파일 이름을 사용할 수 있습니다.

컴파일러 옵션은 "왼쪽에서 오른쪽"으로 처리됩니다. 서로 충돌되는 경우 맨 오른쪽에 있는 옵션이 사용됩니다. CL 환경 변수는 명령줄 이전에 처리되므로 CL과 명령줄이 충돌되는 경우 명령줄의 내용이 사용됩니다.

## <a name="additional-compiler-topics"></a>추가 컴파일러 항목

- [MSVC 컴파일러 옵션](compiler-options.md)

- [미리 컴파일된 헤더 파일](../creating-precompiled-header-files.md)

- [CL에서의 링커 호출](cl-invokes-the-linker.md)

컴파일러 호스트 및 대상 아키텍처 선택에 대 한 내용은 참조 하세요 [구성 C++ 64 비트, x64에 대 한 대상 프로젝트](../configuring-programs-for-64-bit-visual-cpp.md)합니다.

## <a name="see-also"></a>참고자료

[C/C++ 빌드 참조](c-cpp-building-reference.md)
