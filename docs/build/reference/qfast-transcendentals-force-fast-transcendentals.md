---
title: /Qfast_transcendentals(빠른 초월수 강제 적용)
ms.date: 11/04/2016
f1_keywords:
- /Qfast_transcendentals
helpviewer_keywords:
- /Qfast_transcendentals
- Force Fast Transcendentals
ms.assetid: 4de24bd1-38e6-49d4-9a05-04c9937d24ac
ms.openlocfilehash: 383a915721d627367ca2ca035957df947996bbe2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62319319"
---
# <a name="qfasttranscendentals-force-fast-transcendentals"></a>/Qfast_transcendentals(빠른 초월수 강제 적용)

초월 함수에 대한 인라인 코드를 생성합니다.

## <a name="syntax"></a>구문

```
/Qfast_transcendentals
```

## <a name="remarks"></a>설명

이 컴파일러 옵션은 초월수 함수 실행 속도 개선 하기 위해 인라인 코드를 변환할 수 있습니다. 이 옵션은 함께 사용 하는 경우에 효과가 **/fp: 제외한** 또는 **/fp: 정확한**합니다. 기본 동작에서 이미 초월 함수에 대 한 인라인 코드를 생성할 **/fp:fast**합니다.

이 옵션을 사용 하 여 호환 되지 **/fp: strict**합니다. 참조 [/fp (부동 소수점 동작 지정)](fp-specify-floating-point-behavior.md) 부동 소수점 컴파일러 옵션에 대 한 자세한 내용은 합니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. **C/C++** 폴더를 클릭합니다.

1. **명령줄** 속성 페이지를 클릭합니다.

1. **추가 옵션** 상자에 컴파일러 옵션을 입력합니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[/Q 옵션(하위 수준 작업)](q-options-low-level-operations.md)<br/>
[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
