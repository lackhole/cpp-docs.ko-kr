---
title: 컴파일러 및 링커에서의 유니코드 지원
ms.date: 12/15/2017
f1_keywords:
- VC.Project.VCLinkerTool.UseUnicodeResponseFiles
- VC.Project.VCLibrarianTool.UseUnicodeResponseFiles
- VC.Project.VCCLCompilerTool.UseUnicodeResponseFiles
- VC.Project.VCXDCMakeTool.UseUnicodeResponseFiles
helpviewer_keywords:
- Unicode, Visual C++
ms.openlocfilehash: 71458ab345670c0a5715576a7da80c4e6ff2955b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62317330"
---
# <a name="unicode-support-in-the-compiler-and-linker"></a>컴파일러 및 링커에서의 유니코드 지원

가장 Visual C++ 빌드 도구 유니코드 입력 및 출력을 지원 합니다.

## <a name="filenames"></a>파일 이름

명령줄에서 또는 컴파일러 지시문에 지정 된 파일 이름 (같은 `#include`) 유니코드 문자를 포함할 수 있습니다.

## <a name="source-code-files"></a>소스 코드 파일

식별자, 매크로, 문자열 및 문자 리터럴 및 주석에서 유니코드 문자가 지원 됩니다.  유니버설 문자 이름 에서도 지원 됩니다.

다음 인코딩에서 소스 코드 파일에 유니코드를 입력할 수 있습니다.

- Utf-16 little endian 바이트 순서 표시 (BOM)

- Utf-16 big endian BOM 없이

- Utf-8 BOM 사용 하 여

## <a name="output"></a>출력

컴파일하는 동안 컴파일러 진단 u t F-16에서 콘솔에 출력합니다.  콘솔에 표시 될 수 있는 문자는 콘솔 창 속성에 따라 달라 집니다.  파일로 리디렉션할 컴파일러 출력은 현재 ANSI 콘솔 코드 페이지입니다.

## <a name="linker-response-files-and-def-files"></a>링커 지시 파일 및 합니다. DEF 파일

지시 파일과 DEF 파일 utf-16 BOM 또는 ANSI를 수 있습니다.

## <a name="asm-and-cod-dumps"></a>.asm 및.cod 덤프

.asm 및.cod 덤프는 MASM 사용 하 여 호환성을 위해 기본적으로 ANSI입니다. 사용 하 여 [하려면 /FAu](fa-fa-listing-file.md) u t F-8을 출력 합니다. 지정 하는 경우 사용자에 게 유의 **/FAs**, 혼합된 소스가 직접 인쇄를 하 고 예를 들어 소스 코드가 u t F-8 이며 지정 하지 않은 경우 잘못 된 표시 될 수 있습니다 **/FAsu**합니다.

## <a name="see-also"></a>참고자료

[명령줄에서 MSVC 도구 집합 사용](../building-on-the-command-line.md)