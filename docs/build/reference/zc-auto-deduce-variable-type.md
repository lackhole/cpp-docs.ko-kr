---
title: /Zc:auto(변수 형식 추론)
ms.date: 02/28/2018
f1_keywords:
- /Zc:auto
helpviewer_keywords:
- -Zc compiler options (C++)
- Deduce variable type (C++)
- /Zc compiler options (C++)
- Zc compiler options (C++)
ms.assetid: 5f5bc102-44c3-4688-bbe1-080594dcee5c
ms.openlocfilehash: 9609bc484310fbc9999182add384eb4e438378bf
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2019
ms.locfileid: "65446234"
---
# <a name="zcauto-deduce-variable-type"></a>/Zc:auto(변수 형식 추론)

합니다 **/zc: auto [-]** 컴파일러 옵션 컴파일러를 사용 하는 방법을 지시 합니다 [auto 키워드](../../cpp/auto-keyword.md) 변수를 선언 하 합니다. 기본 옵션을 지정 하면 **/zc: auto**, 컴파일러는 초기화 식에서 선언 된 변수의 형식을 추론 합니다. 지정 하는 경우 **/zc: auto-** 를 컴파일러가 자동 저장소 클래스에 변수를 할당 합니다.

## <a name="syntax"></a>구문

> **/Zc:auto**[**-**]

## <a name="remarks"></a>설명

C++ 표준에는 `auto` 키워드의 원래 의미와 수정된 의미가 정의되어 있습니다. Visual Studio 2010 이전 키워드는 자동 저장소 클래스에서 변수를 선언 즉, 변수에는 로컬 수명을 갖고 있습니다. Visual Studio 2010부터 키워드는 선언의 초기화 식에서 변수 형식을 추론 합니다. 사용 합니다 **/zc: auto [-]** 컴파일러 옵션의 원래 또는 수정 된 의미를 사용 하도록 컴파일러에 지시 하는 `auto` 키워드입니다. 합니다 **/zc: auto** 옵션이 기본적으로 켜져 있습니다. 합니다 [/ permissive-](permissive-standards-conformance.md) 옵션의 기본 설정은 변경 되지 않습니다 **/zc: auto**합니다.

경우 적절 한 진단 메시지를 컴파일러가 사용 합니다 `auto` 키워드 현재 모순 **/zc: auto** 컴파일러 옵션입니다. 자세한 내용은 [auto 키워드](../../cpp/auto-keyword.md)합니다. 시각적 개체를 사용 하 여 규칙과 관련 된 문제에 대 한 자세한 내용은 C++를 참조 하세요 [비표준 동작](../../cpp/nonstandard-behavior.md)합니다.

### <a name="to-set-this-compiler-option-in-visual-studio"></a>Visual Studio에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. **구성 속성** > **C/C++** > **명령줄** 속성 페이지를 선택합니다.

1. 추가 **/zc: auto** 하거나 **/zc: auto-** 하는 **추가 옵션:** 창.

## <a name="see-also"></a>참고자료

[/Zc(규칙)](zc-conformance.md)<br/>
[auto 키워드](../../cpp/auto-keyword.md)
