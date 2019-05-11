---
title: 명령줄 빌드에 맞는 경로 및 환경 변수 설정
ms.custom: conceptual
ms.date: 05/06/2019
helpviewer_keywords:
- environment variables [C++]
- VCVARS32.bat file
- cl.exe compiler [C++], environment variables
- LINK tool [C++], environment variables
- PATH reserved word
- INCLUDE reserved word
- LINK tool [C++], path
- LIB environment variable
- compiling source code [C++], from command line
- environment variables [C++], CL compiler
ms.assetid: 99389528-deb5-43b9-b99a-03c8773ebaf4
ms.openlocfilehash: 30dadf365186ae74144a3225889c08eedfb89b47
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65217608"
---
# <a name="set-the-path-and-environment-variables-for-command-line-builds"></a>명령줄 빌드에 맞는 경로 및 환경 변수 설정

Microsoft C++ (MSVC) 명령줄 빌드 도구 설치 및 빌드 구성에 사용자 지정 된 여러 환경 변수가 필요 합니다. C++ 워크 로드를 Visual Studio 설치 관리자가 설치 될 때 사용자 지정된 명령 파일이 나 필수 환경 변수를 설정 하는 일괄 처리 파일을 만듭니다. 설치 관리자는 다음 개발자 명령 프롬프트 창을 열려면 Windows 시작 메뉴에 대 한 바로 가기를 만들려면 이러한 명령 파일을 사용 합니다. 특정 환경 변수를 설정 하는 이러한 바로 가기 빌드 구성입니다. 명령줄 도구를 사용 하려는 경우 이러한 바로 가기 중 하나를 실행할 수 있습니다 하거나 일반 명령 프롬프트 창을 열고를 직접 빌드 구성 환경을 설정 하는 사용자 지정 명령 파일 중 하나를 실행 합니다. 자세한 내용은 [명령줄에서 MSVC 도구 집합을 사용 하 여](building-on-the-command-line.md)입니다.

MSVC 명령줄 도구 PATH, TMP, INCLUDE, LIB 및 LIBPATH 환경 변수를 사용 하 여 및에 설치 된 도구, 플랫폼 및 Sdk에 특정 다른 환경 변수를 사용할 수도 있습니다. 간단한 Visual Studio 설치 20 개 이상의 환경 변수를 설정할 수 있습니다. 이러한 환경 변수 값을 설치 및 빌드 구성 선택 사항은 제품 업데이트 또는 업그레이드 하 여 변경할 수 있습니다 때문에 적극 권장 개발자 명령 프롬프트 바로 가기를 또는 중 하나를 사용 하 여 사용자 지정된 명령 파일을 설정 하는 대신 Windows 환경에서 직접 설정입니다.

개발자 명령 프롬프트 바로 가기로 환경 변수가 설정 되어를 보려면 SET 명령을 사용할 수 있습니다. 일반 명령 프롬프트 창을 열고 하 고는 기준에 대 한 설정 명령의 출력을 캡처하십시오. 개발자 명령 프롬프트 창을 열고 하 고 비교에 대 한 설정 명령의 출력을 캡처하십시오. Visual Studio IDE에 내장 된 것과 같은 도구는 환경 변수를 비교 하 고 개발자 명령 프롬프트에서 설정 된 것을 확인 하려면 유용할 수 있습니다. 컴파일러 및 링커에서의에서 사용 하는 특정 환경 변수에 대 한 자세한 내용은 [CL 환경 변수](reference/cl-environment-variables.md)합니다.

> [!NOTE]
>  여러 명령줄 도구 또는 도구 옵션에는 관리자 권한이 필요할 수 있습니다. 사용 하는 경우 사용 권한 문제가 있는 경우 사용 하 여 개발자 명령 프롬프트 창을 열어야는 것이 좋습니다 합니다 **관리자 권한으로 실행** 옵션입니다. Windows 10에서 명령 프롬프트 창에 대 한 바로 가기 메뉴를 열고를 마우스 오른쪽 단추로 클릭 한 다음 선택 **자세한**하십시오 **관리자 권한으로 실행**합니다.

## <a name="see-also"></a>참고자료

[명령줄에서 MSVC 도구 집합 사용](building-on-the-command-line.md)<br/>
[MSVC 링커 참조](reference/linking.md)<br/>
[MSVC 링커 옵션](reference/linker-options.md)<br/>
[MSVC 컴파일러 참조](reference/compiling-a-c-cpp-program.md)<br/>
[MSVC 컴파일러 옵션](reference/compiler-options.md)
