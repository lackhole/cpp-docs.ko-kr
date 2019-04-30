---
title: /Zf (더 빠른 PDB 생성)
ms.date: 03/29/2018
f1_keywords:
- /Zf
helpviewer_keywords:
- /Zf
- -Zf
ms.openlocfilehash: bed37a189e3eb1eb7b55dbdee1f81f360eafa721
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62315852"
---
# <a name="zf-faster-pdb-generation"></a>/Zf (더 빠른 PDB 생성)

Mspdbsrv.exe에 대 한 RPC 호출을 최소화 하 여 병렬 빌드에서 더 빠른 PDB 생성을 활성화 합니다.

## <a name="syntax"></a>구문

> **/Zf**

## <a name="remarks"></a>설명

합니다 **/Zf** 옵션을 사용 하는 경우 PDB 파일의 더 빠른 생성에 대 한 컴파일러 지원을 사용 하면 합니다 [/MP (여러 프로세스로 빌드)](mp-build-with-multiple-processes.md) 옵션을 되거나 빌드 시스템 (예를 들어 [MSBuild ](/visualstudio/msbuild/msbuild-reference) 나 [CMake](../cmake-projects-in-visual-studio.md)) 동시에 여러 cl.exe 컴파일러 프로세스 실행 될 수 있습니다. 이 옵션 컴파일 끝날 때까지 PDB 파일의 각 형식 레코드에 대 한 형식 인덱스의 생성을 지연 하려면 컴파일러 프런트 엔드 사용 하면 다음 mspdbsrv.exe, 각 레코드에 대 한 RPC 요청을 수행 하는 대신 단일 RPC 호출에서 모든 요청 합니다. 여러 cl.exe 컴파일러 프로세스가 동시에 실행 환경에서 mspdbsrv.exe 프로세스에 대 한 RPC 부하를 줄여서 빌드 처리량을 크게 높일 수 있습니다이.

때문에 합니다 **/Zf** 필요 옵션 PDB 생성에만 적용 됩니다, 합니다 [/Zi](z7-zi-zi-debug-information-format.md) 또는 [/ZI](z7-zi-zi-debug-information-format.md) 옵션입니다.

합니다 **/Zf** 옵션은 기본적으로 해제 되어 있는 Visual Studio 2017 버전 15.1부터 사용할 수 있습니다. 부터 Visual Studio 2017 버전 15.7 미리 보기 3에서이 옵션이 기본적으로 켜져 때 합니다 **/Zi** 또는 **/ZI** 옵션을 사용 합니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. **구성 속성** > **C/C++** > **명령줄** 속성 페이지를 선택합니다.

1. 수정 된 **추가 옵션** 포함할 속성을 **/Zf** 를 선택한 후 **확인**합니다.

## <a name="see-also"></a>참고자료

[컴파일러 옵션 사전순 목록](compiler-options-listed-alphabetically.md)<br/>
[/MP(여러 프로세스로 빌드)](mp-build-with-multiple-processes.md)<br/>
