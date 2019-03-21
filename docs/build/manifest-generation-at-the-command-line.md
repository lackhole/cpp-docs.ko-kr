---
title: 명령줄에서 매니페스트 생성
ms.date: 11/04/2016
helpviewer_keywords:
- manifests [C++]
- manifest tool (mt.exe)
ms.assetid: fc2ff255-82b1-4c44-af76-8405c5850292
ms.openlocfilehash: 37036ceedc59e20374fd1106a051ab2a66edd143
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57820275"
---
# <a name="manifest-generation-at-the-command-line"></a>명령줄에서 매니페스트 생성

Nmake 또는 유사한 도구를 사용 하 여 명령줄에서 C/c + + 응용 프로그램을 빌드하는 경우 링커는 모든 개체 파일을 처리 하 고 최종 이진 파일을 빌드한 후 매니페스트 생성 됩니다. 링커에서 개체 파일에 저장 하는 어셈블리 정보를 수집 하 고 최종 매니페스트 파일에이 정보를 결합 합니다. 링커는 라는 파일을 생성 하는 데 기본적으로 *binary_name*. *확장*.manifest을 최종 이진에 설명 합니다. 링커에서 이진 파일 내에서 매니페스트 파일을 포함 하지 않습니다 하 고 외부 파일로 매니페스트를 생성할 수 있습니다. 여러 가지 방법으로 사용 하는 등 최종 이진 파일에 매니페스트를 포함 하는 [매니페스트 도구 (mt.exe)](https://msdn.microsoft.com/library/aa375649) 매니페스트 리소스 파일에 컴파일 또는 합니다. 서명에 특정 규칙에 증분 링크 같은 기능을 사용 하도록 설정 하려면 최종 이진에 매니페스트를 포함 하는 경우 따라야 하는 염두 하 고 편집 하며 계속 하기는 것이 반드시 합니다. 이러한 및 기타 옵션에 설명 되어 [방법: 매니페스트 안에 C/c + + 응용 프로그램을 포함할](how-to-embed-a-manifest-inside-a-c-cpp-application.md) 명령줄에서 빌드할 때입니다.

## <a name="see-also"></a>참고자료

[매니페스트](/windows/desktop/sbscs/manifests)<br/>
[/INCREMENTAL(증분 링크)](reference/incremental-link-incrementally.md)<br/>
[강력한 이름 어셈블리(어셈블리 서명)(C++/CLI)](../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md)<br/>
[편집하며 계속하기](/visualstudio/debugger/edit-and-continue)<br/>
[ 프로그램의 매니페스트 생성 이해](understanding-manifest-generation-for-c-cpp-programs.md)<br/>
