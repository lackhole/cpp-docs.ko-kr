---
title: .NET 및 UWP 용 구성 요소 확장
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- what's new [C++], keywords
- what's new [C++], language features
- C++, keywords
- keywords [C++]
- Managed Extensions for C++, replacement syntax
ms.assetid: 1e400ee6-3ac9-4910-a608-9d3d5993e423
ms.openlocfilehash: e9586244c9e2293ba6b484efb158fc3a2529c0ea
ms.sourcegitcommit: faa42c8a051e746d99dcebe70fd4bbaf3b023ace
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2019
ms.locfileid: "57814490"
---
# <a name="component-extensions-for-net-and-uwp"></a>.NET 및 UWP 용 구성 요소 확장

C + + 표준 언어에 대 한 비표준 확장을 제공 하기 위해 컴파일러 공급 업체를 허용 합니다. Microsoft는 네이티브 c + + 코드를 코드는.NET Framework 또는 Windows 플랫폼 (UWP (유니버설)에서 실행 되는 연결 하는 데는 확장을 제공 합니다. .NET extensions 라고 C + +.NET에서 실행 되는 CLI 및 생성 코드 언어 런타임 (CLR (공용) 라고 하는 실행 환경을 관리 합니다. UWP 확장 이라고 C + + /cli CX 있으며 네이티브 기계어 코드를 생성 합니다.

> [!NOTE]
> 새 응용 프로그램에 대 한 것이 좋습니다 사용 하 여 C + + /cli WinRT 보다는 C + + /cli CX. C + + /cli WinRT 프로젝션인 새, 표준 C + + 17 개의 언어 Windows 런타임 Api에 대 한 합니다. 우리는 계속 지원 C + + /cli CX 및 WRL, 되지만 항상 권장 구성이 새 응용 프로그램에서 사용할 C + + WinRT 합니다. 자세한 내용은 [C + + /cli WinRT](https://docs.microsoft.com/windows/uwp/cpp-and-winrt-apis/index)합니다.

### <a name="two-runtimes-one-set-of-extensions"></a>두 개의 런타임, 하나의 확장명 집합

C + + /cli CLI ISO/ANSI c + + 표준에서를 확장 하 고 정의 된 아래 Ecma C + + /cli 표준 CLI입니다. 자세한 내용은 [.NET 프로그래밍 C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)를 참조합니다.

C + + /cli CX 확장은 하위 집합 C + + /cli CLI입니다. 생성 되는 코드를 지정 했는지 여부에 따라 달라 집니다는 확장 구문을 대부분의 경우에서 동일한 경우에 합니다 `/ZW` UWP 대상으로 컴파일러 옵션 또는 `/clr` .NET 대상으로 하는 옵션입니다. 이러한 스위치는 Visual Studio를 사용하여 프로젝트를 만들 때 자동으로 설정됩니다.

## <a name="data-type-keywords"></a>데이터 형식 키워드

언어 확장을 포함 *키워드를 집계*, 공백으로 구분 된 두 개의 토큰 구성 되 합니다. 토큰은 별도로 사용될 때의 의미와 함께 사용될 때의 의미가 있을 수 있습니다. 예를 들어 "ref"라는 단어는 일반 식별자이고 "class"라는 단어는 네이티브 클래스를 선언하는 키워드입니다. 때 이러한 단어가 결합 되어 있지만 **ref 클래스**, 이라고 하는 엔터티를 선언 하는 결과 집계 키워드는 *런타임 클래스*합니다.

확장에도 *상황에 맞는* 키워드입니다. 키워드는 해당 키워드를 포함하는 문의 종류 및 해당 문에서의 배치에 따라 상황에 맞는 것으로 처리됩니다. 예를 들어 토큰 "property"는 식별자이거나 특별한 종류의 public 클래스 멤버를 선언할 수 있습니다.

다음 표에는 C++ 언어 확장의 키워드가 나열되어 있습니다.

|키워드|상황에 맞는지 여부|용도|참조|
|-------------|-----------------------|-------------|---------------|
|**ref 클래스**<br /><br /> **ref 구조체**|아니요|클래스를 선언합니다.|[클래스 및 구조체(C++)](../windows/classes-and-structs-cpp-component-extensions.md)|
|**값 클래스**<br /><br /> **값 구조체**|아니요|값 클래스를 선언합니다.|[클래스 및 구조체(C++)](../windows/classes-and-structs-cpp-component-extensions.md)|
|**인터페이스 클래스**<br /><br /> **인터페이스 구조체**|아니요|인터페이스를 선언합니다.|[인터페이스 클래스](../windows/interface-class-cpp-component-extensions.md)|
|**enum 클래스**<br /><br /> **enum 구조체**|아니요|열거형을 선언합니다.|[enum 클래스](../windows/enum-class-cpp-component-extensions.md)|
|**속성**|예|속성을 선언합니다.|[속성](../windows/property-cpp-component-extensions.md)|
|**delegate**|예|대리자를 선언합니다.|[위임(C++/CLI 및 C++/CX)](../windows/delegate-cpp-component-extensions.md)|
|**event**|예|이벤트를 선언합니다.|[event](../windows/event-cpp-component-extensions.md)|

## <a name="override-specifiers"></a>Override 지정자

다음 키워드를 사용하여 파생의 재정의 동작을 정규화할 수 있습니다. 하지만 합니다 **새** 키워드 c + +의 확장이 아닌, 추가 컨텍스트에서 사용할 수 있으므로 여기 나열 됩니다. 일부 지정자는 네이티브 프로그래밍에도 사용할 수 있습니다. 자세한 내용은 [방법: 네이티브 컴파일에 Override 지정자 선언 (C + + /cli CLI)](../dotnet/how-to-declare-override-specifiers-in-native-compilations-cpp-cli.md)합니다.

|키워드|상황에 맞는지 여부|용도|참조|
|-------------|-----------------------|-------------|---------------|
|**abstract**|예|함수 또는 클래스가 추상임을 나타냅니다.|[abstract](../windows/abstract-cpp-component-extensions.md)|
|**new**|아니요|함수가 기본 클래스 버전의 재정의가 아님을 나타냅니다.|[new (의 new 슬롯 vtable)](../windows/new-new-slot-in-vtable-cpp-component-extensions.md)|
|**override**|예|메서드가 기본 클래스 버전의 재정의이어야 함을 나타냅니다.|[override](../windows/override-cpp-component-extensions.md)|
|**sealed**|예|클래스를 기본 클래스로 사용할 수 없도록 합니다.|[sealed](../windows/sealed-cpp-component-extensions.md)|

## <a name="keywords-for-generics"></a>제네릭에 대한 키워드

다음은 제네릭 형식을 지원하도록 추가된 키워드입니다. 자세한 내용은 [제네릭](../windows/generics-cpp-component-extensions.md)을 참조하세요.

|키워드|상황에 맞는지 여부|용도|
|-------------|-----------------------|-------------|
|**generic**|아니요|제네릭 형식을 선언합니다.|
|**where**|예|제네릭 형식 매개 변수에 적용되는 제약 조건을 지정합니다.|

## <a name="miscellaneous-keywords"></a>기타 키워드

다음은 C++ 확장에 추가된 키워드입니다.

|키워드|상황에 맞는지 여부|용도|참조|
|-------------|-----------------------|-------------|---------------|
|**finally**|예|기본 예외 처리 동작을 나타냅니다.|[예외 처리](../windows/exception-handling-cpp-component-extensions.md)|
|**for each, in**|아니요|컬렉션의 요소를 열거합니다.|[for each, in](../dotnet/for-each-in.md)|
|**gcnew**|아니요|가비지 수집 힙에 형식을 할당합니다. 대신 사용 하 여 **새** 하 고 **삭제**합니다.|[ref new, gcnew](../windows/ref-new-gcnew-cpp-component-extensions.md)|
|**ref n e w**|예|Windows 런타임 형식을 할당합니다. 대신 사용 하 여 **새** 하 고 **삭제**합니다.|[ref new, gcnew](../windows/ref-new-gcnew-cpp-component-extensions.md)|
|**initonly**|예|선언 또는 정적 생성자에서만 멤버를 초기화할 수 있음을 나타냅니다.|[initonly(C++/CLI)](../dotnet/initonly-cpp-cli.md)|
|**name**|예|리터럴 변수를 만듭니다.|[name](../windows/literal-cpp-component-extensions.md)|
|**nullptr**|아니요|핸들 또는 포인터가 개체를 가리키지 않음을 나타냅니다.|[nullptr](../windows/nullptr-cpp-component-extensions.md)|

## <a name="template-constructs"></a>템플릿 구문

다음 언어 구문은 키워드 대신 템플릿으로 구현됩니다. 
  `/ZW` 컴파일러 옵션을 지정하는 경우 `lang` 네임스페이스에 정의됩니다. 
  `/clr` 컴파일러 옵션을 지정하는 경우 `cli` 네임스페이스에 정의됩니다.

|키워드|용도|참조|
|-------------|-------------|---------------|
|**array**|배열을 선언합니다.|[배열](../windows/arrays-cpp-component-extensions.md)|
|**interior_ptr**|(CLR에만 해당) 참조 형식의 데이터를 가리킵니다.|[interior_ptr(C++/CLI)](../windows/interior-ptr-cpp-cli.md)|
|**pin_ptr**|(CLR에만 해당) 가비지 수집 시스템을 일시적으로 표시하지 않도록 CLR 참조 형식을 가리킵니다.|[pin_ptr(C++/CLI)](../windows/pin-ptr-cpp-cli.md)|
|**safe_cast**|런타임 형식에 대한 최적의 캐스팅 메서드를 확인하고 실행합니다.|[safe_cast](../windows/safe-cast-cpp-component-extensions.md)|
|**typeid(C++ 구성 요소 확장)**|(CLR에만 해당) 지정된 형식 또는 개체를 설명하는 <xref:System.Type?displayProperty=fullName>개체를 검색합니다.|[typeid(C++ 구성 요소 확장)](../windows/typeid-cpp-component-extensions.md)|

## <a name="declarators"></a>선언자

다음 형식 선언자는 할당된 개체의 수명 및 삭제를 자동으로 관리하도록 런타임에 지시합니다.

|연산자|용도|참조|
|--------------|-------------|---------------|
|`^`|개체에 대 한 핸들 선언 즉, 더 이상 사용할 수 있는 경우 자동으로 삭제 되는 Windows 런타임 또는 CLR 개체에 대 한 포인터입니다.|[개체 연산자 (^)에 대 한 핸들](../windows/handle-to-object-operator-hat-cpp-component-extensions.md)|
|`%`|추적 참조를 선언합니다. 즉, 더 이상 사용할 수 있는 경우 자동으로 삭제 되는 Windows 런타임 또는 CLR 개체에 대 한 참조입니다.|[추적 참조 연산자](../windows/tracking-reference-operator-cpp-component-extensions.md)|

## <a name="additional-constructs-and-related-topics"></a>추가 구문 및 관련 항목

이 섹션에서는 추가 프로그래밍 구문 및 CLR과 관련된 항목을 나열합니다.

|항목|설명|
|-----------|-----------------|
|[__identifier(C++/CLI)](../windows/identifier-cpp-cli.md)|(Windows 런타임 및 CLR) 식별자로 키워드를 사용할 수 있습니다.|
|[가변 인수 목록(...)(C++/CLI)](../windows/variable-argument-lists-dot-dot-dot-cpp-cli.md)|(Windows 런타임 및 CLR) 가변 개수의 인수를 사용 하는 함수를 사용 하도록 설정 합니다.|
|[C++ 네이티브 형식에 해당하는 .NET Framework(C++/CLI)](../dotnet/dotnet-framework-equivalents-to-cpp-native-types-cpp-cli.md)|C++ 정수 계열 형식 대신 사용되는 CLR 유형을 나열합니다.|
|[appdomain](../cpp/appdomain.md) **__declspec** modifier|**__declspec** 정적 및 전역 변수가 appdomain 별로 존재를 규정 하는 한정자입니다.|
|[/Clr을 사용한 C 스타일 캐스트 (C + + /cli CLI)](../windows/c-style-casts-with-clr-cpp-cli.md)|C 스타일 캐스트가 해석되는 방법을 설명합니다.|
|[__clrcall](../cpp/clrcall.md) 호출 규칙|CLR 규격 호출 규칙을 나타냅니다.|
|`__cplusplus_cli`|[미리 정의된 매크로](../preprocessor/predefined-macros.md)|
|[사용자 지정 특성](../windows/custom-attributes-cpp.md)|사용자 고유의 CLR 특성을 정의하는 방법을 설명합니다.|
|[예외 처리](../windows/exception-handling-cpp-component-extensions.md)|예외 처리에 대한 개요를 제공합니다.|
|[명시적 재정의](../windows/explicit-overrides-cpp-component-extensions.md)|멤버 함수에서 임의 멤버를 재정의하는 방법을 보여 줍니다.|
|[Friend 어셈블리(C++)](../dotnet/friend-assemblies-cpp.md)|클라이언트 어셈블리에서 어셈블리 구성 요소의 모든 형식에 액세스할 수 있는 방법을 설명합니다.|
|[Boxing](../windows/boxing-cpp-component-extensions.md)|값 형식이 boxing되는 조건을 보여 줍니다.|
|[형식 특성에 대 한 컴파일러 지원](../windows/compiler-support-for-type-traits-cpp-component-extensions.md)|컴파일 시간에 형식의 특성을 검색하는 방법을 설명합니다.|
|[관리 되는, 관리 되지 않는](../preprocessor/managed-unmanaged.md) pragma|관리되는 함수와 관리되지 않는 함수가 동일한 모듈에 공존하는 방법을 보여 줍니다.|
|[process](../cpp/process.md) **__declspec** modifier|**__declspec** 정적 및 전역 변수가 process 별로 존재를 규정 하는 한정자입니다.|
|[리플렉션(C++/CLI)](../dotnet/reflection-cpp-cli.md)|런타임 형식 정보의 CLR 버전을 보여 줍니다.|
|[String](../windows/string-cpp-component-extensions.md)|
  <xref:System.String>로 문자열 리터럴의 컴파일러 변환을 설명합니다.|
|[형식 전달(C++/CLI)](../windows/type-forwarding-cpp-cli.md)|클라이언트 코드를 다시 컴파일할 필요가 없도록 전달 어셈블리의 형식을 다른 어셈블리로 이동할 수 있습니다.|
|[사용자 정의 특성](../windows/user-defined-attributes-cpp-component-extensions.md)|사용자 정의 특성을 보여 줍니다.|
|[#using 지시문](../preprocessor/hash-using-directive-cpp.md)|외부 어셈블리를 가져옵니다.|
|[XML 문서](../build/reference/xml-documentation-visual-cpp.md)|XML 기반 코드 문서를 사용 하 여 설명 [/doc (문서 주석 처리) (C/c + +)](../build/reference/doc-process-documentation-comments-c-cpp.md)|

## <a name="see-also"></a>참고 항목

[C++/CLI를 사용한 .NET 프로그래밍(Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)<br/>
[네이티브 및 .NET 상호 운용성](../dotnet/native-and-dotnet-interoperability.md)