---
title: 특성(C++/CX)
ms.date: 12/30/2016
ms.assetid: 4438e03c-4de3-433d-abcc-31aa863bc0e0
ms.openlocfilehash: 5f74914ab65fdf2c1803b47665e16378991efa3c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62209457"
---
# <a name="attributes-ccx"></a>특성(C++/CX)

특성 메타 데이터 생성에서 특정 동작을 지정 하는 Windows 런타임 형식 및 메서드에 대괄호 앞에 추가 될 수 있는 ref 클래스의 특별 한 종류입니다. 미리 정의 된 여러 특성-예를 들어 [Windows::Foundation::Metadata::WebHostHidden](/uwp/api/Windows.Foundation.Metadata.WebHostHiddenAttribute)-에서 흔히 사용 됩니다 C++/CX 코드입니다. 이 예제에서는 특성이 클래스에 적용되는 방식을 보여 줍니다.

[!code-cpp[cx_attributes#01](../cppcx/codesnippet/CPP/cx_attributes/class1.h#01)]

## <a name="custom-attributes"></a>사용자 지정 특성

사용자 지정 특성을 정의할 수도 있습니다. 사용자 지정 특성은 이러한 Windows 런타임 규칙을 따라야 합니다.

- 사용자 지정 특성에는 공용 필드만 포함될 수 있습니다.

- 사용자 지정 특성 필드는 특성이 클래스에 적용될 때 초기화될 수 있습니다.

- 필드는 다음 형식 중 하나일 수 있습니다.

   - int32(int)

   - uint32(unsigned int)

   - bool

   - Platform::String^

   - Windows::Foundation::HResult

   - Platform::Type^

   - public enum 클래스(사용자 정의 열거형 포함)

다음 예제에서는 사용자 지정 특성을 정의한 다음 사용할 때 초기화하는 방법을 보여 줍니다.

[!code-cpp[cx_attributes#02](../cppcx/codesnippet/CPP/cx_attributes/class1.h#02)]

## <a name="see-also"></a>참고자료

[형식 시스템(C++/CX)](../cppcx/type-system-c-cx.md)<br/>
[Visual C++ 언어 참조](../cppcx/visual-c-language-reference-c-cx.md)<br/>
[네임스페이스 참조](../cppcx/namespaces-reference-c-cx.md)
