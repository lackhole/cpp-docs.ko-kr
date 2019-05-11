---
title: '방법: -Clr로 마이그레이션'
ms.custom: get-started-article
ms.date: 09/18/2018
helpviewer_keywords:
- upgrading Visual C++ applications, /clr compiler option
- compiling native code [C++]
- interoperability [C++], /clr compiler option
- interop [C++], /clr compiler option
- migration [C++], /clr compiler option
- /clr compiler option [C++], porting to
ms.assetid: c9290b8b-436a-4510-8b56-eae51f4a9afc
ms.openlocfilehash: 9abc85227d6091005d7e097d3305150f4ca347a1
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2019
ms.locfileid: "65448090"
---
# <a name="how-to-migrate-to-clr"></a>방법: /Clr으로 마이그레이션

이 항목에서는 네이티브 코드를 컴파일할 때 발생 하는 문제를 설명 **/clr** (참조 [/clr (공용 언어 런타임 컴파일)](../build/reference/clr-common-language-runtime-compilation.md) 자세한). **/clr** 네이티브 허용 C++ 를 호출 하 고 다른 네이티브 외에도.NET 어셈블리를 호출할 코드 C++ 코드입니다. 참조 [혼합형 (네이티브 및 관리) 어셈블리](../dotnet/mixed-native-and-managed-assemblies.md) 하 고 [네이티브 및.NET 상호 운용성](../dotnet/native-and-dotnet-interoperability.md) 사용 하 여 컴파일하면의 이점에 대 한 자세한 내용은 **/clr**합니다.

## <a name="known-issues-compiling-library-projects-with-clr"></a>알려진된 문제 컴파일 라이브러리 프로젝트 /clr을 사용한

Visual Studio 라이브러리 프로젝트를 컴파일할 때 알려진된 문제가 포함 되어 있습니다 **/clr**:

- 코드를 사용한 런타임 시 형식을 쿼리할 수 있습니다 [CRuntimeClass::FromName](../mfc/reference/cruntimeclass-structure.md#fromname)합니다. 그러나 형식을 MSIL.dll에서 경우 (사용 하 여 컴파일된 **/clr**), 호출 `FromName` (표시 되지 것입니다이 문제가 보낸사람 호출은 코드 후 발생 하는 경우 관리 되는.dll에 정적 생성자 실행 전에 발생 하는 경우 실패할 수 있습니다 실행할 관리 되는.dll). 이 문제를 해결 하려면 관리 되는.dll의 함수를 정의 하 고, 내보내기 등, 네이티브 MFC 응용 프로그램에서 호출 하 여 관리 되는 정적 생성자의 생성을 강제할 수 있습니다. 예를 들어:

    ```
    // MFC extension DLL Header file:
    __declspec( dllexport ) void EnsureManagedInitialization () {
       // managed code that won't be optimized away
       System::GC::KeepAlive(System::Int32::MaxValue);
    }
    ```

## <a name="compile-with-visual-c"></a>시각적 개체를 사용 하 여 컴파일C++

사용 하기 전에 **/clr** 모든 모듈 프로젝트에 대해 먼저 컴파일 및 Visual Studio 2010을 사용한 네이티브 프로젝트를 연결 합니다.

다음 단계를 순서 대로 가장 쉬운 경로를 제공 된 **/clr** 컴파일. 컴파일 및 이러한 각 단계 후 프로젝트를 실행 하는 것이 반드시 합니다.

### <a name="versions-prior-to-visual-studio-2003"></a>Visual Studio 2003 이전 버전

컴파일러 오류와 관련 된 향상 된 Visual Studio 2003 이전 버전에서 Visual Studio 2010으로 업그레이드 하는 경우 표시 될 수 있습니다 C++ Visual Studio 2003에서 표준 준수

### <a name="upgrading-from-visual-studio-2003"></a>Visual Studio 2003에서 업그레이드

Visual Studio 2003을 사용 하 여 빌드한 프로젝트 이전 먼저 컴파일해야 없이 **/clr** Visual Studio 이제 늘어났습니다 ANSI/ISO 규정 준수 및 몇 가지 주요 변경 내용으로 합니다. 주의가 가장 가능성이 있는 변경 내용이 [CRT의 보안 기능](../c-runtime-library/security-features-in-the-crt.md)합니다. CRT를 사용 하는 코드 사용 중단 경고를 생성 하기 위해 매우 높습니다. 이러한 경고는 표시 되지 않는, 하지만 새 마이그레이션 수 [CRT 함수의 버전 보안이 강화 된](../c-runtime-library/security-enhanced-versions-of-crt-functions.md) 는 것이 좋습니다, 향상 된 보안을 제공 하며 코드에서 보안 문제를 통해 확인할 수 있습니다.

### <a name="upgrading-from-managed-extensions-for-c"></a>Managed Extensions for에서 업그레이드C++

Visual Studio 2005에서는 Managed Extensions for를 사용 하 여 작성 된 코드부터 C++ 아래에서 컴파일되지 **/clr**합니다.

## <a name="convert-c-code-to-c"></a>C 코드를 변환 합니다.C++

Visual Studio C 파일 컴파일되지, 이지만 하도록 변환 하는 데 필요한 C++ 에 대 한는 **/clr** 컴파일. 실제 파일 이름; 변경할 수 없습니다. 사용할 수 있습니다 **/Tp** (참조 [/Tc, /Tp, /TC, /TP (소스 파일 형식 지정)](../build/reference/tc-tp-tc-tp-specify-source-file-type.md).) 하지만 C++ 소스 코드 파일은 **/clr**를 개체 지향 패러다임을 사용 하도록 코드를 리팩터링할 필요는 없습니다.

C 코드를 컴파일할 때 변경 해야 할 가능성이 매우 높습니다는 C++ 파일입니다. C++ 형식 안전성 규칙 되므로 strict, 캐스트를 사용 하 여 명시적 형식 변환을 수행 해야 합니다. 예를 들어, malloc void 포인터를 반환 하지만 c에서 캐스트를 사용 하 여 모든 형식에 대 한 포인터에 할당할 수 있습니다.

```
int* a = malloc(sizeof(int));   // C code
int* b = (int*)malloc(sizeof(int));   // C++ equivalent
```

함수 포인터에 형식이 안전한 엄격 하 게도 C++이므로 다음 C 코드를 수정 해야 합니다. C++ 를 만드는 것이 적합 한 `typedef` 함수 포인터 형식을 정의 하 고 그런 다음 해당 형식을 함수 포인터를 사용 하 여:

```
NewFunc1 = GetProcAddress( hLib, "Func1" );   // C code
typedef int(*MYPROC)(int);   // C++ equivalent
NewFunc2 = (MYPROC)GetProcAddress( hLib, "Func2" );
```

C++또한 있어야 함수 하거나 프로토타입화 하거나 완전히 정의 된 참조 하거나 호출할 수 있습니다.

키워드 될 수 있는 C 코드에서 사용 하는 식별자 C++ (같은 **가상**합니다 **새**, **삭제**, **bool**,  **true**하십시오 **false**등) 이름을 변경 해야 합니다. 이 간단한 검색 및 바꾸기 작업을 사용 하 여 일반적으로 수행할 수 있습니다.

```
COMObj1->lpVtbl->Method(COMObj, args);  // C code
COMObj2->Method(args);  // C++ equivalent
```

## <a name="reconfigure-project-settings"></a>프로젝트 설정을 다시 구성

새 프로젝트 구성에 대 한 프로젝트를 컴파일하고 Visual Studio 2010에서 실행 후 만들어야 **/clr** 기본 구성을 수정 대신 합니다. **/clr** 일부 컴파일러 옵션을 사용 하 여 호환 되지 않습니다 별도 구성이 만들면를 네이티브 또는 관리 되는 프로젝트를 빌드할 수 있습니다. 때 **/clr** 속성 페이지 대화 상자와 호환 되지 않는 프로젝트 설정에서에서 선택한 **/clr** 사용 하지 않도록 설정 됩니다 (사용 안 함된 옵션 경우 자동으로 복원 되지 않습니다 및 **/clr** 이후에 선택 하지 않은).

### <a name="create-new-project-configurations"></a>새 프로젝트 구성 만들기

사용할 수 있습니다 **에서 설정 복사** 옵션을 **새 프로젝트 구성 대화 상자** (**빌드** > **ConfigurationManager**  >  **활성 솔루션 구성이** > **새**) 기존 프로젝트 설정에 따라 프로젝트 구성을 만들 수 있습니다. 이렇게 하려면 한 번 및 한 번 릴리스 구성을 디버그 구성에 대 한 합니다. 후속 변경 내용에 적용할 수 있습니다 합니다 **/clr** -관련 구성만 원래 프로젝트 구성은 그대로입니다.

사용자 지정 빌드 규칙을 사용 하는 프로젝트에 특별히 주의 해야 합니다.

이 단계에 메이크파일을 사용 하는 프로젝트에 대 한 여러 문제점이 있습니다. 별도 빌드 대상을 구성할 수 있으며이 경우에 한정 된 버전 **/clr** 컴파일 원래 복사본에서 만들 수 있습니다.

### <a name="change-project-settings"></a>프로젝트 설정 변경

**/clr** 의 지침에 따라 개발 환경에서 선택할 수 있습니다 [/clr (공용 언어 런타임 컴파일)](../build/reference/clr-common-language-runtime-compilation.md)합니다. 이전에 설명한 대로이 단계는 충돌 하는 프로젝트 설정을 자동으로 비활성화 됩니다.

> [!NOTE]
>  Visual Studio 2003에서 관리 되는 라이브러리 또는 웹 서비스 프로젝트를 업그레이드 하는 경우는 **/Zl** 컴파일러 옵션이 추가 됩니다 합니다 **명령줄** 속성 페이지. 그러면 LNK2001 합니다. 제거 **/Zl** 에서 합니다 **명령줄** 속성 페이지를 확인 합니다. 참조 [/Zl (기본 라이브러리 이름 생략)](../build/reference/zl-omit-default-library-name.md) 하 고 [컴파일러 설정 및 빌드 속성](../build/working-with-project-properties.md) 자세한 내용은 합니다. 또는 링커의 msvcrt.lib와 msvcmrt.lib 추가할 **추가 종속성** 속성입니다.

프로젝트의 메이크파일을 사용 하 여 빌드한 경우 호환 되지 않는 컴파일러 옵션을 비활성화 해야 수동으로 한 번 **/clr** 추가 됩니다. 참조 /[/clr 제한](../build/reference/clr-restrictions.md) 와 호환 되지 않는 컴파일러 옵션에 대 한 내용은 **/clr**합니다.

### <a name="precompiled-headers"></a>미리 컴파일된 헤더

지원 되는 미리 컴파일된 헤더 **/clr**합니다. 그러나만 컴파일하는 경우 사용 하 여 CPP 파일의 일부 **/clr** (나머지 네이티브로 컴파일) 일부 변경이 필요할 수 있으므로 미리 컴파일된 헤더를 사용 하 여 생성 **/clr** 와 호환 되지 않습니다 없이 생성 **/clr**합니다. 이러한 비 호환성은 때문에 **/clr** 생성 하 고 메타 데이터를 요구 합니다. 컴파일된 모듈이 **/clr** 메타 데이터를 포함 하지 않는 미리 컴파일된 헤더를 사용할 따라서 수 및 비 **/clr** 모듈 메타 데이터가 포함 된 미리 컴파일된 헤더 파일을 사용할 수 없습니다.

일부 모듈 컴파일되는 프로젝트를 컴파일하는 가장 쉬운 방법은 **/clr** 미리 컴파일된 헤더를 완전히 사용 하지 않도록 설정 하는 것입니다. (프로젝트 속성 페이지 대화 상자를 열고 C /C++ 노드와 미리 컴파일된 헤더를 선택 합니다. 그런 다음 속성을 변경할 미리 컴파일된 헤더 만들기/사용 "되지를 사용 하 여 미리 컴파일된 헤더에".)

그러나 특히 대규모 프로젝트에 대 한 미리 컴파일된 헤더 제공 컴파일 속도가 대폭 향상 하므로 필요 없는이 기능을 사용 하지 않도록 설정 합니다. 이 경우 것이 최적으로 구성 하는 **/clr** 및 비 **/clr** 별도 미리 컴파일된 헤더를 사용 하는 파일. 한 번에이 작업을 수행할 수 있습니다 다중 선택 모듈을 컴파일할 수 **/clr** 를 사용 하 여 **솔루션 탐색기**속성을 선택 하 고 그룹을 마우스 오른쪽 단추로 클릭 합니다. 각각 다른 헤더 파일 이름 및 PCH 파일을 사용 하도록 파일에서 PCH 만들기/사용와 미리 컴파일된 헤더 파일 속성을 변경 합니다.

## <a name="fixing-errors"></a>오류 수정

사용 하 여 컴파일하면 **/clr** 컴파일러, 링커 또는 런타임 오류가 발생할 수 있습니다. 이 섹션에서는 가장 일반적인 문제를 설명 합니다.

### <a name="metadata-merge"></a>메타 데이터 병합

서로 다른 버전의 데이터 형식에는 두 형식에 대해 생성 된 메타 데이터가 일치 하지 않으므로 실패 하도록 링커에 발생할 수 있습니다. (일반적으로는 형식의 멤버 조건에 따라 정의 되지만 조건과 동일 하지 않은 형식을 사용 하는 모든 CPP 파일에 대 한 경우.) 이 경우 링커에 실패 기호 이름과 형식이 정의 된 두 번째 OBJ 파일의 이름을 보고 합니다. 데이터 형식의 다른 버전의 위치를 검색 하려는 링커에 OBJ 파일을 보낸 순서를 회전 하는 것이 유용 합니다.

### <a name="loader-lock-deadlock"></a>로더 잠금 교착 상태

"로더 잠금 교착 상태"가 발생할 수 있지만 결정적 검색 되 고 런타임 시 보고 합니다. 참조 [혼합 어셈블리 초기화](../dotnet/initialization-of-mixed-assemblies.md) 자세한 배경을, 지침 및 솔루션에 대 한 합니다.

### <a name="data-exports"></a>데이터 내보내기

DLL 데이터를 내보내는 경우 오류가 발생 하기 쉬우며 권장 하지 않음 즉, DLL의 data 섹션 DLL의 관리 되는 일부 실행 될 때까지 초기화할 보장 되지 않습니다. 메타 데이터를 사용 하 여 참조 [#using 지시문](../preprocessor/hash-using-directive-cpp.md)합니다.

### <a name="type-visibility"></a>형식 표시 유형

네이티브 형식은 기본적으로 private입니다. 이 DLL 외부에 표시 되 고 있지는 네이티브 형식에서 발생할 수 있습니다. 추가 하 여이 오류를 해결 `public` 이러한 형식에 있습니다.

### <a name="floating-point-and-alignment-issues"></a>부동 소수점 및 맞춤 문제

`__controlfp` 공용 언어 런타임 지원 되지 않습니다 (참조 [_control87, _controlfp, \__control87_2](../c-runtime-library/reference/control87-controlfp-control87-2.md) 자세한). CLR은 또한 영향을 미치지 [맞춤](../cpp/align-cpp.md)합니다.

### <a name="com-initialization"></a>COM 초기화

공용 언어 런타임 초기화 COM 자동으로 모듈을 초기화 될 때 (자동으로 COM을 초기화 하는 경우 소기의 MTA로). 결과적으로, 명시적으로 COM을 초기화 COM 이미 초기화 되어 있다고 나타내는 반환 코드를 생성 합니다. CLR에서 이미 다른 스레딩 모델에 COM 초기화 하는 경우 COM 스레딩 모델 하나를 사용 하 여 명시적으로 초기화 하는 동안 응용 프로그램에 발생할 수 있습니다.

공용 언어 런타임은 기본적으로 COM MTA로 시작 사용 하 여 [/CLRTHREADATTRIBUTE (CLR 스레드 특성 설정)](../build/reference/clrthreadattribute-set-clr-thread-attribute.md) 이 수정 합니다.

### <a name="performance-issues"></a>성능 문제

네이티브 경우 성능 저하가 나타날 수 있습니다 C++ MSIL로 생성 된 메서드를 직접 호출 됩니다 (가상 함수 호출 또는 함수 포인터를 사용 하 여). 이 대 한 자세한 내용은 참조 하세요 [이중 썽킹](../dotnet/double-thunking-cpp.md)합니다.

MSIL을 네이티브 코드에서 이동 하는 경우에 작업 집합의 크기 증가 확인할 수 있습니다. 프로그램이 올바르게 실행 되도록 많은 기능을 제공 하는 공용 언어 런타임 때문입니다. 경우에 **/clr** C4793를 사용 하도록 설정 하려는 경우, 응용 프로그램을 올바르게 실행 되지 않습니다 (기본적으로 꺼져 있음)를 참조 하세요 [컴파일러 경고 (수준 1 및 3) C4793](../error-messages/compiler-warnings/compiler-warning-level-1-and-3-c4793.md) 자세한 내용은 합니다.

### <a name="program-crashes-on-shutdown"></a>종료 시 프로그램 충돌

경우에 따라 CLR가 종료 관리 되는 코드 작업이 완료 되기 전에 실행 됩니다. 사용 하 여 `std::set_terminate` 고 `SIGTERM` 하기 때문일 수 있습니다. 참조 [신호 상수](../c-runtime-library/signal-constants.md) 하 고 [set_terminate](../c-runtime-library/abnormal-termination.md) 자세한 내용은 합니다.

## <a name="using-new-visual-c-features"></a>새 시각적 개체를 사용 하 여 C++ 기능

다음에 응용 프로그램 컴파일, 링크 및 실행을 시작할 수 있습니다로 컴파일된 모든 모듈에서.NET 기능을 사용 하 여 **/clr**합니다. 자세한 내용은 [런타임 플랫폼의 구성 요소 확장](../extensions/component-extensions-for-runtime-platforms.md)을 참조하세요.

Managed Extensions for를 사용 하는 경우 C++, 새 구문을 사용 하 여 코드를 변환할 수 있습니다. Managed Extensions for 변환에 대 한 내용은 C++를 참조 하세요 [ C++CLI 마이그레이션 입문](../dotnet/cpp-cli-migration-primer.md)합니다.

시각적 개체의.NET 프로그래밍에 대 한 내용은 C++ 을 참조 합니다.

- [C++/CLI를 사용한 .NET 프로그래밍(Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)

- [네이티브 및 .NET 상호 운용성](../dotnet/native-and-dotnet-interoperability.md)

- [런타임 플랫폼용 구성 요소 확장](../extensions/component-extensions-for-runtime-platforms.md)

## <a name="see-also"></a>참고자료

[혼합형(네이티브 및 관리) 어셈블리](../dotnet/mixed-native-and-managed-assemblies.md)
