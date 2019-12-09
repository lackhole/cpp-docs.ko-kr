---
title: C++ 명령줄 처리 사용자 지정
ms.date: 11/04/2016
f1_keywords:
- _setenvp
- _setargv
helpviewer_keywords:
- command line [C++], processing
- command-line processing
- startup code, customizing command-line processing
- environment, environment-processing routine
- _setargv function
- command line [C++], processing arguments
- suppressing environment processing
- _setenvp function
ms.assetid: aae01cbb-892b-48b8-8e1f-34f22421f263
ms.openlocfilehash: 1541840521695658b5c4d809ba7e11767b1330a2
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857556"
---
# <a name="customizing-c-command-line-processing"></a>C++ 명령줄 처리 사용자 지정

**Microsoft 전용**

프로그램에서 명령줄 인수를 사용하지 않는 경우 명령줄 처리를 수행하는 라이브러리 루틴의 사용을 억제하여 약간의 공간을 절약할 수 있습니다. 이 루틴은 `_setargv`라고 하며 [와일드카드 확장](../cpp/wildcard-expansion.md)에서 설명합니다. 루틴의 사용을 억제하기 위해 `main` 함수를 포함하는 파일에서 아무 작업도 하지 않는 루틴을 정의하고 `_setargv`를 명명합니다. `_setargv`에 대한 호출은 `_setargv`의 정의로 충족되며 라이브러리 버전이 로드되지 않습니다.

마찬가지로 `envp` 인수를 통해 환경 테이블에 액세스하지 않을 경우 환경 처리 루틴인 `_setenvp` 대신 사용할 수 있는 사용자 고유의 빈 루틴을 제공할 수 있습니다. `_setargv` 함수와 마찬가지로, `_setenvp`는 **extern "C"** 로 선언되어야 합니다.

프로그램은 C 런타임 라이브러리의 루틴 중 `spawn` 또는 `exec` 제품군에 대해 호출할 수 있습니다. 이런 경우에는 부모 프로세스에서 자식 프로세스로 환경을 전달하는 데 이 루틴이 사용되므로 환경 처리 루틴을 억제하면 안 됩니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참조

[main: 프로그램 시작](../cpp/main-program-startup.md)