---
title: 형식 시스템(C++/CX)
ms.date: 02/03/2017
ms.assetid: b67bee8a-b526-4872-969e-ef22724e88fe
ms.openlocfilehash: fbc7a178621624e396c80509703ce1b5b4c19162
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62392091"
---
# <a name="type-system-ccx"></a>형식 시스템(C++/CX)

Windows 런타임 아키텍처를 사용 하 여 사용할 수 있습니다 C++/CX, Visual Basic, Visual C# 및 JavaScript 앱 및 직접 Windows API에 액세스 하 고 다른 Windows 런타임 앱 및 구성 요소와 상호 운용 하는 구성 요소를 작성할 수 있습니다. 유니버설 Windows 플랫폼 앱에서 작성 된 C++ CPU에서 직접 실행 하는 네이티브 코드로 컴파일합니다. C# 또는 Visual Basic에서 작성 된 유니버설 Windows 플랫폼 앱 MSIL (Microsoft intermediate language)을 컴파일하고 CLR (공용 언어 런타임)에서 실행 합니다. JavaScript로 작성 된 유니버설 Windows 플랫폼 앱에서 런타임 환경에서 실행 합니다. Windows 런타임 운영 체제 구성 요소 자체에 작성 된 C++ 네이티브 코드로 실행 합니다. 이러한 구성 요소 및 유니버설 Windows 플랫폼 앱의 모든 Windows 런타임 응용 프로그램 이진 인터페이스 ABI ()를 통해 직접 통신합니다.

최신의 Windows 런타임에 대 한 지원을 사용 하도록 설정 하려면 C++ 관용구를 생성 하는 Microsoft의 C++/CX입니다. C++/CX 제공 기본적인 Windows 런타임 구현 및 기본 제공 기본 형식을 형식 수 있도록 하는 C++ 앱 및 구성 요소가 다른 언어로 작성 된 응용 프로그램을 사용 하 여 abi 전반에서 통신 합니다. 모든 Windows 런타임 형식을 사용할 수도 있고, 클래스, 구조체, 인터페이스 및 기타 유니버설 Windows 플랫폼 앱 및 구성 요소에서 사용할 수 있는 다른 사용자 정의 형식을 만들 수 있습니다. 작성 된 유니버설 Windows 플랫폼 앱을 C++/CX 일반 이용할 수 있습니다 C++ 클래스 및 구조체를 public 액세스 가능성이 없는 하기만 합니다.

C++/CX 언어 프로젝션 및 작동 방법에 대한 자세한 내용은 다음 블로그 게시물을 참조하세요.

1. [C++/CX 파트 0 / \[n\]: 소개](https://blogs.msdn.microsoft.com/vcblog/2012/08/29/ccx-part-0-of-n-an-introduction)

1. [C++/CX 1 부 \[n\]: 간단한 클래스](https://blogs.msdn.microsoft.com/vcblog/2012/09/05/ccx-part-1-of-n-a-simple-class)

1. [C++/CX 파트 2 \[n\]: 유형](https://blogs.msdn.microsoft.com/vcblog/2012/09/17/ccx-part-2-of-n-types-that-wear-hats)

1. [C++3 부 /CX \[n\]: 공사중](https://blogs.msdn.microsoft.com/vcblog/2012/10/05/ccx-part-3-of-n-under-construction/)

1. [C++4 부 /CX \[n\]: 정적 멤버 함수](https://blogs.msdn.microsoft.com/vcblog/2012/10/19/ccx-part-4-of-n-static-member-functions)

## <a name="windows-metadata-winmd-files"></a>Windows 메타데이터(.winmd) 파일

작성 된 유니버설 Windows 플랫폼 앱을 컴파일할 때 C++, 컴파일러에서 네이티브 기계어 코드로 실행 파일을 생성 및 공용 Windows 런타임의 설명을 포함 하는 별도 Windows 메타 데이터 (.winmd) 파일 생성 클래스, 구조체, 열거형, 인터페이스, 매개 변수가 있는 인터페이스 및 대리자를 포함 하는 형식입니다. 메타데이터의 형식은 .NET Framework 어셈블리에 사용된 형식과 유사합니다.  C++ 구성 요소에서 .winmd 파일은 메타데이터만 포함합니다. 실행 코드는 별도의 파일에 상주합니다. 이 경우 Windows에 포함 된 Windows 런타임 구성 요소에 대 한 합니다. WinMD 파일 이름은 소스 코드의 루트 네임스페이스의 접두사와 일치하거나 그 접두사여야 합니다. .NET Framework 언어의 경우 .winmd 파일에는 .NET Framework 어셈블리와 마찬가지로 코드와 메타데이터가 둘 다 포함됩니다.

.winmd 파일의 메타데이터는 코드의 게시된 표면을 나타냅니다. 게시 된 형식은 다른 유니버설 Windows 플랫폼에 표시 되지만 언어에 관계 없이 해당 앱 기록 됩니다. 따라서 메타 데이터 또는 게시 된 코드를 Windows 런타임 형식 시스템에 지정 된 형식을 포함할 수 있습니다. 일반 클래스, 배열, 템플릿 또는 STL 컨테이너와 같은 C++에 특정한 언어 구문은 메타데이터에 게시할 수 없습니다. Javascript 또는 C# 클라이언트 앱은 이러한 언어 구문으로 수행할 작업을 인식하지 못하기 때문입니다.

메타데이터에 형식이 표시되는지, 메서드가 표시되는지는 적용된 액세스 가능성 한정자에 따라 결정됩니다. 표시하려면 네임스페이스에 public으로 형식을 선언해야 합니다. public이 아닌 ref 클래스는 코드의 내부 도우미 형식으로 허용되고, 메타데이터에 표시되지는 않습니다. public ref 클래스의 경우에도 일부 멤버만 표시하면 됩니다. 다음 테이블 간의 관계를 나열 C++ 액세스는 public ref 클래스 및 Windows 런타임 메타 데이터 표시 유형 지정자:

|||
|-|-|
|**메타데이터에 게시됨**|**메타데이터에 게시되지 않음**|
|public|private|
|protected|internal|
|public protected|private protected|

**개체 브라우저** 를 사용하여 .winmd 파일의 내용을 볼 수 있습니다. Windows에 포함 된 Windows 런타임 구성 요소는 Windows.winmd 파일에. Default.winmd 파일에 사용 되는 기본 형식을 포함 C++, CX 및 platform.winmd Platform 네임 스페이스의 추가 형식을 포함 합니다. 기본적으로이 세.winmd 파일에 포함 된 모든 C++ 유니버설 Windows 플랫폼 앱 용 프로젝트입니다.

> [!TIP]
> [Platform::Collections Namespace](../cppcx/platform-collections-namespace.md) 의 형식은 public이 아니므로 .winmd 파일에 표시되지 않습니다. 이는 `Windows::Foundation::Collections`에 정의된 인터페이스의 private C++ 관련 구현입니다. JavaScript 또는 C#로 작성 된 Windows 런타임 앱 무엇 인지 인식 하지는 [Platform::Collections::Vector 클래스](../cppcx/platform-collections-vector-class.md) 를 사용할 수 있지만 `Windows::Foundation::Collections::IVector`합니다. `Platform::Collections` 형식은 collection.h에 정의됩니다.

## <a name="windows-runtime-type-system-in-ccx"></a>Windows 런타임 형식 시스템에서 C++/CX

다음 섹션에서는 Windows 런타임 형식 시스템 및 C + 지원 되는 방법의 주요 기능 + CX 합니다.

### <a name="namespaces"></a>네임스페이스

모든 Windows 런타임 형식 네임 스페이스; 내에서 선언 되어야 합니다. Windows API 자체는 네임 스페이스 별로 구성 됩니다. .winmd 파일은 루트 네임스페이스와 이름이 같아야 합니다. 예를 들어 이름이 A.B.C.MyClass인 클래스는 이름이 A.winmd, A.B.winmd 또는 A.B.C.winmd인 메타데이터 파일에 정의된 경우에만 인스턴스화될 수 있습니다. DLL의 이름은 .winmd 파일 이름과 일치하지 않아도 됩니다.

Windows API 자체는 네임스페이스로 구성된 효율적인 클래스 라이브러리로 다시 만들어졌습니다.  모든 Windows 런타임 구성 요소는 windows. * 네임 스페이스에서 선언 됩니다.

자세한 내용은 [네임 스페이스 및 형식 표시 유형](../cppcx/namespaces-and-type-visibility-c-cx.md)합니다.

### <a name="fundamental-types"></a>기본 형식

Windows 런타임에서 다음 기본 형식, UInt8, Int16, UInt16, Int32, UInt32, Int64, UInt64, Single, Double, Char16, 부울 및 문자열을 정의합니다. C++/CX는 uint16, uint32, uint64, int16, int32, int64, float32, float64 및 char16의 기본 네임 스페이스에 기본 숫자 형식을 지원합니다. Boolean과 String은 둘 다 Platform 네임스페이스에 정의됩니다.

C++/CX 동일한 uint8을 정의 `unsigned char`를 Windows 런타임에서 지원 되지 않습니다 하 고 공용 Api에서 사용할 수 없습니다.

기본 형식을 [Platform::IBox Interface](../cppcx/platform-ibox-interface.md) 인터페이스에서 래핑하여 nullable로 만들 수 있습니다. 자세한 내용은 [값 클래스 및 구조체](../cppcx/value-classes-and-structs-c-cx.md)에 정의된 인터페이스의 private C++ 관련 구현입니다.

기본 형식에 대한 자세한 내용은 [기본 형식](../cppcx/fundamental-types-c-cx.md)

### <a name="strings"></a>문자열

Windows 런타임 문자열은 16 비트 유니코드 문자의 시퀀스를 변경할 수 없는 합니다. Windows 런타임 문자열 처럼 투영 됩니다 `Platform::String^`합니다. 이 클래스는 문자열 작성, 조작 및 `wchar_t`간의 변환을 위한 메서드를 제공합니다.

자세한 내용은 [문자열](../cppcx/strings-c-cx.md)에 정의된 인터페이스의 private C++ 관련 구현입니다.

### <a name="arrays"></a>배열

Windows 런타임 형식의 1 차원 배열을 지원합니다. 배열의 배열은 지원되지 않습니다.  C++CX, Windows 런타임 배열으로 프로젝션 된/합니다 [platform:: array 클래스](../cppcx/platform-array-class.md)합니다.

자세한 내용은 참조 하세요. [Array 및 WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)

### <a name="ref-classes-and-structs"></a>Ref 클래스 및 구조체

Windows 런타임 클래스 프로젝션은 C++/CX ref 클래스나 ref 구조체 참조에 의해 복사 되므로 합니다. ref 클래스 및 ref 구조체의 메모리 관리는 참조 횟수에 따라 투명하게 처리됩니다. 개체에 대한 마지막 참조가 범위를 벗어나면 해당 개체가 삭제됩니다. ref 클래스 또는 ref 구조체는 다음을 지원합니다.

- 멤버 생성자, 메서드, 속성 및 이벤트를 포함할 수 있습니다. 이러한 멤버는 액세스 가능성이 public, private, protected 또는 internal일 수 있습니다.

- private 중첩 열거형, 구조체 또는 클래스 정의를 포함할 수 있습니다.

- 기본 클래스에서 직접 상속될 수 있으며 원하는 수의 인터페이스를 구현할 수 있습니다. 모든 ref 클래스는 암시적으로 [Platform::Object Class](../cppcx/platform-object-class.md) 로 변환될 수 있으며, [Object::ToString](../cppcx/platform-object-class.md#tostring)과 같은 가상 메서드를 재정의할 수 있습니다.

public 생성자가 있는 ref 클래스는 추가 파생을 방지하기 위해 sealed로 선언해야 합니다.

자세한 내용은 [Ref 클래스 및 구조체](../cppcx/ref-classes-and-structs-c-cx.md)

### <a name="value-classes-and-structs"></a>값 클래스 및 구조체

값 클래스 또는 값 구조체는 기본 데이터 구조를 나타내며 값 클래스, 값 구조체 또는 `Platform::String^`형식일 수 있는 필드만 포함합니다.  값 구조체 및 값 클래스는 값으로 복사됩니다.

값 구조체를 IBox 인터페이스에서 래핑하여 nullable로 만들 수 있습니다.

자세한 내용은 [값 클래스 및 구조체](../cppcx/value-classes-and-structs-c-cx.md)에 정의된 인터페이스의 private C++ 관련 구현입니다.

### <a name="partial-classes"></a>partial 클래스

partial 클래스 기능을 사용하면 여러 파일에 대해 하나의 클래스를 정의할 수 있습니다. 이 클래스는 XAML 편집기와 같은 코드 생성 도구에서 사용자가 편집하는 파일을 건드리지 않고 하나의 파일을 수정할 수 있게 하는 데 주로 사용됩니다.

자세한 내용은 [partial 클래스](../cppcx/partial-classes-c-cx.md)

### <a name="properties"></a>속성

속성을 모든 Windows 런타임 형식의 공용 데이터 멤버 이며 get/set 메서드 쌍으로 구현 됩니다. 클라이언트 코드는 공용 필드인 것처럼 속성에 액세스합니다. 사용자 지정 get 또는 set 코드가 필요 없는 속성을 *trivial 속성* 이라고 하며, 명시적인 get 또는 set 메서드 없이 선언할 수 있습니다.

자세한 내용은 [속성](../cppcx/properties-c-cx.md)에 정의된 인터페이스의 private C++ 관련 구현입니다.

### <a name="windows-runtime-collections-in-ccx"></a>Windows 런타임 컬렉션에 C++/CX

Windows 런타임에서 각 언어에서 자체적으로 구현 하는 컬렉션 형식에 대 한 인터페이스 집합을 정의 합니다. C++/CX 구현을 제공 합니다 [Platform::Collections::Vector 클래스](../cppcx/platform-collections-vector-class.md)를 [Platform::Collections::Map 클래스](../cppcx/platform-collections-map-class.md), 및와 호환 되는 기타 관련된 구체적 컬렉션 형식의 해당 표준 템플릿 라이브러리 (STL) 포함 합니다.

자세한 내용은 [컬렉션](../cppcx/collections-c-cx.md)합니다.

### <a name="template-ref-classes"></a>템플릿 ref 클래스

private 및 internal ref 클래스는 템플릿으로 만들고 특수화할 수 있습니다.

자세한 내용은 [템플릿 ref 클래스](../cppcx/template-ref-classes-c-cx.md)에 정의된 인터페이스의 private C++ 관련 구현입니다.

### <a name="interfaces"></a>인터페이스

Windows 런타임 인터페이스를 공용 속성, 메서드 및 ref 클래스 또는 ref 구조체는 인터페이스에서 상속 하는 경우 구현 해야 하는 이벤트 집합을 정의 합니다.

자세한 내용은 [인터페이스](../cppcx/interfaces-c-cx.md)를 참조하세요.

### <a name="enums"></a>열거형

Windows 런타임에서 enum 클래스에서 범위가 지정 된 열거형과 비슷합니다. C++입니다. 기본 형식은 int32입니다. 단, [Flags] 특성이 지정된 경우에는 기본 형식이 uint32입니다.

자세한 내용은 [열거형](../cppcx/enums-c-cx.md)에 정의된 인터페이스의 private C++ 관련 구현입니다.

### <a name="delegates"></a>대리자

Windows 런타임에서 대리자는 std:: function 개체에 비슷합니다. C++입니다. 호환되는 시그니처가 있는 클라이언트 제공 함수를 호출하는 데 사용되는 특별한 종류의 ref 클래스입니다.  대리자는 이벤트의 유형으로 Windows 런타임에서 가장 일반적으로 사용 됩니다.

자세한 내용은 [대리자](../cppcx/delegates-c-cx.md)를 참조하세요.

### <a name="exceptions"></a>예외

C++/CX에서는 사용자 지정 예외 형식, [std::exception](../standard-library/exception-class.md) 형식 및 [Platform::Exception](../cppcx/platform-exception-class.md) 형식을 catch할 수 있습니다.

자세한 내용은 [예외](../cppcx/exceptions-c-cx.md)에 정의된 인터페이스의 private C++ 관련 구현입니다.

### <a name="events"></a>이벤트

이벤트는 형식이 대리자 형식인 ref 클래스 또는 ref 구조체의 public 멤버입니다. 이벤트는 호출될 수만 있습니다. 즉, 소유 클래스에 의해서만 발생합니다. 그러나 클라이언트 코드는 소유 클래스가 이벤트를 발생시킨 경우에 호출되는 이벤트 처리기라는 고유 함수를 제공할 수 있습니다.

자세한 내용은 [이벤트](../cppcx/events-c-cx.md)에 정의된 인터페이스의 private C++ 관련 구현입니다.

### <a name="casting"></a>캐스팅

C++/CX에서는 표준 C++ 캐스트 연산자인 [static_cast](../cpp/static-cast-operator.md), [dynamic_cast](../cpp/dynamic-cast-operator.md)및 [reinterpret_cast](../cpp/reinterpret-cast-operator.md)와 C++/CX에서만 사용되는 **safe_cast** 연산자도 지원됩니다.

자세한 내용은 [캐스팅](../cppcx/casting-c-cx.md)에 정의된 인터페이스의 private C++ 관련 구현입니다.

### <a name="boxing"></a>boxing

boxed 변수는 참조 의미 체계가 필요한 경우 참조 형식에 래핑되는 값 형식입니다.

자세한 내용은 [boxing](../cppcx/boxing-c-cx.md)에 정의된 인터페이스의 private C++ 관련 구현입니다.

### <a name="attributes"></a>특성

특성에는 모든 Windows 런타임 형식 또는 형식 멤버에 적용할 수 있습니다 하 고 런타임에 검사할 수 있는 메타 데이터 값입니다. Windows 런타임에서 정의에서 공통 특성 집합을 `Windows::Foundation::Metadata` 네임 스페이스입니다. 이 릴리스에서 Windows 런타임에서 사용자 정의 특성 공용 인터페이스에서 지원 되지 않습니다.

## <a name="api-deprecation"></a>API 사용 중단

Windows 런타임 시스템 형식에서 사용 되는 동일한 특성을 사용 하 여 사용 되지 않는 것으로 공용 Api를 표시 하는 방법에 설명 합니다.

자세한 내용은 [형식 및 멤버를 사용 중단](../cppcx/deprecating-types-and-members-c-cx.md)합니다.

## <a name="see-also"></a>참고자료

[Visual C++ 언어 참조](../cppcx/visual-c-language-reference-c-cx.md)
