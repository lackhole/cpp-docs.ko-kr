---
title: /NXCOMPAT(데이터 실행 방지 기능과 호환)
description: 실행 파일을 DEP (C++ 데이터 실행 방지)와 호환 되는 것으로 표시 하는 Microsoft C/(MSVC)/NXCOMPAT 링커 옵션에 대해 설명 합니다.
ms.date: 12/17/2019
f1_keywords:
- /NXCOMPAT
helpviewer_keywords:
- /NXCOMPAT linker option
- -NXCOMPAT linker option
- NXCOMPAT linker option
ms.openlocfilehash: f3a0906a49e3524fff3e1ef1643d1eceee28f169
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75298989"
---
# <a name="nxcompat-compatible-with-data-execution-prevention"></a>/NXCOMPAT(데이터 실행 방지 기능과 호환)

실행 파일이 Windows 데이터 실행 방지 기능과 호환 됨을 나타냅니다.

## <a name="syntax"></a>구문

> **/NXCOMPAT**[ **:NO**]

## <a name="remarks"></a>주의

기본적으로 **/NXCOMPAT** 는 on입니다.

**/NXCOMPAT: NO** 를 사용 하 여 데이터 실행 방지와 호환 되지 않는 실행 파일을 명시적으로 지정할 수 있습니다.

데이터 실행 방지에 대 한 자세한 내용은 다음 문서를 참조 하세요.

- [데이터 실행 방지](/windows/win32/Memory/data-execution-prevention)

- [데이터 실행 방지 (Windows Embedded)](/previous-versions/windows/embedded/ms913190\(v=winembedded.5\))

### <a name="to-set-this-linker-option-in-visual-studio"></a>Visual Studio에서 이 링커 옵션을 설정하려면

1. 프로젝트 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조하세요.

1. **구성 속성** > **링커** > **명령줄** 속성 페이지를 선택 합니다.

1. **추가 옵션** 상자에 옵션을 입력 합니다. **확인** 또는 **적용** 을 선택 하 여 변경 내용을 적용 합니다.

### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>를 참조하세요.

## <a name="see-also"></a>참조

[MSVC 링커 참조](linking.md)\
[MSVC 링커 옵션](linker-options.md)
