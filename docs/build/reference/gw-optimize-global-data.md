---
title: /Gw(전역 데이터 최적화)
ms.date: 11/04/2016
f1_keywords:
- /Gw
helpviewer_keywords:
- /Gw compiler option [C++]
- -Gw compiler option [C++]
ms.assetid: 6f90f4e9-5eb8-4c47-886e-631278a5a4a9
ms.openlocfilehash: 8afdb21defbbc8309b27749ab18a40f9555139e5
ms.sourcegitcommit: 28eae422049ac3381c6b1206664455dbb56cbfb6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/31/2019
ms.locfileid: "66450140"
---
# <a name="gw-optimize-global-data"></a>/Gw(전역 데이터 최적화)

최적화를 위해 COMDAT 섹션의 전역 데이터를 패키지화합니다.

## <a name="syntax"></a>구문

```
/Gw[-]
```

## <a name="remarks"></a>설명

합니다 **/Gw** 옵션을 개별 COMDAT 섹션에서 컴파일러가 전역 데이터 패키지를 사용 하면 됩니다. 기본적으로 **/Gw** 해제 되 고 명시적으로 설정 해야 합니다. 명시적으로 사용 하지 않도록를 사용 하 여 **/Gw-** 합니다. 때 둘 다 **/Gw** 하 고 [/GL](gl-whole-program-optimization.md) 는 사용 하도록 설정, 링커를 사용 하 여 전체 프로그램 최적화 병합 또는 참조 되지 않은 전역 데이터를 제외 하기 위해 여러 개체 파일에서 COMDAT 섹션을 비교 동일한 읽기 전용 전역 데이터입니다. 이렇게 하면 결과로 생성되는 바이너리 실행 파일의 크기를 크게 줄일 수 있습니다.

컴파일과 링크를 각각 진행한다면 [/OPT:REF](opt-optimizations.md) 링커 옵션으로 **/Gw** 옵션으로 컴파일된 개체 파일에서 참조되지 않은 전역 데이터를 실행 파일에서 제외할 수 있습니다.

또한 [/OPT:ICF](opt-optimizations.md)와 [/LTCG](ltcg-link-time-code-generation.md) 링커 옵션을 함께 사용하여 **/Gw**옵션으로 컴파일된 여러 개체 파일에서 동일한 모든 읽기 전용 전역 데이터를 병합할 수 있습니다.

자세한 내용은 C++ 팀 블로그에서 [/Gw 컴파일러 스위치 소개](https://devblogs.microsoft.com/cppblog/introducing-gw-compiler-switch/)를 참조하세요.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. **C/C++** 폴더를 선택합니다.

1. **명령줄** 속성 페이지를 선택합니다.

1. **/Gw**를 포함하도록 **추가 옵션** 속성을 수정한 후 **확인**을 선택합니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
