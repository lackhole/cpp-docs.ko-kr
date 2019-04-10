---
title: /execution-charset (실행 문자 집합 설정)
ms.date: 02/06/2019
f1_keywords:
- execution-charset
- /execution-charset
helpviewer_keywords:
- /execution-charset compiler option
- -execution-charset compiler option
ms.assetid: 0e02f487-2236-45bc-95f3-5760933a8f96
ms.openlocfilehash: 0a140bf438a44df152b1578f4569a087a604061c
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57807717"
---
# <a name="execution-charset-set-execution-character-set"></a>/execution-charset (실행 문자 집합 설정)

실행 문자 집합에 실행 파일을 지정할 수 있습니다.

## <a name="syntax"></a>구문

```
/execution-charset:[IANA_name|.CPID]
```

## <a name="arguments"></a>인수

*IANA_name*<br/>
IANA 정의한 문자 집합 이름입니다.

*CPID*<br/>
코드 페이지 식별자입니다.

## <a name="remarks"></a>설명

사용할 수는 **/execution-charset** 실행 문자 집합을 지정 하는 옵션입니다. 실행 문자 집합에는 모든 단계를 전처리 하는 컴파일 단계를 입력 하는 프로그램의 텍스트에 사용 되는 인코딩입니다. 이 문자 집합은 컴파일된 코드에서 문자열 또는 문자 리터럴을 내부 표현에 사용 됩니다. 기본 실행 문자 집합으로 표현할 수 없는 문자를 포함 하는 소스 파일을 사용 하는 확장 된 실행 문자 집합을 지정 하려면이 옵션을 설정 합니다. IANA 중 하나를 사용할 수 있습니다 또는 ISO 문자 집합 이름을 사용 하도록 설정 하는 문자를 지정 하려면 3 ~ 5 자리 10 진수 코드 페이지 식별자가 뒤에 점 (.). 문자 집합 이름 목록이 지원 코드 페이지 식별자를 참조 하세요 [코드 페이지 식별자](/windows/desktop/Intl/code-page-identifiers)합니다.

기본적으로 Visual Studio는 바이트 순서 표시를 검색하여 소스 파일이 인코딩된 유니코드 형식(예: UTF-16 또는 UTF-8)인지 확인합니다. 바이트 순서 표시가 없으면 **/source-charset** 옵션이나 /utf-8 옵션을 사용하여 문자 집합 이름이나 코드 페이지를 지정하지 않은 경우 현재 사용자 코드 페이지를 사용하여 소스 파일이 인코딩된 것으로 가정합니다.**** Visual Studio에서는 여러 문자 인코딩 중 하나를 사용하여 C++ 소스 코드를 저장할 수 있습니다. 소스 및 실행 문자 집합에 대한 자세한 내용은 언어 설명서의 [문자 집합](../../cpp/character-sets.md)을 참조하세요.

소스 문자 집합과 실행 문자 집합 모두 u t F-8로 설정 하려는 경우 사용할 수 있습니다 합니다 **/utf-8** 바로 가기로 컴파일러 옵션입니다. 지정 하는 것과 같습니다 **원본-charset:utf-8 /execution-charset:utf-8** 명령줄에서. 이러한 옵션도 사용 하도록 설정 합니다 **/validate-charset** 옵션이 기본적으로 합니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. **구성 속성**, **C/C++**, **명령줄** 폴더를 확장합니다.

1. **추가 옵션**를 추가 합니다 **/execution-charset** 옵션을 선택한 기본 인코딩을 지정 합니다.

1. **확인**을 선택하여 변경 내용을 저장합니다.

## <a name="see-also"></a>참고자료

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)<br/>
[/source-charset(소스 문자 집합 설정)](source-charset-set-source-character-set.md)<br/>
[/utf-8(소스 및 실행 파일 문자 집합을 UTF-8로 설정)](utf-8-set-source-and-executable-character-sets-to-utf-8.md)<br/>
[/validate-charset(호환 문자에 대한 유효성 검사)](validate-charset-validate-for-compatible-characters.md)
