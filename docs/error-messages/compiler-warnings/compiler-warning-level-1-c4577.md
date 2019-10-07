---
title: 컴파일러 경고 C4577
description: 컴파일러 경고 C4577 설명 및 솔루션입니다.
ms.date: 09/18/2019
helpviewer_keywords:
- C4577
ms.openlocfilehash: 637023f4c27f93238fbbd13b4a0e652e6cd958e0
ms.sourcegitcommit: 389c559918d9bfaf303d262ee5430d787a662e92
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2019
ms.locfileid: "71241128"
---
# <a name="compiler-warning-level-1-c4577"></a>컴파일러 경고 (수준 1) C4577

> 예외 처리 모드를 지정 하지 않고 ' noexcept '을 사용 했습니다. 예외에서 종료는 보장 되지 않습니다. /EHsc 지정

컴파일러가 `noexcept` 사양을 검색 했지만 표준 C++ 예외 처리가 지정 되지 않았습니다. C++ [/Ehsc](../../build/reference/eh-exception-handling-model.md) 컴파일러 옵션을 지정 하지 않으면 컴파일러는 표준에 따라 예외 처리를 완전히 지원 하지 않습니다. 이 문제를 해결 하려면 **/ehsc** 컴파일러 옵션을 설정 합니다.

이 경고는 Visual Studio 2015의 새로운 기능은 기본적으로 해제 되어 있습니다. 자세한 내용은 [기본적으로 해제 되어 있는 컴파일러 경고](../../preprocessor/compiler-warnings-that-are-off-by-default.md)를 참조 하세요.
