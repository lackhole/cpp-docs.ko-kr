---
title: 심각한 오류 C1076
ms.date: 03/08/2019
f1_keywords:
- C1076
helpviewer_keywords:
- C1076
ms.assetid: 84ac1180-3e8a-48e8-9f77-7f18a778b964
ms.openlocfilehash: 91753a49498548b4e523cd8564ee7a7ca7a3b373
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62406953"
---
# <a name="fatal-error-c1076"></a>심각한 오류 C1076

> 컴파일러 한계 : 내부 힙 한계에 도달했습니다. /Zm을 사용하여 한계를 더 높게 지정하십시오.

템플릿 인스턴스화나 기호가 너무 많은 경우 이 오류가 발생할 수 있습니다. Visual Studio 2015부터이 메시지에서 너무 많은 병렬 빌드 프로세스에서 발생 하는 Windows 가상 메모리가 중 될 수 있습니다. 이 예에서 사용 하는 것을 **/Zm** 옵션을 사용 하는 경우 무시할지를 `#pragma hdrstop` 지시문.

이 오류를 해결하려면

1. 미리 컴파일된 헤더가 사용 하는 경우는 `#pragma hdrstop` 지시문을 사용 하 여는 [/Zm](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md) 컴파일러 메모리 제한을 지정 된 값으로 설정 하는 옵션을 [C3859](../../error-messages/compiler-errors-2/compiler-error-c3859.md) 오류 메시지입니다. 자세한 내용은 Visual Studio에서이 값을 설정 하는 방법 등의 주의 섹션을 참조 하세요. [/Zm (지정 미리 컴파일된 헤더 메모리 할당 제한)](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md)합니다.

1. 사용 하 여 지정 된 병렬 프로세스의 수를 줄이고 합니다 **/maxcpucount** msbuild 옵션입니다. 와 함께에서 EXE 합니다 **/MP** CL 옵션입니다. EXE 수 있습니다. 자세한 내용은 [미리 컴파일된 헤더 (PCH) 문제와 권장 사항을](https://devblogs.microsoft.com/cppblog/precompiled-header-pch-issues-and-recommendations/)합니다.

1. 64비트 운영 체제에서 32비트로 호스팅된 컴파일러를 사용하는 경우 64비트로 호스팅된 컴파일러를 대신 사용하십시오. 자세한 내용은 [방법: 64 비트 시각적 개체를 사용 하도록 설정 C++ 명령줄에서 도구 집합](../../build/how-to-enable-a-64-bit-visual-cpp-toolset-on-the-command-line.md)합니다.

1. 필요 없는 포함 파일을 제거합니다.

1. 예를 들어, 대형 배열을 선언하는 대신에 메모리를 동적으로 할당하여 필요 없는 전역 변수를 제거합니다.

1. 사용되지 않는 선언을 제거합니다.

값에 대해 지정 된 빌드가 시작 된 후 바로 C1076이 발생 하면 **/Zm** 너무 높기 때문일 프로그램에 대 한 합니다. 줄일 합니다 **/Zm** 값입니다.