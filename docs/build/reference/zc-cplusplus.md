---
title: '/Zc: __cplusplus (업데이트 __cplusplus 매크로 사용)'
ms.date: 05/30/2018
f1_keywords:
- /Zc:__cplusplus
helpviewer_keywords:
- -Zc:__cplusplus compiler option (C++)
- __cplusplus macro (C++)
ms.openlocfilehash: 89545f541f32374a47dce7f87958e61873c1b47c
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57810096"
---
# <a name="zccplusplus-enable-updated-cplusplus-macro"></a>/Zc: __cplusplus (업데이트 __cplusplus 매크로 사용)

**/zc: __cplusplus** 컴파일러 옵션이 사용 하도록 설정 합니다  **\_ \_cplusplus** 전처리기 매크로를 최신 c + + 언어 표준 지원에 대 한 업데이트 된 값을 보고 합니다. 기본적으로 Visual Studio 항상 값 "199711 L"을 반환 합니다  **\_ \_cplusplus** 전처리기 매크로입니다.

## <a name="syntax"></a>구문

> **/Zc:__cplusplus**[**-**]

## <a name="remarks"></a>설명

합니다  **\_ \_cplusplus** 전처리기 매크로 c + + 표준의 특정 버전을 지 원하는 보고서 일반적으로 사용 됩니다. 기존 코드를 많이 "199711 L"와 일치 하는이 매크로의 값에 따라 달라 지도록 나타나므로 컴파일러 변경 되지 않습니다 매크로의 값을 명시적으로 옵트인 할를 사용 하 여 경우가 아니면 합니다 **/zc: __cplusplus** 컴파일러 옵션입니다. 합니다 **/zc: __cplusplus** 옵션 Visual Studio 2017 버전 15.7부터 사용할 수 있고 기본적으로 해제 되어 있습니다. 이전 버전의 Visual Studio 및 기본적으로 이거나 **/Zc:__cplusplus-** 으로 지정 되지 "199711 L" 값을 반환 하는 Visual Studio는  **\_ \_cplusplus** 전처리기 매크로입니다. [/ permissive-](permissive-standards-conformance.md) 옵션이 사용 되지 않습니다 **/zc: __cplusplus**합니다.

경우는 **/zc: __cplusplus** 옵션을 사용 하면에서 보고 된 값을  **\_ \_cplusplus** 매크로에 따라 달라 집니다를 [/std](std-specify-language-standard-version.md) 버전 스위치 설정입니다. 이 표에서 매크로 대 한 가능한 값을 보여 줍니다.

|/Zc: __cplusplus 스위치|/std:c++ 스위치|__cplusplus 값|
|-|-|-|
Zc:__cplusplus|/std: c + + 14 (기본값)|201402L
Zc:__cplusplus|/std:c++17|201703L
Zc:__cplusplus|/std:c++latest|201704L
Zc:__cplusplus-(사용 안 함)|모든 값|199711L
지정 되지 않음|모든 값|199711L

컴파일러는 C + + 98, C + + 03 또는 C + + 11 표준 스위치를 지원 하지 않습니다.

정밀 컴파일러 도구 집합에 변경 내용 검색을 사용 합니다 [_MSC_VER](../../preprocessor/predefined-macros.md) 미리 정의 된 매크로입니다. 이 기본 제공 매크로의 값은 Visual Studio 2017 이상 버전에서 모든 도구 집합 업데이트 마다 증가 됩니다. 합니다 [_MSVC_LANG](../../preprocessor/predefined-macros.md) 미리 정의 된 매크로 표준 버전을 여부를 보고 합니다 **/zc: __cplusplus** 옵션의 설정 여부입니다. 때 **/zc: __cplusplus** 을 사용 하는 `__cplusplus == _MSVC_LANG`합니다.

### <a name="to-set-this-compiler-option-in-visual-studio"></a>Visual Studio에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 하세요 [Visual Studio에서 설정 c + + 컴파일러 및 빌드 속성](../working-with-project-properties.md)합니다.

1. 선택 된 **구성 속성** > **C/c + +** > **명령줄** 속성 페이지.

1. 추가 **/zc: __cplusplus** 하거나 **/Zc:__cplusplus-** 하는 **추가 옵션:** 창.

## <a name="see-also"></a>참고자료

- [/Zc(규칙)](zc-conformance.md)
- [/std (지정 언어 표준 버전)](std-specify-language-standard-version.md)
- [미리 정의된 매크로](../../preprocessor/predefined-macros.md)
