---
title: 명령줄에서 매니페스트 생성
ms.date: 11/04/2016
helpviewer_keywords:
- manifests [C++]
- manifest tool (mt.exe)
ms.assetid: fc2ff255-82b1-4c44-af76-8405c5850292
ms.openlocfilehash: 381406213422e286dd9aba26adcdbd6caff7bfe3
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69493197"
---
# <a name="manifest-generation-at-the-command-line"></a>명령줄에서 매니페스트 생성

Nmake 또는 유사한 도구C++ 를 사용 하 여 명령줄에서 C/응용 프로그램을 빌드하는 경우 링커에서 모든 개체 파일을 처리 하 고 최종 이진 파일을 빌드한 후 매니페스트가 생성 됩니다. 링커는 개체 파일에 저장 된 어셈블리 정보를 수집 하 고이 정보를 최종 매니페스트 파일로 결합 합니다. 기본적으로 링커는 이름이 *binary_name*인 파일을 생성 합니다. 최종 이진 파일을 설명 하는 *확장명*매니페스트입니다. 링커는 매니페스트 파일을 이진 파일 안에 포함 하지 않고 매니페스트를 외부 파일로만 생성할 수 있습니다. 매니페스트 [도구 (mt.exe)](/windows/win32/sbscs/mt-exe) 를 사용 하거나 매니페스트를 리소스 파일로 컴파일하는 등의 여러 가지 방법으로 최종 이진 파일 내에 매니페스트를 포함할 수 있습니다. 증분 링크, 서명, 편집 하며 계속 하기와 같은 기능을 사용할 수 있도록 최종 이진 내에 매니페스트를 포함 하는 경우 특정 규칙을 따라야 합니다. 이러한 옵션과 기타 옵션에 [대해서는 방법: 명령줄에서 빌드할 때 C/C++ 응용 프로그램](how-to-embed-a-manifest-inside-a-c-cpp-application.md) 내에 매니페스트를 포함 합니다.

## <a name="see-also"></a>참고자료

[매니페스트](/windows/win32/sbscs/manifests)<br/>
[/INCREMENTAL(증분 링크)](reference/incremental-link-incrementally.md)<br/>
[강력한 이름 어셈블리(어셈블리 서명)(C++/CLI)](../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md)<br/>
[편집하며 계속하기](/visualstudio/debugger/edit-and-continue)<br/>
[ 프로그램의 매니페스트 생성 이해](understanding-manifest-generation-for-c-cpp-programs.md)<br/>
