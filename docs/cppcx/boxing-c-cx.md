---
title: Boxing(C++/CX)
ms.date: 12/30/2016
ms.assetid: edfb12fa-2a9b-42f6-bdac-d4d76cb8274e
ms.openlocfilehash: 90c5af31efc6523683227dbf54c85390bc98510a
ms.sourcegitcommit: 180f63704f6ddd07a4172a93b179cf0733fd952d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70740675"
---
# <a name="boxing-ccx"></a>Boxing(C++/CX)

*boxing* 은 [Windows::Foundation::DateTime](/uwp/api/windows.foundation.datetime)과 같은 값 형식 변수 또는 `int`와 같은 기본 스칼라 형식이 [Platform::Object^](../cppcx/platform-object-class.md) 을 해당 입력 형식으로 사용하는 메서드에 전달될 때 해당 변수를 ref 클래스에 래핑합니다.

## <a name="passing-a-value-type-to-an-object-parameter"></a>Object^ 매개 변수에 값 형식 전달

[Platform::Object^](../cppcx/platform-object-class.md)형식의 메서드 매개 변수에 전달하기 위해 명시적으로 변수를 boxing할 필요는 없지만 이전에 boxing된 값을 검색할 때는 명시적으로 원래 형식으로 캐스팅해야 합니다.

[!code-cpp[cx_boxing#01](../cppcx/codesnippet/CPP/cx_boxing/class1.cpp#01)]

### <a name="using-platformiboxt-to-support-nullable-value-types"></a>Platform:: ibox\<T >를 사용 하 여 nullable 값 형식 지원

C# 및 Visual Basic에서는 null 허용 값 형식의 개념을 지원합니다. C++/Cx에서는 `Platform::IBox<T>` 형식을 사용 하 여 nullable 값 형식 매개 변수를 지 원하는 공용 메서드를 노출할 수 있습니다. 다음 예제에서는 호출자가 C++인수 중 하나에 대해 null을 C# 전달 하는 경우 null을 반환 하는/cx 공용 메서드를 보여 줍니다.

[!code-cpp[cx_boxing#02](../cppcx/codesnippet/CPP/cx_boxing/class1.h#02)]

C# XAML 클라이언트에서 이러한 메서드를 다음과 같이 사용할 수 있습니다.

```

// C# client code
    BoxingDemo.Class1 obj = new BoxingDemo.Class1();
    int? a = null;
    int? b = 5;
    var result = obj.Multiply(a,b); //result = null
```

## <a name="see-also"></a>참고자료

[형식 시스템(C++/CX)](../cppcx/type-system-c-cx.md)<br/>
[캐스팅(C++/CX)](../cppcx/casting-c-cx.md)<br/>
[C++/CX 언어 참조](../cppcx/visual-c-language-reference-c-cx.md)<br/>
[네임스페이스 참조](../cppcx/namespaces-reference-c-cx.md)
