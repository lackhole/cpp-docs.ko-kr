---
title: 리플렉션(C++/CLI)
ms.date: 11/04/2016
helpviewer_keywords:
- typeid keyword [C++]
- reflection [C++}, about reflection
- metadata, reflection
- GetType method
- .NET Framework [C++], reflection
- data types [C++], reflection
- reflection [C++}
- plug-ins [C++]
- reflection [C++}, plug-ins
- assemblies [C++], enumerating data types in
- public types [C++]
- reflection [C++], external assemblies
- assemblies [C++]
- data types [C++], enumerating
- public members [C++]
ms.assetid: 46b6ff4a-e441-4022-8892-78e69422f230
ms.openlocfilehash: a17910e0288b81723aa837ba9204bb40713d5d49
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62384688"
---
# <a name="reflection-ccli"></a>리플렉션(C++/CLI)

리플렉션 알려진된 데이터 형식을 런타임에 검사할 수 있습니다. 리플렉션은 데이터 형식의 열거형을 지정된 된 어셈블리에 있으며 지정 된 클래스 또는 값 형식의 멤버를 검색할 수 있습니다. 여부에 관계 없이 형식 된 알려진 컴파일 타임에 참조도 마찬가지입니다. 이렇게 하면 리플렉션 개발 및 코드 관리 도구에 대 한 유용한 기능이 있습니다.

어셈블리 이름을 제공 된 강력한 이름 (참조 [강력한 어셈블리 만들기 및 사용](/dotnet/framework/app-domains/create-and-use-strong-named-assemblies)), 어셈블리 버전, 문화권 및 서명 정보를 포함 하는 합니다. 데이터 형식이 정의 되어 있는 네임 스페이스의 이름의 검색할 수 있는 기본 클래스의 이름과 함께 또한 note 합니다.

리플렉션 기능에 액세스 하는 가장 일반적인 방법은 방법은 <xref:System.Object.GetType%2A> 메서드. 이 메서드는 제공한 <xref:System.Object?displayProperty=nameWithType>, 가비지 수집 된 모든 클래스는 파생에서.

> [!NOTE]
> 시각적 개체를 사용 하 여 빌드한.exe에서 리플렉션 C++ 컴파일러는.exe는 기반으로 하는 경우에 허용 됩니다는 **/clr: pure** 또는 **/clr: safe** 컴파일러 옵션. **/clr: pure** 및 **/clr: safe** 컴파일러 옵션은 Visual Studio 2015에서 사용 되지 않는 및 Visual Studio 2017에서 사용할 수 없습니다. 참조 [/clr (공용 언어 런타임 컴파일)](../build/reference/clr-common-language-runtime-compilation.md) 자세한 내용은 합니다.

자세한 내용은 <xref:System.Reflection>을 참조하세요.

## <a name="example-gettype"></a>예제: GetType

`GetType` 에 대 한 포인터를 반환 하는 메서드를 <xref:System.Type> 는 개체를 기반으로 하는 경우의 기본 형식을 설명 하는 클래스 개체입니다. (합니다 **형식** 개체 인스턴스 관련 정보를 포함 하지 않습니다.) 이러한 항목은 다음과 같이 표시 될 수 있는 형식의 전체 이름:

형식 이름을 포함 하는 형식이 정의 된 네임 스페이스를 포함 하 여 전체 범위 및 점 범위 확인 연산자를 사용 하 여.NET 구문에 표시 되는 참고 합니다.

```cpp
// vcpp_reflection.cpp
// compile with: /clr
using namespace System;
int main() {
   String ^ s = "sample string";
   Console::WriteLine("full type name of '{0}' is '{1}'", s, s->GetType());
}
```

```Output
full type name of 'sample string' is 'System.String'
```

## <a name="example-boxed-value-types"></a>예제: boxed 값 형식

값 형식을 사용할 수는 `GetType` 에서도 작동 하지만 먼저 boxed 수 있어야 합니다.

```cpp
// vcpp_reflection_2.cpp
// compile with: /clr
using namespace System;
int main() {
   Int32 i = 100;
   Object ^ o = i;
   Console::WriteLine("type of i = '{0}'", o->GetType());
}
```

```Output
type of i = 'System.Int32'
```

## <a name="example-typeid"></a>예제: typeid

와 마찬가지로 `GetType` 메서드를 [typeid](../extensions/typeid-cpp-component-extensions.md) 연산자에 대 한 포인터를 반환 합니다.는 **형식** 개체 이므로이 코드는 형식 이름을 나타냅니다 **System.Int32**합니다. 형식 이름 표시 리플렉션의 가장 기본적인 기능 이지만 잠재적으로 유용한 기술 검사 또는 열거형된 형식에 대 한 유효한 값을 검색 하는 것입니다. 정적을 사용 하 여 이렇게 **Enum::GetNames** 함수를 텍스트 형식에는 열거형 값이 포함 된 각 문자열의 배열을 반환 합니다.  다음 샘플에 대 한 열거형 값을 설명 하는 문자열의 배열을 검색 합니다 **옵션** (CLR) 열거형 루프에 표시 됩니다.

네 번째 옵션을 추가할 경우 합니다 **옵션** 열거형이이 코드 열거형 별도 어셈블리에 정의 된 경우에 다시 컴파일하지 않고도 새 옵션을 보고 합니다.

```cpp
// vcpp_reflection_3.cpp
// compile with: /clr
using namespace System;

enum class Options {   // not a native enum
   Option1, Option2, Option3
};

int main() {
   array<String^>^ names = Enum::GetNames(Options::typeid);

   Console::WriteLine("there are {0} options in enum '{1}'",
               names->Length, Options::typeid);

   for (int i = 0 ; i < names->Length ; i++)
      Console::WriteLine("{0}: {1}", i, names[i]);

   Options o = Options::Option2;
   Console::WriteLine("value of 'o' is {0}", o);
}
```

```Output
there are 3 options in enum 'Options'
0: Option1
1: Option2
2: Option3
value of 'o' is Option2
```

## <a name="example-gettype-members-and-properties"></a>예제: GetType 멤버 및 속성

`GetType` 개체 멤버 및 형식 검사를 사용할 수 있는 속성의 숫자를 지원 합니다. 이 코드는 검색 하 고이 정보 중 일부를 표시 합니다.

```cpp
// vcpp_reflection_4.cpp
// compile with: /clr
using namespace System;
int main() {
   Console::WriteLine("type information for 'String':");
   Type ^ t = String::typeid;

   String ^ assemblyName = t->Assembly->FullName;
   Console::WriteLine("assembly name: {0}", assemblyName);

   String ^ nameSpace = t->Namespace;
   Console::WriteLine("namespace: {0}", nameSpace);

   String ^ baseType = t->BaseType->FullName;
   Console::WriteLine("base type: {0}", baseType);

   bool isArray = t->IsArray;
   Console::WriteLine("is array: {0}", isArray);

   bool isClass = t->IsClass;
   Console::WriteLine("is class: {0}", isClass);
}
```

```Output
type information for 'String':
assembly name: mscorlib, Version=1.0.5000.0, Culture=neutral,
PublicKeyToken=b77a5c561934e089
namespace: System
base type: System.Object
is array: False
is class: True
```

## <a name="example-enumeration-of-types"></a>예: 열거형 형식

리플렉션은 어셈블리 내에 형식 및 클래스 내에서 멤버를 열거할을 수 있습니다. 이 기능을 보여 주기 위해 간단한 클래스를 정의 합니다.

```cpp
// vcpp_reflection_5.cpp
// compile with: /clr /LD
using namespace System;
public ref class TestClass {
   int m_i;
public:
   TestClass() {}
   void SimpleTestMember1() {}
   String ^ SimpleMember2(String ^ s) { return s; }
   int TestMember(int i) { return i; }
   property int Member {
      int get() { return m_i; }
      void set(int i) { m_i = i; }
   }
};
```

## <a name="example-inspection-of-assemblies"></a>어셈블리의 예: 검사

위의 코드를 vcpp_reflection_6.dll 라는 DLL로 컴파일된 경우이 어셈블리의 내용을 확인 하려면 다음 리플렉션을 사용할 수 있습니다. 여기에 정적 리플렉션 API 함수 xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType를 사용 하 여 어셈블리를 로드 합니다. 주소를 반환 하는이 함수는 **어셈블리** 모듈 및 내의 형식에 대 한 다음 쿼리할 수 있는 개체입니다.

리플렉션 시스템 어셈블리의 배열을 성공적으로 로드 되 면 **형식** 사용 하 여 개체 검색은 <xref:System.Reflection.Assembly.GetTypes%2A?displayProperty=nameWithType> 함수입니다. 각 배열 요소 하나만 클래스 정의이 예제의 경우 되지만 다른 형식에 대 한 정보를 포함 합니다. 루프를 사용 하 여 각 **형식** 사용 하 여 형식 멤버에 대 한 쿼리는이 배열에는 **Type::GetMembers** 함수입니다. 이 함수는 배열을 반환 **MethodInfo** 개체, 멤버 함수, 데이터 멤버 또는 형식의 속성에에서 대 한 정보가 포함 된 각 개체입니다.

에 정의 된 메서드 목록을 함수를 명시적으로 포함 하는 참고 **TestClass** 함수에서 암시적으로 상속 합니다 **system:: object** 클래스입니다. .NET 대신 시각적 개체에서 설명 하 고의 일환으로 C++ get/set 함수에서 액세스 하는 기본 데이터 멤버와 구문을 속성이 나타납니다. Get/set 함수로 정규 메서드로이 목록에 나타납니다. 시각적 개체가 아닌 공용 언어 런타임을 통해 리플렉션은 지원 됩니다 C++ 컴파일러.

정의 된 어셈블리를 검사 하려면이 코드를 사용 하지만.NET 어셈블리를 검사 하도이 코드를 사용할 수 있습니다. 예를 들어 TestAssembly에는 mscorlib에 변경한 경우 모든 형식과 mscorlib.dll에 정의 된 메서드 목록이 표시 됩니다.

```cpp
// vcpp_reflection_6.cpp
// compile with: /clr
using namespace System;
using namespace System::IO;
using namespace System::Reflection;
int main() {
   Assembly ^ a = nullptr;
   try {
      // load assembly -- do not use file extension
      // will look for .dll extension first
      // then .exe with the filename
      a = Assembly::Load("vcpp_reflection_5");
   }
   catch (FileNotFoundException ^ e) {
      Console::WriteLine(e->Message);
      return -1;
   }

   Console::WriteLine("assembly info:");
   Console::WriteLine(a->FullName);
   array<Type^>^ typeArray = a->GetTypes();

   Console::WriteLine("type info ({0} types):", typeArray->Length);

   int totalTypes = 0;
   int totalMembers = 0;
   for (int i = 0 ; i < typeArray->Length ; i++) {
      // retrieve array of member descriptions
      array<MemberInfo^>^ member = typeArray[i]->GetMembers();

      Console::WriteLine("  members of {0} ({1} members):",
      typeArray[i]->FullName, member->Length);
      for (int j = 0 ; j < member->Length ; j++) {
         Console::Write("       ({0})",
         member[j]->MemberType.ToString() );
         Console::Write("{0}  ", member[j]);
         Console::WriteLine("");
         totalMembers++;
      }
      totalTypes++;
   }
   Console::WriteLine("{0} total types, {1} total members",
   totalTypes, totalMembers);
}
```

## <a name="implement"></a> 방법: 리플렉션을 사용 하 여 플러그 인 구성 요소 아키텍처 구현

다음 코드 예제에서는 간단한 "플러그 인" 아키텍처를 구현 하는 리플렉션 사용을 보여 줍니다. 첫 번째 목록은 응용 프로그램을 이며 두 번째 플러그 인입니다. 응용 프로그램에 명령줄 인수로 제공 하는 플러그 인 DLL의 모든 양식 기반 클래스를 사용 하 여 자신을 채우는 여러 문서 형태입니다.

응용 프로그램에서 사용 하 여 제공 된 어셈블리를 로드 하려고 합니다 <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName> 메서드. 성공 하는 경우를 사용 하 여 어셈블리 내의 형식을 열거는 <xref:System.Reflection.Assembly.GetTypes%2A?displayProperty=fullName> 메서드. 각 유형에 사용 하 여 호환성 확인 하는 <xref:System.Type.IsAssignableFrom%2A?displayProperty=fullName> 메서드. 이 예제에서는 제공 된 어셈블리의 클래스에서 파생 되어야 합니다는 <xref:System.Windows.Forms.Form> 클래스는 플러그 인 역할을 합니다.

호환 되는 클래스에 다음 사용 하 여 인스턴스화됩니다 합니다 <xref:System.Activator.CreateInstance%2A?displayProperty=fullName> 메서드를를 <xref:System.Type> 인수로 서 새 인스턴스에 대 한 포인터를 반환 합니다. 각 새 인스턴스는 다음 폼에 연결 하 고 표시 합니다.

<xref:System.Reflection.Assembly.Load%2A> 메서드 파일 확장명을 포함 하는 어셈블리 이름을 허용 하지 않습니다. 다음 코드 예제에서는 두 경우 모두에서 작동 하므로 응용 프로그램의 main 함수 모든 제공 된 확장을 삭제 합니다.

### <a name="example"></a>예제

다음 코드는 플러그 인을 허용 하는 응용 프로그램을 정의 합니다. 어셈블리 이름이 첫 번째 인수로 제공 되어야 합니다. 이 어셈블리에는 하나 이상의 공용 있어야 <xref:System.Windows.Forms.Form> 파생 형식입니다.

```cpp
// plugin_application.cpp
// compile with: /clr /c
#using <system.dll>
#using <system.drawing.dll>
#using <system.windows.forms.dll>

using namespace System;
using namespace System::Windows::Forms;
using namespace System::Reflection;

ref class PluggableForm : public Form  {
public:
   PluggableForm() {}
   PluggableForm(Assembly^ plugAssembly) {
      Text = "plug-in example";
      Size = Drawing::Size(400, 400);
      IsMdiContainer = true;

      array<Type^>^ types = plugAssembly->GetTypes( );
      Type^ formType = Form::typeid;

      for (int i = 0 ; i < types->Length ; i++) {
         if (formType->IsAssignableFrom(types[i])) {
            // Create an instance given the type description.
            Form^ f = dynamic_cast<Form^> (Activator::CreateInstance(types[i]));
            if (f) {
               f->Text = types[i]->ToString();
               f->MdiParent = this;
               f->Show();
            }
         }
      }
   }
};

int main() {
   Assembly^ a = Assembly::LoadFrom("plugin_application.exe");
   Application::Run(gcnew PluggableForm(a));
}
```

### <a name="example"></a>예제

다음 코드는 세 가지 클래스에서 파생 된 정의 <xref:System.Windows.Forms.Form>합니다. 결과 어셈블리의 이름을 이전 목록에서 실행 파일에 전달 되 면 세 클래스는 각 검색 되며 불구 하는 호스팅 응용 프로그램 컴파일 타임에 알려진 모든 올바르지 않은 인스턴스화됩니다.

```cpp
// plugin_assembly.cpp
// compile with: /clr /LD
#using <system.dll>
#using <system.drawing.dll>
#using <system.windows.forms.dll>

using namespace System;
using namespace System::Windows::Forms;
using namespace System::Reflection;
using namespace System::Drawing;

public ref class BlueForm : public Form {
public:
   BlueForm() {
      BackColor = Color::Blue;
   }
};

public ref class CircleForm : public Form {
protected:
   virtual void OnPaint(PaintEventArgs^ args) override {
      args->Graphics->FillEllipse(Brushes::Green, ClientRectangle);
   }
};

public ref class StarburstForm : public Form {
public:
   StarburstForm(){
      BackColor = Color::Black;
   }
protected:
   virtual void OnPaint(PaintEventArgs^ args) override {
      Pen^ p = gcnew Pen(Color::Red, 2);
      Random^ r = gcnew Random( );
      Int32 w = ClientSize.Width;
      Int32 h = ClientSize.Height;
      for (int i=0; i<100; i++) {
         float x1 = w / 2;
         float y1 = h / 2;
         float x2 = r->Next(w);
         float y2 = r->Next(h);
         args->Graphics->DrawLine(p, x1, y1, x2, y2);
      }
   }
};
```

## <a name="enumerate"></a> 방법: 리플렉션을 사용 하 여 어셈블리에 데이터 형식 열거

다음 코드에서는 공용 형식 및 멤버를 사용 하 여 열거 <xref:System.Reflection>합니다.

아래 코드 지정 된 이름을 어셈블리의 로컬 디렉터리 또는 GAC에 어셈블리를 열고 설명을 검색 하려고 시도 합니다. 성공 하면 public 멤버를 사용 하 여 각 형식이 표시 됩니다.

<xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName> 에서는 파일 확장명이 없습니다 사용 됩니다. 따라서 "mscorlib.dll" 명령줄 인수로 사용 하 여 실패 합니다 "mscorlib"를 사용 하면.NET Framework 형식을 표시 하는 동안. 어셈블리 이름이 없습니다. 제공 하는 경우 코드를 감지 하 고 현재 어셈블리 내의 형식 (이 코드에서 결과 EXE)을 보고 됩니다.

### <a name="example"></a>예제

```cpp
// self_reflection.cpp
// compile with: /clr
using namespace System;
using namespace System::Reflection;
using namespace System::Collections;

public ref class ExampleType {
public:
   ExampleType() {}
   void Func() {}
};

int main() {
   String^ delimStr = " ";
   array<Char>^ delimiter = delimStr->ToCharArray( );
   array<String^>^ args = Environment::CommandLine->Split( delimiter );

// replace "self_reflection.exe" with an assembly from either the local
// directory or the GAC
   Assembly^ a = Assembly::LoadFrom("self_reflection.exe");
   Console::WriteLine(a);

   int count = 0;
   array<Type^>^ types = a->GetTypes();
   IEnumerator^ typeIter = types->GetEnumerator();

   while ( typeIter->MoveNext() ) {
      Type^ t = dynamic_cast<Type^>(typeIter->Current);
      Console::WriteLine("   {0}", t->ToString());

      array<MemberInfo^>^ members = t->GetMembers();
      IEnumerator^ memberIter = members->GetEnumerator();
      while ( memberIter->MoveNext() ) {
         MemberInfo^ mi = dynamic_cast<MemberInfo^>(memberIter->Current);
         Console::Write("      {0}", mi->ToString( ) );
         if (mi->MemberType == MemberTypes::Constructor)
            Console::Write("   (constructor)");

         Console::WriteLine();
      }
      count++;
   }
   Console::WriteLine("{0} types found", count);
}
```

## <a name="see-also"></a>참고자료

- [C++/CLI를 사용한 .NET 프로그래밍(Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)
