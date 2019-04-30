---
title: /V(버전 번호)
ms.date: 11/04/2016
f1_keywords:
- /v
helpviewer_keywords:
- embedding version strings
- /V compiler option [C++]
- version numbers, specifying for .obj
- V compiler option [C++]
- -V compiler option [C++]
ms.assetid: 3e93fb7a-5dfd-49a6-bd49-3dca8052e0f3
ms.openlocfilehash: 7bebd3ab9677bb340203bbf857e4ee9f287e36e6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62317317"
---
# <a name="v-version-number"></a>/V(버전 번호)

더 이상 사용되지 않습니다. .Obj 파일에 텍스트 문자열을 포함합니다.

## <a name="syntax"></a>구문

```
/Vstring
```

## <a name="arguments"></a>인수

*string*<br/>
.Obj 파일에 포함할 버전 번호 또는 저작권 표시를 지정 하는 문자열입니다.

## <a name="remarks"></a>설명

버전 번호 또는 저작권 표시를 사용 하 여.obj 파일 stringcan 레이블. 문자열의 일부인 경우 공백이 나 탭 문자를 큰따옴표 (")에 묶어야 합니다. 백슬래시 (\\) 문자열의 일부인 경우 모든 큰따옴표 앞에 야 합니다. 사이 공백을 **/V** 고 `string` 선택 사항입니다.

사용할 수도 있습니다 [주석 (C /C++)](../../preprocessor/comment-c-cpp.md) .obj 파일에는 컴파일러의 이름 및 버전 번호를 배치 하는 컴파일러 주석 형식 인수를 사용 합니다.

합니다 **/V** 옵션; Visual Studio 2005부터 사용 되지 않습니다 **/V** 주로 가상 장치 드라이버 (Vxd) 빌드를 지 원하는 데 사용 되며 시각적 개체에서 더 이상 지원 되지 Vxd 빌드 C++ 도구 집합입니다. 사용 되지 않는 컴파일러 옵션의 목록을 참조 하세요 **컴파일러 옵션 및 사용 되지 않음** 에 [컴파일러 옵션 범주별 목록](compiler-options-listed-by-category.md)합니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. **C/C++** 폴더를 클릭합니다.

1. **명령줄** 속성 페이지를 클릭합니다.

1. **추가 옵션** 상자에 컴파일러 옵션을 입력합니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
