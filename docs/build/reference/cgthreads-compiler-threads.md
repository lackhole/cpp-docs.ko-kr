---
title: /CGTHREADS(컴파일러 스레드)
ms.date: 11/04/2016
helpviewer_keywords:
- /CGTHREADS linker option
- -CGTHREADS linker option
- CGTHREADS linker option
ms.assetid: 4b52cfdb-3702-470b-9580-fabeb1417488
ms.openlocfilehash: b778802d3fffcaafc0cf01ac46ae85c4efbef95c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62294670"
---
# <a name="cgthreads-compiler-threads"></a>/CGTHREADS(컴파일러 스레드)

링크 타임 코드 생성이 지정된 경우 최적화 및 코드 생성에 사용할 cl.exe 스레드의 수를 설정합니다.

## <a name="syntax"></a>구문

```
/CGTHREADS:[1-8]
```

## <a name="arguments"></a>인수

*number*<br/>
사용할 cl.exe to의 최대 스레드 수(범위 1~8)

## <a name="remarks"></a>설명

합니다 **/CGTHREADS** 옵션 경우 링크 타임 컴파일의 최적화 및 코드 생성 단계에 대해 병렬로 스레드 cl.exe 사용의 최대 수를 지정 코드를 생성 ([/LTCG](ltcg-link-time-code-generation.md))은 지정 합니다. 기본적으로 cl.exe에서는 4 개의 스레드 처럼 **/CGTHREADS:4** 지정 되었습니다. 더 많은 프로세서 코어를 사용할 수 있는 경우에는 더 큰 `number` 값으로 인해 빌드 시간이 줄어들 수 있습니다.

빌드에 여러 수준의 병렬 처리를 지정할 수 있습니다. Msbuild.exe 스위치인 **/maxcpucount** 병렬로 실행할 수 있는 MSBuild 프로세스의 수를 지정 합니다. 합니다 [/MP (여러 프로세스로 빌드)](mp-build-with-multiple-processes.md) 컴파일러 플래그는 동시에 소스 파일을 컴파일하는 cl.exe 프로세스의 수를 지정 합니다. 합니다 [/cgthreads](cgthreads-code-generation-threads.md) 컴파일러 옵션 각 cl.exe 프로세스에서 사용 되는 스레드 수를 지정 합니다. 프로세서는 프로세서 코어와 동일한 수의 스레드를 동시에 실행할 수 있으므로 이러한 모든 옵션에 대해 동시에 더 큰 값을 지정하는 것은 유용하지 않으며 오히려 역효과가 일어날 수 있습니다. 병렬로 프로젝트를 빌드하는 방법에 대 한 자세한 내용은 참조 하세요. [병렬로 여러 프로젝트 빌드](/visualstudio/msbuild/building-multiple-projects-in-parallel-with-msbuild)합니다.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. 선택 된 **구성 속성**를 **링커** 폴더입니다.

1. 선택 된 **명령줄** 속성 페이지.

1. 수정 된 **추가 옵션** 포함할 속성을 **/CGTHREADS:**`number`여기서 `number` 1에서 8 사이의 값 이며 선택한 **확인**합니다.

### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[MSVC 링커 옵션](linker-options.md)<br/>
[MSVC 링커 참조](linking.md)
