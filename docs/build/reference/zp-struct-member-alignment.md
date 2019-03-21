---
title: /Zp(구조체 멤버 맞춤)
ms.date: 12/17/2018
f1_keywords:
- /zp
- VC.Project.VCCLCompilerTool.StructMemberAlignment
- VC.Project.VCCLWCECompilerTool.StructMemberAlignment
helpviewer_keywords:
- Struct Member Alignment compiler option
- Zp compiler option
- /Zp compiler option [C++]
- -Zp compiler option [C++]
ms.assetid: 5242f656-ed9b-48a3-bc73-cfcf3ed2520f
ms.openlocfilehash: d30e61137fc5ff8f6a5501ac7815edafc18f7680
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57807691"
---
# <a name="zp-struct-member-alignment"></a>/Zp(구조체 멤버 맞춤)

구조체의 멤버가 메모리에 압축 되는 방식을 제어 하 고 모듈의 모든 구조체에 대해 동일한 압축을 지정 합니다.

## <a name="syntax"></a>구문

> **/Zp**[**1**|**2**|**4**|**8**|**16**]

## <a name="remarks"></a>설명

지정 하는 경우는 **/Zp**_n_ 옵션을 첫 번째 멤버 형식의 크기에 저장 된 이후의 각 구조체 멤버가 또는 *n*-바이트 경계 (여기서 *n* 는 1, 2, 4, 8 또는 16)를 더 작은 값입니다.

사용 가능한 압축 값은 다음 표에 설명 되어 있습니다.

|/Zp 인수|효과|
|-|-|
|1|1 바이트 경계에서 구조체를 압축 합니다. 동일 **/Zp**합니다.|
|2|2 바이트 경계에서 구조체를 압축 합니다.|
|4|4 바이트 경계에서 구조체를 압축 합니다.|
|8|8 바이트 경계 (기본값)에서 구조체를 압축 합니다.|
|16| 16 바이트 경계에서 구조체를 압축 합니다.|

특정 맞춤 요구 사항이 있는 아니라면이 옵션을 사용 하지 않아야 합니다.

> [!WARNING]
> Windows SDK의 c + + 헤더 가정 **/zp8** 압축 합니다. 메모리 손상이 경우 발생할 수 있습니다 합니다 **/Zp** Windows SDK 헤더를 사용 하는 경우 설정이 변경 됩니다.

사용할 수도 있습니다 [팩](../../preprocessor/pack.md) 컨트롤 구조체 압축 합니다. 정렬에 대한 자세한 내용은 다음을 참조하십시오.

- [align(C++)](../../cpp/align-cpp.md)

- [__alignof 연산자](../../cpp/alignof-operator.md)

- [__unaligned](../../cpp/unaligned.md)

- [/ALIGN(섹션 맞춤)](align-section-alignment.md)

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 하세요 [Visual Studio에서 설정 c + + 컴파일러 및 빌드 속성](../working-with-project-properties.md)합니다.

1. 선택 된 **C/c + +** > **코드 생성** 속성 페이지.

1. 수정 된 **구조체 멤버 맞춤** 속성입니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.StructMemberAlignment%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

- [MSVC 컴파일러 옵션](compiler-options.md)
- [MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
