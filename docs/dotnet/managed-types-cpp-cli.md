---
title: 관리되는 형식(C++/CLI)
ms.date: 11/04/2016
helpviewer_keywords:
- data types [C++], managed
- managed data types [C++]
- .NET Framework [C++], managed types
- data types [C++], .NET feature access
- main function, in managed applications
- managed code, main() function
- .NET Framework [C++], C++ equivalents
- __nogc type declarations
- __value keyword, issues when nesting
- equality, testing for
- versioning, diagnosing conflicts
- versioning
- exceptions, diagnosing odd behavior
- compatibility, between assemblies
ms.assetid: 679b8ed3-d966-4a0c-b627-2a3f3ec96b74
ms.openlocfilehash: b91918d526d83d4cf47436d02b7c67038576bafb
ms.sourcegitcommit: 42e65c171aaa17a15c20b155d22e3378e27b4642
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/22/2019
ms.locfileid: "58356181"
---
# <a name="managed-types-ccli"></a>관리되는 형식(C++/CLI)

Visual c + +에는 장점과 런타임의 제한 사항이 적용 되며 공용 언어 런타임의 기능에 대 한 지원을 제공 하는 관리 되는 형식 기능을 통해.NET 기능에 액세스할 수 있습니다.

## <a name="main_functions"></a> 관리 되는 형식 및 main 함수

사용 하 여 응용 프로그램을 작성 하는 경우 **/clr**의 인수는 **main ()** 함수는 관리 되는 형식일 수 없습니다.

적절 한 서명의 예는.

```cpp
// managed_types_and_main.cpp
// compile with: /clr
int main(int, char*[], char*[]) {}
```

## <a name="dotnet"></a> C + + 네이티브 형식에 해당 하는.NET framework

다음 표에서 미리 정의 된 형식의 별칭인 기본 제공 Visual c + + 형식에 대 한 키워드에는 **시스템** 네임 스페이스입니다.

|Visual c + + 형식|.NET Framework 형식|
|-----------------------|-------------------------|
|**void**|<xref:System.Void?displayProperty=nameWithType>|
|**bool**|<xref:System.Boolean?displayProperty=nameWithType>|
|**signed) char** |<xref:System.SByte?displayProperty=nameWithType>|
|**unsigned char**|<xref:System.Byte?displayProperty=nameWithType>|
|**wchar_t**|<xref:System.Char?displayProperty=nameWithType>|
|**짧은** 고 **즉 서명**|<xref:System.Int16?displayProperty=nameWithType>|
|**unsigned short**|<xref:System.UInt16?displayProperty=nameWithType>|
|**int**, **int 서명**합니다 **long**, 및 **기호가 있는 long**|<xref:System.Int32?displayProperty=nameWithType>|
|**부호 없는 int** 고 **부호 없는 long**|<xref:System.UInt32?displayProperty=nameWithType>|
|**__int64** 고 **__int64 서명**|<xref:System.Int64?displayProperty=nameWithType>|
|**unsigned __int64**|<xref:System.UInt64?displayProperty=nameWithType>|
|**float**|<xref:System.Single?displayProperty=nameWithType>|
|**이중** 고 **long double**|<xref:System.Double?displayProperty=nameWithType>|

에 부호가 있거나 부호가 없는 기본 컴파일러 옵션에 대 한 자세한 내용은 **char**를 참조 하세요 [/J (기본 문자 형식이 부호가 없습니다)](../build/reference/j-default-char-type-is-unsigned.md)합니다.

## <a name="version_issues"></a> 네이티브 형식에 중첩 된 값 형식의 버전 문제

클라이언트 어셈블리를 빌드하는 데 사용 하는 서명된 (강력한 이름) 어셈블리 구성 요소를 고려해 야 합니다. 구성 요소에는 기본 공용 구조체, 클래스 또는 배열 멤버에 대 한 형식으로 클라이언트에 사용 되는 값 형식이 있습니다. 이후 버전의 구성 요소 크기 또는 값 형식의 레이아웃 변경 되 면 클라이언트 컴파일해야 합니다.

사용 하 여 키 파일을 만들려면 [sn.exe](/dotnet/framework/tools/sn-exe-strong-name-tool) (`sn -k mykey.snk`).

### <a name="example"></a>예제

다음 예제는 구성 요소입니다.

```cpp
// nested_value_types.cpp
// compile with: /clr /LD
using namespace System::Reflection;
[assembly:AssemblyVersion("1.0.0.*"),
assembly:AssemblyKeyFile("mykey.snk")];

public value struct S {
   int i;
   void Test() {
      System::Console::WriteLine("S.i = {0}", i);
   }
};
```

### <a name="example"></a>예제

이 샘플은 클라이언트:

```cpp
// nested_value_types_2.cpp
// compile with: /clr
#using <nested_value_types.dll>

struct S2 {
   S MyS1, MyS2;
};

int main() {
   S2 MyS2a, MyS2b;
   MyS2a.MyS1.i = 5;
   MyS2a.MyS2.i = 6;
   MyS2b.MyS1.i = 10;
   MyS2b.MyS2.i = 11;

   MyS2a.MyS1.Test();
   MyS2a.MyS2.Test();
   MyS2b.MyS1.Test();
   MyS2b.MyS2.Test();
}
```

### <a name="output"></a>출력

```Output
S.i = 5
S.i = 6
S.i = 10
S.i = 11
```

### <a name="comments"></a>설명

그러나 다른 멤버를 추가 하는 경우 `struct S` nested_value_types.cpp를에서 (예를 들어 `double d;`) 및 클라이언트를 다시 컴파일하지 않고도 구성 요소 다시 컴파일 결과 처리 되지 않은 예외 (형식의 <xref:System.IO.FileLoadException?displayProperty=fullName>).

## <a name="test_equality"></a> 방법: 같음 여부 테스트

다음 샘플에서는 Managed Extensions for c + +는 같음 테스트를 기반으로 핸들을 가리키는 합니다.

### <a name="example"></a>예제

```cpp
// mcppv2_equality_test.cpp
// compile with: /clr /LD
using namespace System;

bool Test1() {
   String ^ str1 = "test";
   String ^ str2 = "test";
   return (str1 == str2);
}
```

이 프로그램에 대 한 IL op_Equality에 대 한 호출을 사용 하 여가 구현 하는 반환 값을 보여 줍니다.

```MSIL
IL_0012:  call       bool [mscorlib]System.String::op_Equality(string,
                                                               string)
```

## <a name="diagnose_fix"></a> 방법: 어셈블리 호환성 문제 진단 및 해결

이 항목에서는 컴파일 타임에 참조 된 어셈블리의 버전에는 런타임 시 참조 된 어셈블리의 버전과 일치 하지 하는 경우 발생할 수 있는 결과 설명 하 고 문제를 방지 하는 방법입니다.

어셈블리를 컴파일할 때 사용 하 여 다른 어셈블리를 참조할 수 있습니다는 `#using` 구문입니다. 컴파일하는 동안 이러한 어셈블리는 컴파일러에 의해 액세스 됩니다. 이러한 어셈블리의 정보를 사용 하 여 최적화 결정을 내릴 수 있습니다.

그러나 참조 된 어셈블리가 변경 되 고 다시 컴파일하면를 참조 하는 어셈블리에 종속 된 컴파일하지 않으면 어셈블리 않을 여전히 호환 되어야 합니다. 에 잘못 된 최적화 결정 먼저 올바르지 않을 수 있습니다 새 어셈블리 버전을 기준으로 합니다. 이러한 비 호환성으로 인해 다양 한 런타임 오류가 발생할 수 있습니다. 이러한 경우에 생성 되는 특정 예외가 있습니다. 런타임 시 오류가 보고 되는 방법은 문제를 발생 시킨 코드 변경의 특성에 따라 달라 집니다.

이러한 오류는 제품의 릴리스 버전에 대 한 전체 응용 프로그램은 다시 작성으로 최종 프로덕션 코드에 문제가 되지 않습니다. 공개적으로 출시 되는 어셈블리는 이러한 문제가 방지 되도록 하는 공식 버전 번호로 표시 되어야 합니다. 자세한 내용은 [어셈블리 버전 관리](/dotnet/framework/app-domains/assembly-versioning)를 참조하세요.

### <a name="diagnosing-and-fixing-an-incompatibility-error"></a>진단 하 고 비 호환성 오류를 수정 합니다.

1. 기타 식별 된 원인에 있고 런타임 예외 또는 다른 어셈블리를 참조 하는 코드에서 발생 하는 기타 오류 조건 발생 하는 경우 오래 된 어셈블리를 사용 하 여 처리 해야 할 수도 있습니다.

1. 첫째, 격리 및 예외 또는 기타 오류 조건을 재현 합니다. 오래 된 예외로 인해 발생 하는 문제를 재현할 수 있어야 합니다.

1. 응용 프로그램에서 참조 하는 어셈블리의 타임 스탬프를 확인 합니다.

1. 참조 된 어셈블리의 타임 스탬프는 응용 프로그램의 마지막 컴파일 타임 스탬프 보다 나중에 응용 프로그램 만료 되었습니다. 이 경우 최신 어셈블리를 사용 하 여 응용 프로그램 다시 컴파일하고 필요한 코드 변경 내용을 확인 합니다.

1. 응용 프로그램을 다시 실행 하 고 문제를 재현 하 고 예외를 발생 하지 않으면 확인 단계를 수행 하십시오.

### <a name="example"></a>예제

다음 프로그램 메서드의 액세스 가능성을 줄이고 다시 컴파일하지 않고 다른 어셈블리에서이 메서드에 액세스 하려고 하 여 문제를 보여 줍니다. 컴파일을 시도 `changeaccess.cpp` 첫 번째입니다. 참조 된 어셈블리를 변경 하는 경우 그런 다음 컴파일합니다 `referencing.cpp`합니다. 컴파일이 성공합니다. 이제 호출 된 메서드의 액세스 가능성을 줄입니다. Recompile `changeaccess.cpp` 플래그로 `/DCHANGE_ACCESS`합니다. 이렇게 하면 메서드가 개인 대신 protected 수 더 이상 호출할 수 합법적으로 합니다. 다시 컴파일하지 않고 `referencing.exe`, 응용 프로그램을 다시 실행 합니다. 예외가 <xref:System.MethodAccessException> 발생 합니다.

```cpp
// changeaccess.cpp
// compile with: /clr:safe /LD
// After the initial compilation, add /DCHANGE_ACCESS and rerun
// referencing.exe to introduce an error at runtime. To correct
// the problem, recompile referencing.exe

public ref class Test {
#if defined(CHANGE_ACCESS)
protected:
#else
public:
#endif

  int access_me() {
    return 0;
  }

};
```

```cpp
// referencing.cpp
// compile with: /clr:safe
#using <changeaccess.dll>

// Force the function to be inline, to override the compiler's own
// algorithm.
__forceinline
int CallMethod(Test^ t) {
  // The call is allowed only if access_me is declared public
  return t->access_me();
}

int main() {
  Test^ t = gcnew Test();
  try
  {
    CallMethod(t);
    System::Console::WriteLine("No exception.");
  }
  catch (System::Exception ^ e)
  {
    System::Console::WriteLine("Exception!");
  }
  return 0;
}
```

## <a name="see-also"></a>참고자료

[C++/CLI를 사용한 .NET 프로그래밍(Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)<br/>
[다른 .NET 언어와의 상호 운용성(C++/CLI)](../dotnet/interoperability-with-other-dotnet-languages-cpp-cli.md)<br/>
[관리되는 형식(C++/CLI)](../dotnet/managed-types-cpp-cli.md)<br/>
[#using 지시문](../preprocessor/hash-using-directive-cpp.md)
