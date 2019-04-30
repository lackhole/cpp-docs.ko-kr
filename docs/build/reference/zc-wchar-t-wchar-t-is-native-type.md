---
title: /Zc:wchar_t(wchar_t를 네이티브 형식으로 인식)
ms.date: 03/01/2018
f1_keywords:
- VC.Project.VCCLWCECompilerTool.TreatWChar_tAsBuiltInType
- VC.Project.VCCLCompilerTool.TreatWChar_tAsBuiltInType
- /Zc:wchar_t
helpviewer_keywords:
- /Zc compiler options [C++]
- -Zc compiler options [C++]
- wchar_t type
- Conformance compiler options
- Zc compiler options [C++]
ms.assetid: b0de5a84-da72-4e5a-9a4e-541099f939e0
ms.openlocfilehash: b2563ba0ae2a07bc9f9d81128745ed4b9651fb6c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62315640"
---
# <a name="zcwchart-wchart-is-native-type"></a>/Zc:wchar_t(wchar_t를 네이티브 형식으로 인식)

C++ 표준에 따라 `wchar_t`를 기본 제공 형식으로 구문 분석합니다.

## <a name="syntax"></a>구문

> **/Zc:wchar_t**[**-**]

## <a name="remarks"></a>설명

하는 경우 **/zc: wchar_t** 켜져 `wchar_t` 로 컴파일된 코드에서 기본 제공 정수 계열 형식에 대 한 키워드는 C++. 하는 경우 **/zc: wchar_t-** (빼기 기호)로 지정 하거나 코드에서 C로 컴파일된, `wchar_t` 기본 제공 형식이 아닙니다. 대신 `wchar_t` 으로 정의 되는 `typedef` 에 대 한 `unsigned short` canonical 헤더 stddef.h에 합니다. (Microsoft에서 구현한 정의 다른 표준 헤더 stddef.h로 포함 되는 다른 헤더에 함.)

하지 않는 것이 좋습니다 **/zc: wchar_t-** 때문에 C++ 표준에서는 `wchar_t` 기본 제공 형식 이어야 합니다. `typedef` 버전을 사용하면 이식성 문제가 발생할 수 있습니다. 시각적 개체의 이전 버전에서 업그레이드 하는 경우 C++ 컴파일러 오류 발생 [C2664](../../error-messages/compiler-errors-2/compiler-error-c2664.md) 코드를 암시적으로 변환 하 려 하기 때문에 `wchar_t` 에 `unsigned short`, 오류를 해결 하는 코드를 변경 하는 것이 좋습니다 설정 하는 대신 **/zc: wchar_t-** 합니다.

합니다 **/zc: wchar_t** 옵션이 기본적으로 켜져 C++ 컴파일에 C 컴파일에서 무시 됩니다. 합니다 [/ permissive-](permissive-standards-conformance.md) 옵션이 적용 되지 않습니다 **/zc: wchar_t**합니다.

Microsoft는 `wchar_t`를 2바이트 부호 없는 값으로 구현합니다. Microsoft 전용 네이티브 형식으로 매핑됩니다 `__wchar_t`합니다. 에 대 한 자세한 내용은 `wchar_t`를 참조 하세요 [데이터 형식 범위](../../cpp/data-type-ranges.md) 하 고 [기본 형식](../../cpp/fundamental-types-cpp.md)합니다.

계속 사용 하는 이전 코드와 상호 운용 하는 새 코드를 작성 하는 경우는 `typedef` 버전이 `wchar_t`, 둘 다에 대해 오버 로드를 제공할 수 있습니다 합니다 `unsigned short` 및 `__wchar_t` 다양 한 `wchar_t`코드를 사용 하 여 연결할 수 있도록 로 컴파일된 코드 **/zc: wchar_t** 또는 그것으로 컴파일되지 않은 코드입니다. 서로 다른 두 라이브러리를 사용 하 여 하나 및 없는 빌드의 수를 제공 하는 것이 고, 그렇지 **/zc: wchar_t** 사용 하도록 설정 합니다. 그러나 이 경우 새 코드를 컴파일하는 데 사용하는 것과 같은 컴파일러를 사용하여 이전 코드를 빌드하는 것이 좋습니다. 다른 컴파일러로 컴파일된 이진 파일을 혼합해서는 안 됩니다.

때 **/zc: wchar_t** 를 지정 하면  **\_WCHAR\_T\_정의** 하 고  **\_네이티브\_WCHAR\_T\_정의** 기호가 정의 됩니다. 자세한 내용은 [Predefined Macros](../../preprocessor/predefined-macros.md)을 참조하십시오.

코드 때문에 컴파일러 COM 전역 함수를 사용 하는 경우 **/zc: wchar_t** 기본적으로 좋습니다 comsupp.lib에 대 한 명시적 참조를 변경 하는 이제 (에서 합니다 [주석 pragma](../../preprocessor/comment-c-cpp.md) 또는 명령줄)에서는 comsuppw.lib 또는 comsuppwd.lib를 합니다. (사용 하 여 컴파일해야 **/zc: wchar_t-**, comsupp.lib를 사용 합니다.) comdef.h 헤더 파일을 포함하는 경우 올바른 라이브러리가 지정됩니다. 컴파일러 COM 지원에 대 한 자세한 내용은 [컴파일러 COM 지원](../../cpp/compiler-com-support.md)합니다.

`wchar_t` C 코드를 컴파일할 때에 기본 제공 형식이 지원 되지 않습니다. 시각적 개체를 사용 하 여 규칙과 관련 된 문제에 대 한 자세한 내용은 C++를 참조 하세요 [비표준 동작](../../cpp/nonstandard-behavior.md)합니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. 선택 된 **구성 속성** > **C /C++** > **언어** 페이지입니다.

1. 수정 된 **wchar_t를 기본 제공 형식으로 처리** 속성입니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.TreatWChar_tAsBuiltInType%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[/Zc(규칙)](zc-conformance.md)<br/>
