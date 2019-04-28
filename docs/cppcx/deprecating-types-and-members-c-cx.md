---
title: 형식 및 멤버가 사용되지 않도록 지정(C++/CX)
ms.date: 12/30/2016
ms.assetid: b20b01c1-a439-4ff0-8cf3-d7280c492813
ms.openlocfilehash: 7f488dfa522c0b48c75150d40584b0946baae806
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62301502"
---
# <a name="deprecating-types-and-members-ccx"></a>형식 및 멤버가 사용되지 않도록 지정(C++/CX)

C++/CX를 사용 하 여 생산자와 소비자에 대 한 Windows 런타임 형식 및 멤버의 사용을 중단 합니다 [사용 되지 않음](/uwp/api/windows.foundation.metadata.deprecatedattribute) 특성은 지원 합니다. 이 속성이 적용된 API를 사용하는 경우 API가 더 이상 사용되지 않음을 나타내고 대체 API를 사용하도록 권장하는 컴파일 타임 경고 메시지가 나타납니다. public 형식 및 메서드에서 이 특성을 적용하고 사용자 지정 메시지를 제공할 수 있습니다.

> [!CAUTION]
> 합니다 [사용 되지 않는](/uwp/api/windows.foundation.metadata.deprecatedattribute) 특성은 Windows 런타임 형식에만 사용 합니다. 표준 C++ 클래스 및 멤버에는 [__declspec(deprecated)](../cpp/deprecated-cpp.md)를 사용하세요.

### <a name="example"></a>예제

다음 예제에서는 Windows 런타임 구성 요소에서 사용자 고유의 공용 API를 사용할 수 없게 하는 방법을 보여 줍니다. [Windows:Foundation::Metadata::DeprecationType](/uwp/api/windows.foundation.metadata.deprecationtype) 형식의 두 번째 매개 변수는 API를 사용할 수 없게 할지 제거할지 여부를 지정합니다. 현재는 DeprecationType::Deprecated 값만 지원됩니다. 특성의 세 번째 매개 변수는 특성이 적용되는 [Windows::Foundation::Metadata::Platform](/uwp/api/windows.foundation.metadata.platformattribute) 을 지정합니다.

```

namespace wfm = Windows::Foundation::Metadata;

public ref class Bicycle sealed
{

public:
    property double Speed;

    [wfm::Deprecated("Use the Speed property to compute the angular speed of the wheel", wfm::DeprecationType::Deprecate, 0x0)]
    double ComputeAngularVelocity();
};
```

## <a name="supported-targets"></a>지원되는 대상

다음 표에서는 Deprecated 특성이 적용될 수 있는 구문을 보여 줍니다.

| |
|-|
|XAML 컨트롤|
|대리자(delegate)|
|이벤트(event)|
|열거형 필드|
|enum|
|struct|
|메서드|
|클래스|
|interface(인터페이스)|
|속성|
|구조체 필드|
|매개 변수가 있는 생성자|

## <a name="see-also"></a>참고자료

[형식 시스템](../cppcx/type-system-c-cx.md)<br/>
[Visual C++ 언어 참조](../cppcx/visual-c-language-reference-c-cx.md)<br/>
[네임스페이스 참조](../cppcx/namespaces-reference-c-cx.md)
