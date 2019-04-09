---
title: '#using 지시문 (C + + /cli CLI)'
ms.date: 10/18/2018
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
ms.openlocfilehash: ddae6137e94e10f5701e1e7d0f8f7a7514b18662
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59034263"
---
# <a name="using-directive-ccli"></a>#using 지시문 (C + + /cli CLI)

로 컴파일된 프로그램으로 메타 데이터를 가져옵니다 [/clr](../build/reference/clr-common-language-runtime-compilation.md)합니다.

## <a name="syntax"></a>구문

```
#using file [as_friend]
```

### <a name="parameters"></a>매개 변수

*파일*<br/>
MSIL .dll, .exe, .netmodule 또는. obj 예를 들어 개체에 적용된

`#using <MyComponent.dll>`

*as_friend*<br/>
모든 형식과 지정 *파일* 액세스할 수 있습니다. 자세한 내용은 [Friend 어셈블리 (c + +)](../dotnet/friend-assemblies-cpp.md)합니다.

## <a name="remarks"></a>설명

*파일* Microsoft MSIL (intermediate language) 파일을 가져오면 해당 관리 되는 데이터 및 관리 되는 구문에 대 한 일 수 있습니다. .Dll 파일에는 어셈블리 매니페스트를 포함 하 고 매니페스트에서 참조 하는 모든.dll 가져온 빌드 중인 어셈블리 표시 하는 경우 *파일* 어셈블리 참조로 메타 데이터에서입니다.

하는 경우 *파일* 어셈블리를 포함 하지 않습니다 (하는 경우 *파일* 은 모듈)만 나타내는의 옵션이 현재 (어셈블리) 응용 프로그램의 모듈에서 형식 정보를 사용 하지 않을 경우 및 이 모듈은 파트 어셈블리 사용 하 여 [/ASSEMBLYMODULE](../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md)합니다. 그러면 어셈블리를 참조하는 모든 응용 프로그램에서 모듈의 형식을 사용할 수 있습니다.

사용 하는 대신 **#using** 되는 [/FU](../build/reference/fu-name-forced-hash-using-file.md) 컴파일러 옵션입니다.

에 전달 된.exe 어셈블리 **#using** 컴파일해야.NET Visual Studio 컴파일러 (Visual Basic 또는 Visual C#, 예를 들어) 중 하나를 사용 하 여 합니다.  `/clr`를 사용하여 컴파일된 .exe 어셈블리에서 메타데이터를 가져오면 파일 로드 예외가 발생합니다.

> [!NOTE]
> 사용 하 여 참조 되는 구성 요소 **#using** 클라이언트 응용 프로그램에서 예기치 않은 결과가 발생 하는 컴파일 시 가져온 파일의 다른 버전으로 실행할 수 있습니다.

컴파일러가 어셈블리 (모듈 아님)의 형식을 인식할 수 순서로 강제로 수행할 수 있습니다, 예를 들어, 형식의 인스턴스를 정의 하 여 형식을 확인 해야 합니다. 가지 다른 방법으로 예를 들어, 컴파일러에 대 한 어셈블리의 형식 이름을 확인 하는 어셈블리의 형식에서 상속 하는 경우, 형식 이름을 컴파일러에 알려 다음 됩니다.

사용 된 소스 코드에서 작성 된 메타 데이터를 가져오면 [__declspec (thread)](../cpp/thread.md), 메타 데이터에서 스레드 의미 체계가 유지 되지 않습니다. 예를 들어, 사용 하 여 선언 된 변수에 **__declspec (thread)** 는.NET Framework 공용 언어 런타임에 대 한 빌드를 통해 가져온 프로그램에서 컴파일된 **#using**, 더 이상 **__declspec (thread)** 변수에 의미 합니다.

가져온 모든 형식 (관리 / 네이티브)에서 참조 하는 파일의 **#using** 을 사용할 수 있지만 컴파일러 네이티브 형식 정의가 아닌 선언으로 처리 합니다.

`/clr`을 사용하여 컴파일하는 경우 mscorlib.dll은 자동으로 참조됩니다.

LIBPATH 환경 변수를 컴파일러에 전달 된 파일 이름을 확인 하려고 할 때 검색할 디렉터리를 지정 **#using**합니다.

컴파일러는 다음과 같은 경로에 따라 참조를 검색합니다.

- 에 지정 된 경로 **#using** 문입니다.

- 현재 디렉터리입니다.

- .NET Framework 시스템 디렉터리

- 추가 된 디렉터리를 [/AI](../build/reference/ai-specify-metadata-directories.md) 컴파일러 옵션입니다.

- LIBPATH 환경 변수의 디렉터리

## <a name="example"></a>예제

어셈블리(C)를 빌드하고 다른 어셈블리(A)를 참조하는 어셈블리(B)를 참조하는 경우 C에서 A 형식 중 하나를 명시적으로 사용하지 않는 한 어셈블리 A를 명시적으로 참조할 필요가 없습니다.

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

다음 샘플에서는 프로그램이 using_assembly_A.cpp에 정의된 형식 중 하나를 사용하지 않으므로 using_assembly_A.dll을 사용하여 참조하지 않는 컴파일러 오류가 발생하지 않습니다.

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