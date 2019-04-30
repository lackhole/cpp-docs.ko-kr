---
title: 템플릿 ref 클래스(C++/CX)
ms.date: 01/22/2017
ms.assetid: a24d5f45-8dbb-4540-958f-c76c90d8ed93
ms.openlocfilehash: 4398cc2c545a57277289a6aa41fc4664d9734eed
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62396039"
---
# <a name="template-ref-classes-ccx"></a>템플릿 ref 클래스(C++/CX)

C++ 템플릿은 메타데이터에 게시되지 않으므로 프로그램에서 public 또는 protected 액세스 가능성을 가질 수 없습니다. 물론 표준 C++ 템플릿을 프로그램에서 내부적으로 사용할 수 있습니다. 또한 private ref 클래스를 템플릿으로 정의하고 명시적으로 특수화된 템플릿 ref 클래스를 public ref 클래스에서 private 멤버로 선언할 수 있습니다.

## <a name="authoring-ref-class-templates"></a>ref 클래스 템플릿 작성

다음 예제에서는 private ref 클래스를 템플릿으로 선언하는 방법 및 표준 C++ 템플릿을 선언하는 방법과 이 둘을 public ref 클래스에서 멤버로 선언하는 방법을 보여 줍니다. 표준 C++ platform:: string이 예제의 Windows 런타임 형식으로 템플릿 특수화 될 수 있습니다 ^ 합니다.

[!code-cpp[cx_templates#01](../cppcx/codesnippet/CPP/templatedemo/class1.h#01)]

## <a name="see-also"></a>참고자료

[형식 시스템(C++/CX)](../cppcx/type-system-c-cx.md)<br/>
[Visual C++ 언어 참조](../cppcx/visual-c-language-reference-c-cx.md)<br/>
[네임스페이스 참조](../cppcx/namespaces-reference-c-cx.md)
