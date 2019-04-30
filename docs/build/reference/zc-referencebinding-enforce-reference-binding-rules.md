---
title: '/Zc: referencebinding (참조 바인딩 규칙 적용)'
ms.date: 03/06/2018
f1_keywords:
- referenceBinding
- /Zc:referenceBinding
helpviewer_keywords:
- -Zc compiler options (C++)
- referenceBinding
- Enforce reference binding rules
- /Zc compiler options (C++)
- Zc compiler options (C++)
ms.assetid: 0c6cfaac-9c2a-41a3-aa94-64ca8ef261fc
ms.openlocfilehash: 9dfe8f5b4713d9567f6e98af6685c552fb51160e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62316108"
---
# <a name="zcreferencebinding-enforce-reference-binding-rules"></a>/Zc: referencebinding (참조 바인딩 규칙 적용)

경우는 **/zc: referencebinding** 옵션을 지정 하면 컴파일러 임시 바인딩할 비 const lvalue 참조를 허용 하지 않습니다.

## <a name="syntax"></a>구문

> **/Zc:referenceBinding**[**-**]

## <a name="remarks"></a>설명

하는 경우 **/zc: referencebinding** 지정 된 컴파일러는 c++11 표준의 섹션 8.5.3 따르며 임시 사용자 정의 형식 비 const lvalue 참조에 바인딩하는 식으로 허용 하지 않습니다. 기본적으로 이거나 **/Zc:referenceBinding-** 를 지정 하면 컴파일러는 이러한 식은 Microsoft 확장으로 허용 하지만 수준 4 경고가 발생 합니다. 코드 보안, 이식성 및 규칙을 사용 하는 권장 **/zc: referencebinding**합니다.

합니다 **/zc: referencebinding** 옵션은 기본적으로 해제 되어 있습니다. 합니다 [/ permissive-](permissive-standards-conformance.md) 컴파일러 옵션에는 암시적으로이 옵션을 설정 하지만 사용 하 여 재정의할 수 있습니다 **/Zc:referenceBinding-** 합니다.

## <a name="example"></a>예제

이 샘플에서는 사용자 정의 형식의 임시 비 const lvalue 참조에 바인딩할 수 있도록 Microsoft 확장을 보여 줍니다.

```cpp
// zcreferencebinding.cpp
struct S {
};

void f(S&) {
}

S g() {
    return S{};
}

void main() {
    S& s = g();         // warning C4239 at /W4
    const S& cs = g();  // okay, bound to const ref
    f(g());             // Extension: error C2664 only if /Zc:referenceBinding
}
```

Visual C++의 규칙과 관련된 문제에 대한 자세한 내용은 [Nonstandard Behavior](../../cpp/nonstandard-behavior.md)을 참조하세요.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. **구성 속성** > **C/C++** > **명령줄** 속성 페이지를 선택합니다.

1. 수정 된 **추가 옵션** 포함할 속성을 **/zc: referencebinding** 를 선택한 후 **확인**합니다.

## <a name="see-also"></a>참고자료

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)<br/>
[/Zc(규칙)](zc-conformance.md)<br/>
