---
title: 심각한 오류 C1083
ms.date: 09/01/2017
f1_keywords:
- C1083
helpviewer_keywords:
- C1083
ms.assetid: 97e52df3-e79c-4f85-8f1e-bbd1057d55e7
ms.openlocfilehash: 522bc4a36be59d4e2c9425e50b1238eb9f4aba61
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57822199"
---
# <a name="fatal-error-c1083"></a>심각한 오류 C1083

> 열 수 없습니다 *filetype* 파일: '*파일*': *메시지*

컴파일러는 필요한 파일을 찾을 수 없는 경우 C1083 오류가 발생을 생성 합니다. 이 오류에 대 한 많은 잠재적 원인이 있습니다. 잘못 된 포함 검색 경로 또는 누락 되었거나 이름이 잘못 지정 된 헤더 파일은 가장 일반적인 원인 이지만 다른 파일 형식 및 문제 C1083 길어질 수 있습니다. 일부 일반적인 이유는 컴파일러가이 오류를 생성 하는 이유는 다음과 같습니다.

## <a name="the-specified-file-name-is-wrong"></a>지정한 파일 이름이 잘못됨

파일 이름이 잘못 입력될 수 있습니다. 예를 들면 다음과 같습니다.

`#include <algorithm.h>`

원하는 파일을 찾을 수 없습니다. 대부분의 c + + 표준 라이브러리 헤더 파일에는.h 파일 확장명이 없습니다. 합니다 \<알고리즘 > 헤더를이 찾을 수 없습니다 `#include` 지시문입니다. 이 문제를 해결 하려면이 예제와 같이 올바른 파일 이름을 입력 되어 있는지 확인 합니다.

`#include <algorithm>`

특정 C 런타임 라이브러리 헤더는 표준 포함 디렉터리의 하위 디렉터리에 있습니다. 예를 들어 sys/types.h 등을 포함 해야에 sys 하위 디렉터리 이름을 `#include` 지시문:

`#include <sys/types.h>`

## <a name="the-file-is-not-included-in-the-include-search-path"></a>파일 포함 검색 경로에 포함 되지 않습니다.

컴파일러가 `#include` 또는 `#import` 지시문으로 표시되는 검색 규칙을 사용하여 파일을 찾을 수 없습니다. 예를 들어 경우 헤더 파일 이름은 괄호로 묶여 따옴표

`#include "myincludefile.h"`

이 먼저 소스 파일을 포함 하는 동일한 디렉터리에 파일을 찾은 후 빌드 환경에 의해 지정 된 다른 위치에서를 컴파일러에 지시 합니다. 따옴표에 절대 경로가 포함되어 있는 경우 컴파일러는 해당 위치에서만 파일을 찾습니다. 따옴표에 상대 경로가 포함되어 있는 경우 컴파일러는 소스 디렉터리에 관련된 디렉터리에서 파일을 찾습니다.

이름이 꺾쇠 괄호 포함 되어 있으면

`#include <stdio.h>`

컴파일러가 빌드 환경에서 정의 된 검색 경로 따릅니다 합니다 **/I** 컴파일러 옵션을 합니다 **/X** 컴파일러 옵션 및 **포함** 환경 변수. 파일을 검색 하는 검색 순서에 대 한 특정 세부 정보를 비롯 한 자세한 내용은 참조 하세요. [#include 지시문 (C/c + +)](../../preprocessor/hash-include-directive-c-cpp.md) 하 고 [#import 지시문](../../preprocessor/hash-import-directive-cpp.md)합니다.

Include 파일 원본 디렉터리를 기준으로 다른 디렉터리에 있으며에서 상대 경로 사용 하는 경우에 include 지시문을 꺾쇠 괄호 대신 큰따옴표를 사용 해야 합니다. 예를 들어, 헤더 파일 myheader.h에 헤더 라는 프로젝트 소스가의 하위 디렉터리에 있으면이 예제에서는 파일을 찾지 못하면 고 C1083 하면:

`#include <headers\myheader.h>`

하지만이 예제에서는 작동 합니다.

`#include "headers\myheader.h"`

포함 검색 경로에 디렉터리를 사용 하 여 상대 경로 사용할 수도 있습니다. 디렉터리를 추가 하는 경우는 **INCLUDE** 환경 변수 또는 프로그램 **포함 디렉터리** Visual Studio에서 경로 한 경로의 일부를 include 지시문도 추가 하지 마십시오. 예를 들어, \path\example\headers\를에 추가 하 여 헤더, \path\example\headers\myheader.h에 위치한 사용자 **포함 디렉터리** Visual Studio에서 경로 하지만 `#include` 지시문으로 파일을 가리킵니다.

`#include <headers\myheader.h>`

그런 다음 파일을 찾을 수 없습니다. 포함 검색 경로에 지정 된 디렉터리를 기준으로 올바른 경로 사용 합니다. 이 예제에서는 \path\example에 포함 검색 경로 변경할 수 있습니다\, 에서 headers\ 경로 세그먼트를 제거 하거나는 `#include` 지시문입니다.

## <a name="third-party-library-issues-and-vcpkg"></a>Vcpkg 및 타사 라이브러리 문제

빌드의 일부로 타사 라이브러리를 구성 하려는 경우이 오류를 표시 하는 경우 사용을 고려 [Vcpkg](../../vcpkg.md), Visual c + + 패키지 관리자를 설치 하 여 라이브러리를 빌드합니다. Vcpkg 지 원하는 점점 [타사 라이브러리의 목록](https://github.com/Microsoft/vcpkg/tree/master/ports), 모든 구성 속성 및 프로젝트의 일환으로 빌드가 성공한 경우에 필요한 종속성을 가져오거나 설정 합니다. 자세한 내용은 참조는 관련 [Visual c + + 블로그](https://blogs.msdn.microsoft.com/vcblog/2016/09/19/vcpkg-a-tool-to-acquire-and-build-c-open-source-libraries-on-windows/) 게시 합니다.

## <a name="the-file-is-in-your-project-but-not-the-include-search-path"></a>파일이 프로젝트에 있지만 포함 검색 경로

헤더 파일에 표시 되 면에 **솔루션 탐색기** 프로젝트의 일환으로, 파일은만 컴파일러에서 검색 하 여 참조 하는 경우는 `#include` 또는 `#import` 지시문을 소스 파일과에 있는 검색 경로 포함 합니다. 빌드 종류에 따라 다른 검색 경로가 사용될 수도 있습니다. 합니다 **/X** 포함 검색 경로에서 디렉터리를 제외 하려면 컴파일러 옵션을 사용할 수 있습니다. 이렇게 하면 각 빌드에서 이름은 같지만 다른 디렉터리에 보관되는 다른 포함 파일을 사용할 수 있습니다. 이는 전처리기 명령을 통한 조건부 컴파일의 대체 방법입니다. 에 대 한 자세한 내용은 합니다 **/X** 컴파일러 옵션을 참조 하십시오 [/X (표준 포함 경로 무시)](../../build/reference/x-ignore-standard-include-paths.md)합니다.

이 문제를 해결하려면 컴파일러가 포함되거나 가져온 파일을 찾는 데 사용하는 경로를 수정합니다. 새 프로젝트는 기본 검색 경로 포함 합니다. 프로젝트에 대 한 디렉터리를 추가 하려면 포함 검색 경로 수정 해야 합니다. 명령줄에서 컴파일하는, 경우에 대 한 경로 추가 합니다 **포함** 환경 변수 또는 **/I** 컴파일러 옵션은 파일의 경로를 지정 하 합니다.

Visual Studio에서 include 디렉터리 경로 설정 하려면 프로젝트를 열고 **속성 페이지** 대화 상자. 선택 **VC + + 디렉터리** 아래에서 **구성 속성** 왼쪽된 창에 다음 편집 합니다 **포함 디렉터리** 속성입니다. Visual Studio에서 컴파일러가 검색 하는 사용자 당 및 프로젝트별 디렉터리에 대 한 자세한 내용은 참조 하세요. [VC + + Directories Property Page](../../build/reference/vcpp-directories-property-page.md)합니다. 에 대 한 자세한 내용은 합니다 **/I** 컴파일러 옵션을 참조 하십시오 [/I (추가 포함 디렉터리)](../../build/reference/i-additional-include-directories.md)합니다.

## <a name="the-command-line-include-or-lib-environment-is-not-set"></a>명령줄 포함 또는 LIB 환경 설정 되지 않은 경우

명령줄에서 컴파일러를 호출하는 경우 대체로 환경 변수를 사용하여 검색 경로를 지정합니다. 설명 하는 검색 경로 **INCLUDE** 또는 **LIB** 환경 변수가 올바르게 설정 되지 않았습니다, C1083 오류가 생성 될 수 있습니다. 기본 명령줄 환경을 설정 하려면 개발자 명령 프롬프트 바로 가기를 사용 하 여 작성 하는 것이 좋습니다. 자세한 내용은 [빌드 C/c + + 명령줄에서](../../build/building-on-the-command-line.md)합니다. 환경 변수를 사용 하는 방법에 대 한 자세한 내용은 참조 하세요. [방법: 환경 변수를 사용 하 여 빌드에서](/visualstudio/msbuild/how-to-use-environment-variables-in-a-build)합니다.

## <a name="the-file-may-be-locked-or-in-use"></a>파일이 잠겨 있거나 사용 중

다른 프로그램을 편집 하거나 파일에 액세스를 사용 하는 경우 파일을 잠근 것 같습니다. 다른 프로그램에서 파일을 닫으십시오. 경우에 따라 다른 프로그램 병렬 컴파일 옵션을 사용 하는 경우 Visual Studio 자체를 수 있습니다. 병렬 빌드 옵션을 해제 하는 경우 이것이 문제를 해결, 오류를 수 있습니다. 다른 병렬 빌드 시스템에서이 문제를 가질 수도 있습니다. 빌드 순서는 올바른 파일 및 프로젝트 종속성을 설정 해야 합니다. 경우에 따라 여러 프로젝트에서 빌드될 수 있는 공통 파일에 대 한 빌드 종속성 순서를 강제로 중간 프로젝트를 만들어 하는 것이 좋습니다. 경우에 따라 바이러스 백신 프로그램 최근에 변경 된 파일 검색에 대 한를 일시적으로 잠급니다. 가능한 경우 바이러스 백신 검사 프로그램에서 프로젝트 빌드 디렉터리를 제외 하는 것이 좋습니다.

## <a name="the-wrong-version-of-a-file-name-is-included"></a>잘못된 버전의 파일 이름이 포함됨

C1083 오류가 잘못된 버전의 파일이 포함되었음을 나타낼 수도 있습니다. 예를 들어 빌드에서 사용되지 않는 헤더 파일에 대한 `#include` 지시문이 있는 잘못된 버전의 파일이 빌드에 포함되어 있을 수 있습니다. 예를 들어, 특정 파일을 적용할 수 있습니다만 x86 빌드 또는 디버그 빌드에 있습니다. 헤더 파일을 찾을 수 없는 경우 컴파일러에서 C1083 오류가 발생합니다. 이 문제를 해결하려면 올바른 파일을 사용하고 헤더 파일 또는 디렉터리를 빌드에 추가하지 마십시오.

## <a name="the-precompiled-headers-are-not-yet-precompiled"></a>미리 컴파일된 헤더가 미리 컴파일되지 않았음

프로젝트가 미리 컴파일된 헤더를 사용하도록 구성되어 있는 경우 헤더 콘텐츠를 사용하는 파일이 컴파일될 수 있도록 관련 .pch 파일을 만들어야 합니다. 예를 들어 stdafx.cpp 파일이 자동으로 새 프로젝트에 대 한 프로젝트 디렉터리에 만들어집니다. 먼저 해당 파일을 컴파일하여 미리 컴파일된 헤더 파일을 만듭니다. 일반적인 빌드 프로세스 디자인에서는이 자동으로 수행 됩니다. 자세한 내용은 [미리 컴파일된 헤더 파일 만들기](../../build/creating-precompiled-header-files.md)합니다.

## <a name="additional-causes"></a>추가 원인

- SDK 또는 타사 라이브러리를 설치한 경우 하지만 SDK 후 새 개발자 명령 프롬프트 창을 열지 않은 경우 또는 라이브러리 설치 됩니다. SDK 또는 라이브러리 파일을 추가 합니다 **포함** 경로, 이러한 환경 변수 변경 내용이 새 개발자 명령 프롬프트 창을 열려면 해야 할 수 있습니다.

- 관리 되는 코드가 컴파일러 옵션을 사용 하는 파일 **/clr** 지정 하지 않으면. 자세한 내용은 [/clr(공용 언어 런타임 컴파일)](../../build/reference/clr-common-language-runtime-compilation.md)을 참조하세요.

- 다른을 사용 하 여 파일을 컴파일하 **/analyze** 헤더를 미리 컴파일하는 데 사용 된 컴파일러 옵션 설정입니다. 프로젝트의 헤더가 미리 컴파일된 경우 동일한 사용 해야 모든 **/analyze** 설정 합니다. 자세한 내용은 [/analyze(코드 분석)](../../build/reference/analyze-code-analysis.md)를 참조하세요.

- 파일 또는 디렉터리는 Linux 용 Windows 하위 시스템에 의해 생성 된, 디렉터리별 대/소문자 구분을 사용 및 지정 된 경우 경로 또는 파일의 경로 또는 디스크 파일의 경우 일치 하지 않습니다.

- 파일, 디렉터리 또는 디스크가 읽기 전용입니다.

- Visual Studio 또는 명령줄 도구를 없는 파일 또는 디렉터리를 읽을 수 있는 권한이 있습니다. 이 때 발생할 수 있습니다, 예를 들어, 프로젝트 파일을 Visual Studio 또는 명령줄 도구를 실행 하는 프로세스 보다 다양 한 소유권을 갖습니다. 경우에 따라 Visual Studio 또는 개발자 명령 프롬프트를 관리자 권한으로 실행 하 여이 문제를 해결할 수 있습니다.

- 파일 핸들이 충분하지 않습니다. 일부 응용 프로그램을 닫은 후 다시 컴파일하십시오. 이러한 경우는 일반적인 상황에서 거의 발생하지 않습니다. 하지만 실제 메모리가 제한된 컴퓨터에서 큰 프로젝트를 빌드하는 경우 발생할 수 있습니다.

## <a name="example"></a>예제

다음 예제에서는 C1083 오류가 발생 하는 경우 헤더 파일 `"test.h"` 포함 검색 경로 또는 원본 디렉터리에 존재 하지 않습니다.

```cpp
// C1083.cpp
// compile with: /c
#include "test.h"   // C1083 test.h does not exist
#include "stdio.h"  // OK
```

IDE 또는 명령줄에서 C/c + + 프로젝트를 빌드하는 방법에 대 한 정보 및 환경 변수를 설정 하는 방법에 대 한 정보를 참조 하세요 [프로젝트 및 빌드 시스템](../../build/projects-and-build-systems-cpp.md)입니다.

## <a name="see-also"></a>참고자료

- [MSBuild 속성](/visualstudio/msbuild/msbuild-properties)
