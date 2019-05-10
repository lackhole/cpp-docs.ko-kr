---
title: /Zc:trigraphs(삼중자 대체)
ms.date: 03/06/2018
f1_keywords:
- /Zc
helpviewer_keywords:
- -Zc compiler options (C++)
- /Zc compiler options (C++)
- Conformance compiler options
- Zc compiler options (C++)
ms.assetid: e3d6058f-400d-4966-a3aa-800cfdf69cbf
ms.openlocfilehash: 7a20123603030dfe719cd8990018f795df137981
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62316004"
---
# <a name="zctrigraphs-trigraphs-substitution"></a>/Zc:trigraphs(삼중자 대체)

때 **/zc: trigraphs** 를 지정 하면 컴파일러가 해당 문장 부호 문자를 사용 하 여 삼중 자 문자 시퀀스를 바꿉니다.

## <a name="syntax"></a>구문

> **/Zc:trigraphs**[**-**]

## <a name="remarks"></a>설명

A *삼중 자* 두 개의 연속 물음표 이루어져 있습니다 ("??") 뒤에 고유한 세 번째 문자입니다. C 언어 표준 특정 문장 부호 문자에 대 한 편리한 그래픽 표현을 포함 하지 않는 문자 집합을 사용 하는 원본 파일에 삼중 자를 지원 합니다. 예를 들어, trigraphs을 사용 하는 경우 컴파일러 대체는 "?? = "삼중 자를 '#' 문자를 사용 하 여 합니다. C + + 14를 통해 삼중 자는 C.와 같이 지원 C++17 표준에서 삼중 자 제거는 C++ 언어입니다. C++ 코드를 **/zc: trigraphs** 컴파일러 옵션 해당 문장 부호 문자로 대체 삼중 자 시퀀스를 사용 하도록 설정 합니다. **/Zc:trigraphs-** 삼중 자 대체를 사용 하지 않도록 설정 합니다.

**/zc: trigraphs** 옵션은 기본적으로 해제 되어 및 옵션은 없을 때 영향을 받는 합니다 [관대 한 /-](permissive-standards-conformance.md) 옵션을 지정 합니다.

C의 목록은 /C++ 삼중 자 및 삼중 자를 사용 하는 방법을 보여 주는 예제를 참조 하세요 [삼중 자](../../c-language/trigraphs.md)합니다.

## <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. **구성 속성** > **C/C++** > **명령줄** 속성 페이지를 선택합니다.

1. 수정 된 **추가 옵션** 포함할 속성을 **/zc: trigraphs** 또는 **/Zc:trigraphs-** 를 선택한 후 **확인**합니다.

## <a name="see-also"></a>참고자료

[/Zc(규칙)](zc-conformance.md)<br/>
[삼중자](../../c-language/trigraphs.md)<br/>
