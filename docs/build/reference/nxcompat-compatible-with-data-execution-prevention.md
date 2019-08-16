---
title: /NXCOMPAT(데이터 실행 방지 기능과 호환)
ms.date: 12/29/2017
f1_keywords:
- /NXCOMPAT
helpviewer_keywords:
- /NXCOMPAT linker option
- -NXCOMPAT linker option
- NXCOMPAT linker option
ms.openlocfilehash: 7c788f5ec499f0edf0c44f1ff269af9767af6c08
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69492672"
---
# <a name="nxcompat-compatible-with-data-execution-prevention"></a>/NXCOMPAT(데이터 실행 방지 기능과 호환)

실행 파일이 Windows 데이터 실행 방지 기능과 호환 됨을 나타냅니다.

## <a name="syntax"></a>구문

> **/NXCOMPAT**[ **:NO**]

## <a name="remarks"></a>설명

기본적으로 **/NXCOMPAT** 는 on입니다.

**/NXCOMPAT: NO** 를 사용 하 여 데이터 실행 방지와 호환 되지 않는 실행 파일을 명시적으로 지정할 수 있습니다.

데이터 실행 방지에 대 한 자세한 내용은 다음 문서를 참조 하세요.

- [DEP (데이터 실행 방지) 기능에 대 한 자세한 설명](https://support.microsoft.com/help/875352/a-detailed-description-of-the-data-execution-prevention-dep-feature-in)

- [데이터 실행 방지](/windows/win32/Memory/data-execution-prevention)

- [데이터 실행 방지 (Windows Embedded)](/previous-versions/windows/embedded/ms913190\(v=winembedded.5\))

### <a name="to-set-this-linker-option-in-visual-studio"></a>Visual Studio에서 이 링커 옵션을 설정하려면

1. 프로젝트 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. **구성 속성** > 링커명령줄 > 속성 페이지를 선택 합니다.

1. **추가 옵션** 상자에 옵션을 입력 합니다. **확인** 또는 **적용** 을 선택 하 여 변경 내용을 적용 합니다.

### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[MSVC 링커 참조](linking.md)<br/>
[MSVC 링커 옵션](linker-options.md)
