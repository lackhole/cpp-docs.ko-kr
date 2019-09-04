---
title: '#using 지시문 (C++/cli)'
ms.date: 08/29/2019
f1_keywords:
- friend_as_cpp
- '#using'
- friend_as
- '#using_cpp'
helpviewer_keywords:
- using directive (#using)
- '#using directive'
- LIBPATH environment variable
- preprocessor, directives
ms.assetid: 870b15e5-f361-40a8-ba1c-c57d75c8809a
ms.openlocfilehash: 5dae5c277055157aef5451c19ee020fbbd2aaccb
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70220205"
---
# <a name="using-directive-ccli"></a>#using 지시문 (C++/cli)

[/Clr](../build/reference/clr-common-language-runtime-compilation.md)을 사용 하 여 컴파일된 프로그램으로 메타 데이터를 가져옵니다.

## <a name="syntax"></a>구문

> **#using** *파일* [**as_friend**]

### <a name="parameters"></a>매개 변수

*파일과*\
MSIL .dll, .exe, .netmodule 또는. obj 예를 들면 다음과 같습니다.

`#using <MyComponent.dll>`

**as_friend**\
*파일* 의 모든 형식에 액세스할 수 있도록 지정 합니다. 자세한 내용은 [Friend 어셈블리 (c + +)](../dotnet/friend-assemblies-cpp.md)합니다.

## <a name="remarks"></a>설명

*파일* 은 관리 되는 데이터 및 관리 되는 구문에 대해 가져오는 MSIL (Microsoft 중간 언어) 파일 일 수 있습니다. .Dll 파일에 어셈블리 매니페스트가 포함 된 경우 매니페스트에서 참조 하는 모든 .dll을 가져오고 빌드하는 어셈블리는 메타 데이터의 *파일* 을 어셈블리 참조로 나열 합니다.

*파일* 에 어셈블리가 포함 되어 있지 않은 경우 ( *파일이* 모듈인 경우) 및 현재 (어셈블리) 응용 프로그램의 모듈에서 형식 정보를 사용 하지 않으려는 경우 모듈이 어셈블리에 포함 됨을 나타내는 옵션이 있습니다. [/ASSEMBLYMODULE](../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md)를 사용 합니다. 그러면 어셈블리를 참조하는 모든 애플리케이션에서 모듈의 형식을 사용할 수 있습니다.

**#Using** 를 사용 하는 대신 [/fu](../build/reference/fu-name-forced-hash-using-file.md) 컴파일러 옵션을 사용할 수 있습니다.

**#using** 에 전달 된 .exe 어셈블리는 .Net visual Studio 컴파일러 (예: Visual Basic 또는 Visual C#) 중 하나를 사용 하 여 컴파일해야 합니다.  `/clr`를 사용하여 컴파일된 .exe 어셈블리에서 메타데이터를 가져오면 파일 로드 예외가 발생합니다.

> [!NOTE]
> **#Using** 로 참조 되는 구성 요소는 컴파일 시간에 가져온 다른 버전의 파일을 사용 하 여 실행할 수 있으므로 클라이언트 응용 프로그램이 예기치 않은 결과를 제공 합니다.

컴파일러가 모듈이 아니라 어셈블리의 형식을 인식할 수 있도록 하려면 해당 형식을 강제로 확인 해야 합니다. 예를 들어 형식의 인스턴스를 정의 하 여 강제로 적용할 수 있습니다. 컴파일러에 대 한 어셈블리의 형식 이름을 확인 하는 다른 방법이 있습니다. 예를 들어 어셈블리의 형식에서 상속 하는 경우 형식 이름이 컴파일러에 알려집니다.

[__Declspec (thread)](../cpp/thread.md)를 사용 하는 소스 코드에서 빌드된 메타 데이터를 가져올 때 스레드 의미 체계가 메타 데이터에 유지 되지 않습니다. 예를 들어, **__declspec (thread)** 를 사용 하 여 선언 된 변수는 .NET Framework 공용 언어 런타임에 대해 작성 된 다음 **#using**를 통해 가져오므로 변수에 대 한 **__declspec (thread)** 의미 체계가 없습니다.

**#Using** 에서 참조 하는 파일에서 가져온 모든 형식 (관리 및 네이티브)을 사용할 수 있지만 컴파일러는 네이티브 형식을 정의가 아닌 선언으로 간주 합니다.

`/clr`을 사용하여 컴파일하는 경우 mscorlib.dll은 자동으로 참조됩니다.

LIBPATH 환경 변수는 컴파일러가 **#using**에 전달 된 파일 이름을 확인 하는 경우 검색할 디렉터리를 지정 합니다.

컴파일러는 다음 경로를 따라 참조를 검색 합니다.

- **#Using** 문에 지정 된 경로입니다.

- 현재 디렉터리입니다.

- .NET Framework 시스템 디렉터리

- [/Ai](../build/reference/ai-specify-metadata-directories.md) 컴파일러 옵션을 사용 하 여 추가 된 디렉터리입니다.

- LIBPATH 환경 변수의 디렉터리

## <a name="example"></a>예제

어셈블리 (C)를 빌드하고 다른 어셈블리 (A)를 참조 하는 어셈블리 (B)를 참조 하는 경우 C에서 A의 형식 중 하나를 명시적으로 사용 하지 않는 한 어셈블리 A를 명시적으로 참조할 필요가 없습니다.

```cpp
// using_assembly_A.cpp
// compile with: /clr /LD
public ref class A {};
```

## <a name="example"></a>예제

```cpp
// using_assembly_B.cpp
// compile with: /clr /LD
#using "using_assembly_A.dll"
public ref class B {
public:
   void Test(A a) {}
   void Test() {}
};
```

## <a name="example"></a>예제

다음 샘플에서는 프로그램에서 *using_assembly_A*에 정의 된 형식을 사용 하지 않으므로 *using_assembly_A*를 참조 하지 않는 컴파일러 오류가 발생 하지 않습니다.

```cpp
// using_assembly_C.cpp
// compile with: /clr
#using "using_assembly_B.dll"
int main() {
   B b;
   b.Test();
}
```

## <a name="see-also"></a>참고자료

[전처리기 지시문](../preprocessor/preprocessor-directives.md)
