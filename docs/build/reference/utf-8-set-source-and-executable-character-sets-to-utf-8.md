---
title: /utf-8 (소스 및 실행 문자 집합을 u t F-8)
ms.date: 11/04/2016
f1_keywords:
- /utf-8
helpviewer_keywords:
- /utf-8 compiler option
ms.assetid: f0e1f3cb-6cae-46eb-9483-04ed13d9b504
ms.openlocfilehash: 5ac15c63041e76b8bb0d292868bb982c21866078
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57812293"
---
# <a name="utf-8-set-source-and-executable-character-sets-to-utf-8"></a>/utf-8 (소스 및 실행 문자 집합을 u t F-8)

소스 문자 집합 및 u t F-8로 실행 문자 집합을 지정 합니다.

## <a name="syntax"></a>구문

```
/utf-8
```

## <a name="remarks"></a>설명

사용할 수는 **/utf-8** 인코딩 u t F-8을 사용 하 여 소스 및 실행 문자 집합을 지정 하는 옵션입니다. 지정 하는 것과 같습니다 **원본-charset:utf-8 /execution-charset:utf-8** 명령줄에서. 이러한 옵션도 사용 하도록 설정 합니다 **/validate-charset** 옵션이 기본적으로 합니다. 문자 집합 이름 목록이 지원 코드 페이지 식별자를 참조 하세요 [코드 페이지 식별자](/windows/desktop/Intl/code-page-identifiers)합니다.

Visual Studio는 기본적으로 인지 하는 경우 소스 파일 인코딩된 유니코드 형식으로 예를 들어, utf-16 또는 u t F-8 바이트 순서 표시를 검색 합니다. 바이트 순서 표시가 없는 경우 소스 파일은 인코딩된 현재 사용자 코드 페이지를 사용 하는 코드 페이지를 사용 하 여 지정 하지 않으면 가정 **/utf-8** 또는 **/source-charset** 옵션입니다. Visual Studio를 사용 하면 여러 문자 인코딩 중 하나를 사용 하 여 c + + 소스 코드를 저장할 수 있습니다. 소스 및 실행 문자 집합에 대 한 정보를 참조 하세요 [문자 집합](../../cpp/character-sets.md) 언어 설명서에 있습니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 설정 c + + 컴파일러 및 빌드 속성](../working-with-project-properties.md)합니다.

1. 확장 된 **구성 속성**, **C/c + +** 를 **명령줄** 폴더입니다.

1. **추가 옵션**를 추가 합니다 **/utf-8** 기본 인코딩을 지정 하는 옵션입니다.

1. **확인**을 선택하여 변경 내용을 저장합니다.

## <a name="see-also"></a>참고자료

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)<br/>
[/execution-charset (실행 문자 집합 설정)](execution-charset-set-execution-character-set.md)<br/>
[/source-charset(소스 문자 집합 설정)](source-charset-set-source-character-set.md)<br/>
[/validate-charset(호환 문자에 대한 유효성 검사)](validate-charset-validate-for-compatible-characters.md)
