---
title: /hotpatch(핫 패치 가능 이미지 만들기)
ms.date: 11/12/2018
f1_keywords:
- /hotpatch
- VC.Project.VCCLCompilerTool.CreateHotpatchableImage
helpviewer_keywords:
- hot patching
- -hotpatch compiler option [C++]
- /hotpatch compiler option [C++]
- hotpatching
ms.assetid: aad539b6-c053-4c78-8682-853d98327798
ms.openlocfilehash: 8830b26b8fdfc3db2aa5fe31a52e6226fd554946
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57807483"
---
# <a name="hotpatch-create-hotpatchable-image"></a>/hotpatch(핫 패치 가능 이미지 만들기)

핫 패치 가능한 이미지를 준비합니다.

## <a name="syntax"></a>구문

```
/hotpatch
```

## <a name="remarks"></a>설명

때 **/hotpatch** 는 컴파일에서 컴파일러는 각 함수의 첫 번째 명령이 최소한 2 바이트가 되도록, 핫 패치에 필요한 합니다.

사용 하 여는 이미지 핫 패치 가능 하기 위한 준비를 완료 하려면 **/hotpatch** 컴파일하려면를 사용 해야 [/FUNCTIONPADMIN (핫 패치 가능 이미지 만들기)](functionpadmin-create-hotpatchable-image.md) 연결 합니다. 컴파일 및 cl.exe를 한 호출을 사용 하 여 이미지를 연결 하는 경우 **/hotpatch** 의미 **/functionpadmin**합니다.

지침은 항상 2 바이트 이상 ARM 아키텍처 이므로 컴파일은 항상 처리 하는 x64 처럼 **/hotpatch** 지정 지정할 필요가 **/hotpatch** 때 이러한 대상;에 대 한 컴파일 그러나 사용 하 여 여전히 연결 해야 합니다 **/functionpadmin** 에 핫 패치 가능 이미지를 만들 수 있습니다. 합니다 **/hotpatch** 컴파일러 옵션만 영향을 줍니다 x86 컴파일.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 하세요 [Visual Studio에서 설정 c + + 컴파일러 및 빌드 속성](../working-with-project-properties.md)합니다.

1. 선택 된 **C/c + +** 폴더입니다.

1. 선택 된 **명령줄** 속성 페이지.

1. 컴파일러 옵션을 추가 합니다 **추가 옵션** 상자입니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
