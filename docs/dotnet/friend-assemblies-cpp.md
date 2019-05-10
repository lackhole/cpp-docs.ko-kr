---
title: Friend 어셈블리(C++)
ms.date: 11/04/2016
helpviewer_keywords:
- friend assemblies, Visual C++
ms.assetid: 8d55fee0-b7c2-4fbe-a23b-dfe424dc71cd
ms.openlocfilehash: 05b9d8bcf5d7364e1dcd31940bc0db64a5e605f1
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2019
ms.locfileid: "65447309"
---
# <a name="friend-assemblies-c"></a>Friend 어셈블리(C++)

적용 가능한 런타임 합니다 *friend 어셈블리* 언어 기능을 사용 하면 네임 스페이스 범위 또는 하나 이상의 클라이언트 어셈블리 또는.netmodules에 액세스할 수는 어셈블리 구성 요소에서 전역 범위에 있는 형식입니다.

## <a name="all-runtimes"></a>모든 런타임

**설명**

(이 언어 기능 모든 런타임에서 지원 되지 않습니다.)

## <a name="windows-runtime"></a>Windows 런타임

**설명**

(이 언어 기능 Windows 런타임에서 지원 되지 않습니다.)

### <a name="requirements"></a>요구 사항

컴파일러 옵션: **/ZW**

## <a name="common-language-runtime"></a>공용 언어 런타임

**설명**

#### <a name="to-make-types-at-namespace-scope-or-global-scope-in-an-assembly-component-accessible-to-a-client-assembly-or-netmodule"></a>네임 스페이스 범위 또는 전역 범위에서 형식 어셈블리 구성 요소에 액세스할 수 있도록 클라이언트 어셈블리 또는.netmodule

1. 구성 요소의 어셈블리 특성을 지정 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>, 클라이언트 어셈블리 또는.netmodule 형식 네임 스페이스 범위 또는 구성 요소에서 글로벌 범위를 액세스 하는 이름을 전달 합니다.  추가 특성을 지정 하 여 여러 클라이언트 어셈블리 또는.netmodules를 지정할 수 있습니다.

1. 클라이언트 어셈블리 또는.netmodule를 사용 하 여 구성 요소 어셈블리를 참조 하면 `#using`를 전달 합니다 `as_friend` 특성입니다.  지정 하는 경우는 `as_friend` 지정 하지 않는 어셈블리에 대 한 특성 `InternalsVisibleToAttribute`, 네임 스페이스 범위 또는 구성 요소에서 전역 범위에서 형식에 액세스 하려고 하면 런타임 예외가 throw 됩니다.

어셈블리를 포함 하는 경우 빌드 오류가 발생 합니다는 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 특성은 강력한 이름을 사용 하는 클라이언트 어셈블리를 `as_friend` 특성이 없습니다.

클라이언트 어셈블리 또는.netmodule 형식 네임 스페이스 범위 및 전역 범위를 알 수 있습니다, 있지만 멤버 액세스 가능성 계속 적용 됩니다.  예를 들어, 전용 멤버를 액세스할 수 없습니다.

어셈블리의 모든 형식에 대 한 액세스를 명시적으로 부여 되어야 합니다.  예를 들어, 어셈블리 C에 없는 모든 형식에 대 한 액세스는 어셈블리의 어셈블리 C 참조 어셈블리 B 및 어셈블리 B 1. 어셈블리에 대 한 모든 형식에 액세스 하는 경우

서명 하는 방법에 대 한 자세한-즉, 강력한 이름을 제공 하는 방법-Microsoft를 사용 하 여 기본 제공 되는 어셈블리 C++ 컴파일러 참조 [강력한 이름 어셈블리 (어셈블리 서명) (C++/CLI)](../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md)합니다.

Friend 어셈블리 기능을 사용 하는 대신, 사용할 수 있습니다 <xref:System.Security.Permissions.StrongNameIdentityPermission> 를 개별 형식에 대 한 액세스를 제한 합니다.

### <a name="requirements"></a>요구 사항

컴파일러 옵션: **/clr**

### <a name="examples"></a>예제

다음 코드 예제에서는 구성 요소에서 형식에 대 한 액세스 권한이 있는 클라이언트 어셈블리를 지정 하는 구성 요소를 정의 합니다.

```cpp
// friend_assemblies.cpp
// compile by using: /clr /LD
using namespace System::Runtime::CompilerServices;
using namespace System;
// an assembly attribute, not bound to a type
[assembly:InternalsVisibleTo("friend_assemblies_2")];

ref class Class1 {
public:
   void Test_Public() {
      Console::WriteLine("Class1::Test_Public");
   }
};
```

다음 코드 예제에서는 구성 요소에는 전용 형식에 액세스합니다.

```cpp
// friend_assemblies_2.cpp
// compile by using: /clr
#using "friend_assemblies.dll" as_friend

int main() {
   Class1 ^ a = gcnew Class1;
   a->Test_Public();
}
```

```Output
Class1::Test_Public
```

다음 코드 예제에서는 구성 요소를 정의 하지만 구성 요소에서 형식에 액세스할 수 있는 클라이언트 어셈블리를 지정 하지 않습니다.

구성 요소를 사용 하 여 연결 되어 있는지 확인할 수 있습니다 **/opt: noref**합니다. 이렇게 하면 개인 형식이 필요 하지 않은 경우 구성 요소의 메타 데이터에서 생성 됩니다는 `InternalsVisibleTo` 특성이 있습니다. 자세한 내용은 [/OPT (최적화)](../build/reference/opt-optimizations.md)합니다.

```cpp
// friend_assemblies_3.cpp
// compile by using: /clr /LD /link /opt:noref
using namespace System;

ref class Class1 {
public:
   void Test_Public() {
      Console::WriteLine("Class1::Test_Public");
   }
};
```

다음 코드 예제는 해당 전용 형식에 대 한 액세스를 부여 하지 않는 구성 요소에는 전용 형식에 액세스 하려고 하는 클라이언트를 정의 합니다. 런타임 동작으로 인해 해당 예외를 catch 하려는 경우 해야 하려는 개인 형식 도우미 함수에 액세스 합니다.

```cpp
// friend_assemblies_4.cpp
// compile by using: /clr
#using "friend_assemblies_3.dll" as_friend
using namespace System;

void Test() {
   Class1 ^ a = gcnew Class1;
}

int main() {
   // to catch this kind of exception, use a helper function
   try {
      Test();
   }
   catch(MethodAccessException ^ e) {
      Console::WriteLine("caught an exception");
   }
}
```

```Output
caught an exception
```

다음 코드 예제에는 구성 요소에서 형식에 액세스할 수 있는 클라이언트 어셈블리를 지정 하는 강력한 이름의 구성 요소를 만드는 방법을 보여 줍니다.

```cpp
// friend_assemblies_5.cpp
// compile by using: /clr /LD /link /keyfile:friend_assemblies.snk
using namespace System::Runtime::CompilerServices;
using namespace System;
// an assembly attribute, not bound to a type

[assembly:InternalsVisibleTo("friend_assemblies_6, PublicKey=00240000048000009400000006020000002400005253413100040000010001000bf45d77fd991f3bff0ef51af48a12d35699e04616f27ba561195a69ebd3449c345389dc9603d65be8cd1987bc7ea48bdda35ac7d57d3d82c666b7fc1a5b79836d139ef0ac8c4e715434211660f481612771a9f7059b9b742c3d8af00e01716ed4b872e6f1be0e94863eb5745224f0deaba5b137624d7049b6f2d87fba639fc5")];

private ref class Class1 {
public:
   void Test_Public() {
      Console::WriteLine("Class1::Test_Public");
   }
};
```

구성 요소가 해당 공개 키를 지정 해야 함을 알 수 있습니다. 있습니다 다음 명령을 순차적으로 실행 키 쌍을 만들고 공개 키를 가져오려면 명령 프롬프트에서 하는 것이 좋습니다.

**sn -d friend_assemblies.snk**

**sn -k friend_assemblies.snk**

**sn -i friend_assemblies.snk friend_assemblies.snk**

**sn -pc friend_assemblies.snk key.publickey**

**sn -tp key.publickey**

다음 코드 예제에서는 강력한 이름의 구성 요소에는 전용 형식에 액세스합니다.

```cpp
// friend_assemblies_6.cpp
// compile by using: /clr /link /keyfile:friend_assemblies.snk
#using "friend_assemblies_5.dll" as_friend

int main() {
   Class1 ^ a = gcnew Class1;
   a->Test_Public();
}
```

```Output
Class1::Test_Public
```

## <a name="see-also"></a>참고자료

[런타임 플랫폼용 구성 요소 확장](../extensions/component-extensions-for-runtime-platforms.md)
