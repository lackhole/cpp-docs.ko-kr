---
title: /clr(공용 언어 런타임 컴파일)
ms.date: 09/18/2018
f1_keywords:
- /CLR
- VC.Project.VCNMakeTool.CompileAsManaged
- VC.Project.VCCLCompilerTool.CompileAsManaged
helpviewer_keywords:
- cl.exe compiler, common language runtime option
- -clr compiler option [C++]
- clr compiler option [C++]
- /clr compiler option [C++]
- Managed Extensions for C++, compiling
- common language runtime, /clr compiler option
ms.assetid: fec5a8c0-40ec-484c-a213-8dec918c1d6c
ms.openlocfilehash: 1946fdabe66934e64cf95d3c3f12e16bc98ba664
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62272548"
---
# <a name="clr-common-language-runtime-compilation"></a>/clr(공용 언어 런타임 컴파일)

애플리케이션 및 구성 요소가 CLR(공용 언어 런타임)의 기능을 사용할 수 있게 합니다.

## <a name="syntax"></a>구문

> **/clr**[**:**_options_]

## <a name="arguments"></a>인수

*options*<br/>
다음 스위치가 하나 이상 쉼표로 구분되어 있습니다.

- 없음

   옵션 없이 **/clr** 응용 프로그램에 대 한 메타 데이터를 만듭니다. 메타데이터는 다른 CLR 애플리케이션에서 사용될 수 있으며 애플리케이션이 다른 CLR 구성 요소의 메타데이터에 있는 형식과 데이터를 사용할 수 있게 합니다. 자세한 내용은 [혼합형 (네이티브 및 관리) 어셈블리](../../dotnet/mixed-native-and-managed-assemblies.md)합니다.

- **pure**

   **/clr: pure 되지**합니다. 옵션은 Visual Studio 2017에서 제거 됩니다. C#에 대한 순수형 MSIL이어야 하는 코드를 포팅하는 것이 좋습니다.

- **safe**

   **/clr: safe는 사용 되지 않습니다.** 합니다. 옵션은 Visual Studio 2017에서 제거 됩니다. C#에 안전 하 게 MSIL 이어야 하는 코드를 포팅하는 것이 좋습니다.

- **noAssembly**

   **/clr:noAssembly 되지**합니다. 대신 [/LN (Create MSIL Module)](ln-create-msil-module.md) 를 사용하세요.

   어셈블리 매니페스트를 출력 파일에 삽입하지 않도록 지정합니다. 기본적으로 **noAssembly** 옵션은 적용되지 않습니다.

   매니페스트에 어셈블리 메타데이터가 없는 관리되는 프로그램을 *모듈*이라고 합니다. **noAssembly** 옵션은 모듈을 생성하는 데만 사용할 수 있습니다. [/c](c-compile-without-linking.md) 및 **/clr:noAssembly**를 사용하여 컴파일하는 경우 링커 단계에서 [/NOASSEMBLY](noassembly-create-a-msil-module.md) 옵션을 지정하여 모듈을 만듭니다.

   Visual C++ 2005 이전은, **/clr:noAssembly** 에 **/LD**가 필요합니다. **/clr:noAssembly** 를 지정할 때 **/LD**가 암시됩니다.

- **initialAppDomain**

   시각적 개체를 사용 하도록 설정 C++ 의 CLR 버전 1에서 실행할 응용 프로그램입니다.  **initialAppDomain** 을 사용하여 컴파일된 응용 프로그램은 CLR 버전 1에서 지원되지 않으므로 ASP.NET을 사용하는 응용 프로그램에서 사용하면 안됩니다.

- **nostdlib**

   기본 \clr 디렉터리를 무시하도록 컴파일러에 지시합니다. System.dll과 같은 DLL의 여러 버전을 포함하는 경우 컴파일러에서 오류가 발생합니다. 이 옵션을 사용하면 컴파일하는 동안 사용할 특정 프레임워크를 지정할 수 있습니다.

## <a name="remarks"></a>설명

관리 코드는 CLR에서 검사 및 관리할 수 있는 코드입니다. 관리 코드는 관리되는 개체에 액세스할 수 있습니다. 자세한 내용은 [/clr Restrictions](clr-restrictions.md)을 참조하십시오.

관리되는 형식을 정의 및 사용하는 애플리케이션을 개발하는 방법에 대한 자세한 내용은 [Component Extensions for Runtime Platforms](../../extensions/component-extensions-for-runtime-platforms.md).

**/clr** 을 사용하여 컴파일된 응용 프로그램은 관리되는 데이터를 포함할 수도 있고, 포함하지 않을 수도 있습니다.

관리 되는 응용 프로그램에서 디버깅을 사용 하려면 참조 [/ASSEMBLYDEBUG (DebuggableAttribute 추가)](assemblydebug-add-debuggableattribute.md)합니다.

CLR 형식만 가비지 수집 힙에 인스턴스화됩니다. 자세한 내용은 [클래스 및 구조체](../../extensions/classes-and-structs-cpp-component-extensions.md)합니다. 함수를 네이티브 코드로 컴파일하려면 `unmanaged` pragma를 사용합니다. 자세한 내용은 [관리 되는, 관리 되지 않는](../../preprocessor/managed-unmanaged.md)합니다.

기본적으로 **/clr** 은 적용되지 않습니다. **/clr** 이 적용되는 경우 **/MD** 도 적용됩니다. 자세한 내용은 [/MD, /MT, /LD(런타임 라이브러리 사용)](md-mt-ld-use-run-time-library.md)를 참조하세요. **/MD** 는 표준 헤더(.h) 파일에서 동적으로 연결된 다중 스레드 버전의 런타임 루틴이 선택되도록 합니다. CLR 가비지 수집기는 보조 스레드에서 종료자를 실행하므로 관리되는 프로그래밍에 다중 스레딩이 필요합니다.

사용 하 여 컴파일하면 **/c**를 사용 하 여 결과 출력 파일의 CLR 형식을 지정할 수 있습니다 [/CLRIMAGETYPE](clrimagetype-specify-type-of-clr-image.md)합니다.

**/clr** 은 **/EHa**를 암시하며, 다른 **/EH** 옵션은 **/clr**에 대해 지원되지 않습니다. 자세한 내용은 [/EH(예외 처리 모델)](eh-exception-handling-model.md)를 참조하세요.

파일의 CLR 이미지 형식을 결정하는 방법에 대한 자세한 내용은 [/CLRHEADER](clrheader.md)를 참조하세요.

링커의 지정된 호출에 전달되는 모든 모듈은 동일한 런타임 라이브러리 컴파일러 옵션(**/MD** or **/LD**)을 사용하여 컴파일해야 합니다.

어셈블리에 리소스를 포함하려면 [/ASSEMBLYRESOURCE](assemblyresource-embed-a-managed-resource.md) 링커 옵션을 사용합니다. [/DELAYSIGN](delaysign-partially-sign-an-assembly.md), [/KEYCONTAINER](keycontainer-specify-a-key-container-to-sign-an-assembly.md)및 [/KEYFILE](keyfile-specify-key-or-key-pair-to-sign-an-assembly.md) 링커 옵션을 사용하여 어셈블리를 만드는 방법을 사용자 지정할 수도 있습니다.

**/clr** 을 사용하는 경우 `_MANAGED` 기호가 1로 정의됩니다. 자세한 내용은 [Predefined Macros](../../preprocessor/predefined-macros.md)을 참조하십시오.

네이티브 개체 파일의 전역 변수가 먼저 초기화된 다음(실행 파일이 DLL인 경우 DllMain 중에) 관리되는 섹션의 전역 변수가 초기화됩니다(관리 코드가 실행되기 전에). `#pragma` [init_seg](../../preprocessor/init-seg.md) 만 관리 하 고 관리 되지 않는 범주의 초기화 순서에 영향을 줍니다.

## <a name="metadata-and-unnamed-classes"></a>메타데이터 및 명명되지 않은 클래스

명명되지 않은 클래스는 `$UnnamedClass$`*crc-of-current-file-name*`$`*index*`$`와 같이 이름이 지정된 메타데이터에 나타납니다. 여기서 *index* 는 컴파일할 때 이름이 지정되지 않은 클래스의 순차적 개수입니다. 예를 들어 다음 코드 샘플은 메타데이터에 명명되지 않은 클래스를 생성합니다.

```cpp
// clr_unnamed_class.cpp
// compile by using: /clr /LD
class {} x;
```

메타데이터를 보려면 Ildasm.exe를 사용합니다.

## <a name="see-also"></a>참고자료

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
