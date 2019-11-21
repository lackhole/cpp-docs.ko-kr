---
title: '/o실험적: 전처리기 (전처리기 규칙 모드 사용)'
description: '/O실험적: 전처리기 컴파일러 옵션을 사용 하 여 표준에 맞는 전처리기에 대해 실험적 컴파일러 지원을 사용 하도록 설정할 수 있습니다.'
ms.date: 10/31/2019
f1_keywords:
- preprocessor
- /experimental:preprocessor
helpviewer_keywords:
- preprocessor conformance
- /experimental:preprocessor
- Enable preprocessor conformance mode
ms.openlocfilehash: cb1ac63d2c12083975139455d8625544cb419adf
ms.sourcegitcommit: 2362d15b5eb18d27773c3f7522da3d0eed9e2571
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2019
ms.locfileid: "73754046"
---
# <a name="experimentalpreprocessor-enable-preprocessor-conformance-mode"></a>/o실험적: 전처리기 (전처리기 규칙 모드 사용)

이 옵션을 사용 하면 C99 전처리기 기능을 비롯 하 여 c + + 11 표준을 보다 긴밀 하 게 준수 하는 실험적 토큰 기반 전처리기를 사용할 수 있습니다. 자세한 내용은 [MSVC 실험적 전처리기 개요](../../preprocessor/preprocessor-experimental-overview.md)를 참조 하세요.

## <a name="syntax"></a>구문

> **/sb: 전처리기**[ **-** ]

## <a name="remarks"></a>주의

**/B실험적: 전처리기** 컴파일러 옵션을 사용 하 여 전처리기에 맞는 실험을 사용 하도록 설정 합니다. **/O실험적: 전처리기-** 옵션을 사용 하 여 기존 전처리기를 명시적으로 지정할 수 있습니다.

**/S실험적: 전처리기** 옵션은 Visual Studio 2017 버전 15.8부터 사용할 수 있습니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. **구성 속성** > **C/C++**  > **명령줄** 속성 페이지를 선택합니다.

1. **/S실험적: 전처리기** 를 포함 하도록 **추가 옵션** 속성을 수정한 다음 **확인**을 선택 합니다.

## <a name="see-also"></a>참조

[/Zc(규칙)](zc-conformance.md)
