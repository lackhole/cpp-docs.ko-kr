---
title: /utf-8 (원본 및 실행 파일 문자 집합을 u t f-8로 설정)
ms.date: 11/04/2016
f1_keywords:
- /utf-8
helpviewer_keywords:
- /utf-8 compiler option
ms.assetid: f0e1f3cb-6cae-46eb-9483-04ed13d9b504
ms.openlocfilehash: 1ff0f23ad0758642c73b1b35d6d4dd1be20899cb
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69498174"
---
# <a name="utf-8-set-source-and-executable-character-sets-to-utf-8"></a>/utf-8 (원본 및 실행 파일 문자 집합을 u t f-8로 설정)

소스 문자 집합과 실행 문자 집합을 u t f-8로 지정 합니다.

## <a name="syntax"></a>구문

```
/utf-8
```

## <a name="remarks"></a>설명

**/Utf-8** 옵션을 사용 하 여 소스 및 실행 문자 집합을 u t f-8을 사용 하 여 인코딩된 것으로 지정할 수 있습니다. 명령줄에서 **/source-charset: utf-8/source-charset: u t f-8** 을 지정 하는 것과 같습니다. 이러한 옵션을 사용 하면 기본적으로 **/validate-charset** 옵션이 사용 됩니다. 지원 되는 코드 페이지 식별자 및 문자 집합 이름 목록은 [코드 페이지 식별자](/windows/win32/Intl/code-page-identifiers)를 참조 하세요.

기본적으로 Visual Studio는 바이트 순서 표시를 검색하여 소스 파일이 인코딩된 유니코드 형식(예: UTF-16 또는 UTF-8)인지 확인합니다. 바이트 순서 표시가 없는 경우 **/utf-8** 또는 **/source-charset** 옵션을 사용 하 여 코드 페이지를 지정 하지 않으면 현재 사용자 코드 페이지를 사용 하 여 소스 파일이 인코딩된 것으로 가정 합니다. Visual Studio에서는 여러 문자 인코딩 중 하나를 사용하여 C++ 소스 코드를 저장할 수 있습니다. 소스 및 실행 문자 집합에 대한 자세한 내용은 언어 설명서의 [문자 집합](../../cpp/character-sets.md)을 참조하세요.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. **구성 속성**, **C/C++** , **명령줄** 폴더를 확장합니다.

1. **추가 옵션**에서 **/utf-8** 옵션을 추가 하 여 기본 설정 인코딩을 지정 합니다.

1. **확인**을 선택하여 변경 내용을 저장합니다.

## <a name="see-also"></a>참고자료

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)<br/>
[/sv-ecin 문자 집합 (실행 문자 집합 설정)](execution-charset-set-execution-character-set.md)<br/>
[/source-charset(소스 문자 집합 설정)](source-charset-set-source-character-set.md)<br/>
[/validate-charset(호환 문자에 대한 유효성 검사)](validate-charset-validate-for-compatible-characters.md)
