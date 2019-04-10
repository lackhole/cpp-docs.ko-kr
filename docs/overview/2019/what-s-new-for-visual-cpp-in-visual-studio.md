---
title: Visual Studio 2019의 새로운 C++ 기능
ms.date: 04/02/2019
ms.technology: cpp-ide
ms.assetid: 8801dbdb-ca0b-491f-9e33-01618bff5ae9
author: mikeblome
ms.author: mblome
ms.openlocfilehash: 493b96a8ce3359cc18287adbae8cbd6c374671ec
ms.sourcegitcommit: b72a10a7b12e722fd91a17406b91b270026f763a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/03/2019
ms.locfileid: "58899409"
---
<!--NOTE all https:// links to docs.microsoft.com need to be converted to site-relative links prior to publishing-->

# <a name="whats-new-for-c-in-visual-studio-2019"></a>Visual Studio 2019의 새로운 C++ 기능

Visual Studio 2019에는 Microsoft C++ 환경에 대한 많은 업데이트와 수정이 포함되었습니다. 대부분 **사용자 의견 보내기** 아래의 [문제 보고](/visualstudio/how-to-report-a-problem-with-visual-studio-2017) 및 [제안하기](https://developercommunity.visualstudio.com/spaces/62/index.html) 옵션을 통해 고객이 제출한 많은 버그와 보고된 문제를 해결했습니다. 버그를 알려 주셔서 감사합니다. 모든 Visual Studio의 새로운 기능에 대한 자세한 내용은 [Visual Studio의 새로운 기능](/visualstudio/ide/whats-new-visual-studio-2019)을 참조하세요.

## <a name="c-compiler"></a>C++ 컴파일러

- `/std:c++latest` 옵션에는 세 방향 비교를 위한 C++20 operator <=> ("spaceship")의 초기 지원을 포함한 완료되지 않은 C++20 기능이 포함되어 있습니다.

- [P0941R2 - feature-test 매크로](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0941r2.html)는 `__has_cpp_attribute`에 대한 지원으로 완료되었습니다. Feature-test 매크로는 모든 표준 모드에서 지원됩니다.

- [C++20 P1008R1 - 사용자 선언 생성자를 사용하여 집계 금지](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p1008r1.pdf)도 완료되었습니다.

- C++ 17 기능에 대한 향상된 지원 및 모듈, 코루틴 등과 같은 C++ 20 기능에 대한 실험적 지원입니다. 자세한 내용은 [Visual Studio 2019의 C++ 규칙 향상](../cpp-conformance-improvements.md)을 참조하세요.

- C++ 컴파일러 스위치 `/Gm`은 이제 사용되지 않습니다. 명시적으로 정의된 경우 빌드 스크립트에서 `/Gm` 스위치를 사용하지 않도록 설정하는 것이 좋습니다. 하지만 "경고를 오류로 처리"(`/WX`)를 사용하는 경우 오류로 처리되지 않으므로 `/Gm`에 대한 사용 중단 경고를 안전하게 무시할 수도 있습니다.

- C++ 콘솔 및 데스크톱 앱의 경우 미리 컴파일된 헤더가 더 이상 생성되지 않습니다.

### <a name="codegen-security-diagnostics-and-versioning"></a>Codegen, 보안, 진단 및 버전 관리

스펙터 변형 1(CVE-2017-5753)에 대한 완화 지원을 제공하기 위해 `/Qspectre`를 사용한 분석을 개선했습니다. 자세한 내용은 [MSVC의 스펙터 완화](https://devblogs.microsoft.com/cppblog/spectre-mitigations-in-msvc/)를 참조하세요.

## <a name="c-standard-library-improvements"></a>C++ 표준 라이브러리 향상

- [C++ 20 P0550R2\(remove_cvref)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0550r2.pdf)가 완료되었습니다.

- C++ 17 \<charconv> floating-point to_chars()가 향상되었습니다. shortest chars_format::fixed는 60~80%가 빠르고 shortest/precision chars_format::hex가 완료되었습니다.

- 자세한 알고리즘은 구현을 병렬화했습니다. implementations: is_sorted(), is_sorted_until(), is_partitioned(), set_difference(), set_intersection(), is_heap(), is_heap_until()

- `std::variant`에 대한 향상된 기능으로 인해 최적화 프로그램이 친화적으로 만들어져 좋은 코드를 생성하게 되었습니다. 코드 인라인은 `std::visit`를 사용하는 것이 좋습니다.

- 가독성 향상을 위해 C++ 표준 라이브러리 헤더에 Clang 형식을 적용했습니다.

- 몇 가지 표준 라이브러리 기능이 `if constexpr`을 사용하여 컴파일되면 처리량을 향상시켰습니다.

- 표준 라이브러리 실제 디자인을 최적화하여 #include'd가 아닌 표준 라이브러리의 일부를 컴파일하지 않으면 \<vector>만 포함된 빈 비어 있는 파일의 빌드 시간 중 절반을 잘라냅니다.

## <a name="performancethroughput-fixes"></a>성능/처리량 수정

- 링커에서 파일 I/O를 처리하는 방식 및 PDB 형식 병합 및 생성 시 링크 시간을 포함한 빌드 처리량 향상된 기능입니다.

- OpenMP SIMD 벡터화에 대한 기본 지원을 추가했습니다. 새 CL 스위치 `-openmp:experimental`을 사용하여 설정할 수 있습니다. 이 옵션을 사용하면 `#pragma omp simd`로 주석을 단 루프가 잠재적으로 벡터화될 수 있습니다. 벡터화는 보장되지 않으며 주석이 있지만 벡터화되지 않은 루프에는 보고된 경고가 표시됩니다. SIMD 절은 지원되지 않고 보고된 경고를 표시하여 무시됩니다.

- `-Ob2`의 적극적인 버전인 새로운 인라인 명령줄 스위치 `-Ob3`을 추가했습니다. `-O2` (속도를 위해 이진 파일 최적화)기본적으로 `-Ob2`를 의미합니다. 컴파일러가 충분히 적극적으로 인라인하지 않는다면 `-O2 -Ob3`을 전달하는 것이 좋습니다.

- 수학 라이브러리 함수 및 정수 나누기와 같은 특정 다른 작업에 대한 호출을 포함하는 루프의 수동 벡터화를 지원하기 위해 SVML(Short Vector Math Library) 내장 함수에 대한 지원을 추가했습니다. 이러한 함수는 해당하는 128비트, 256비트 또는 512비트 벡터를 계산합니다. 지원되는 기능에 대한 정의는 [Intel Intrinsic 가이드](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#!=undefined&techs=SVML)를 참조하세요.

- 새로운 기능과 향상된 최적화:

  - 부동 소수점 및 정수 양식 모두에 대해 SIMD 벡터 내장 함수를 사용하는 식에 대한 상수 폴딩 및 산술을 단순화했습니다.

  - 제어 흐름(if/else/switch 문)에서 정보를 추출하여 항상 true 또는 false인 것으로 입증되는 분기를 제거하기 위한 강력한 분석을 추가했습니다.

  - SSE2 벡터 지침을 사용하도록 memset 언롤링을 개선했습니다.

  - 특히 값으로 전달되는 C++ 프로그램의 경우 쓸모 없는 구조체/클래스 복사본 제거를 개선했습니다.

  - `std::copy`, `std::vector` 및 `std::string` 구문과 같은 `memmove`를 사용하여 코드의 최적화를 개선했습니다.

## <a name="c-ide"></a>C++ IDE

### <a name="live-share-c-support"></a>Live Share C++ 지원

[Live Share](/visualstudio/liveshare/)는 이제 C++를 지원하므로 개발자가 Visual Studio 또는 Visual Studio Code를 사용하여 실시간으로 공동 작업을 수행할 수 있습니다. 자세한 내용은 [ C++용 Live Share 알림: 실시간 공유 및 공동 작업](https://devblogs.microsoft.com/cppblog/cppliveshare/)을 참조하세요.

### <a name="intellicode-for-c"></a>C++용 IntelliCode

IntelliCode는 광범위한 학습 및 코드 컨텍스트를 사용하는 선택적 확장으로 사용할 가능성이 가장 높은 항목을 완성 목록의 맨 위에 배치합니다. 목록을 아래로 스크롤할 필요가 없어질 수 있습니다. C++의 경우 IntelliCode는 표준 라이브러리와 같은 인기 있는 라이브러리를 사용할 때 가장 도움이 됩니다. 자세한 내용은 [IntelliCode를 통해 C++에 대한 AI 지원 코드 완성 추천](https://devblogs.microsoft.com/cppblog/cppintellicode/)을 참조하세요.

### <a name="template-intellisense"></a>템플릿 IntelliSense

이제 **템플릿 모음**은 모달 창 대신 **피크 창** UI를 활용하고 중첩된 템플릿을 지원하며 모든 기본 인수를 **피크 창**에 미리 채웁니다. 자세한 내용은 [Visual Studio 2019 Preview 2에 대한 템플릿 IntelliSense 향상](https://devblogs.microsoft.com/cppblog/template-intellisense-improvements-for-visual-studio-2019-preview-2/)을 참조하세요. **템플릿 모음**에서 **가장 최근에 사용됨** 드롭다운을 사용하면 샘플 인수의 이전 세트 간을 신속하게 전환할 수 있습니다.

### <a name="new-start-window-experience"></a>새로운 시작 창 환경

IDE를 시작할 때 최근에 사용한 프로젝트 열기, 소스 제어에서 코드 복제, 솔루션 또는 폴더로 로컬 코드 열기, 새 프로젝트 만들기 옵션을 사용하여 새로운 시작 창이 나타납니다. 새 프로젝트 대화 상자는 우선 검색, 필터링 가능 환경으로 철저히 점검되었습니다.

### <a name="new-names-for-some-project-templates"></a>일부 프로젝트 템플릿에 대한 새 이름

업데이트된 새 프로젝트 대화 상자에 맞게 몇 개의 프로젝트 템플릿 이름과 설명이 수정되었습니다.

### <a name="various-productivity-improvements"></a>다양한 생산성 향상

Visual Studio 2019에는 코딩을 쉽고 직관적으로 만드는 데 도움이 되는 다음 기능이 포함됩니다.

- 다음에 대한 빠른 수정:
  - 누락된 #include 추가
  - NULL에서 nullptr로
  - 누락된 세미콜론 추가
  - 누락된 네임스페이스 또는 범위 확인
  - 잘못된 간접 참조 피연산자 바꾸기(\*를 &로, &를 \*로)
- 닫는 중괄호를 마우스로 가리켜서 블록에 대한 요약 정보 제공
- 헤더/코드 파일 피킹
- #include에서 정의로 이동하여 파일 열기

자세한 내용은 [Visual Studio 2019 Preview 2의 C++ 생산성 향상](https://devblogs.microsoft.com/cppblog/c-productivity-improvements-in-visual-studio-2019-preview-2/)을 참조하세요.

## <a name="cmake-support"></a>CMake 지원

- Visual Studio는 이제 CMakeGUI와 같은 외부 도구, 사용자 지정 메타 빌드 시스템 또는 cmake.exe 자체를 호출하는 빌드 스크립트에서 생성된 기존 CMake 캐시를 열 수 있습니다.

- IntelliSense 성능이 개선되었습니다.

- 새로운 설정 편집기는 CMakeSettings.json 파일을 수동으로 편집하기 위한 대안을 제공하고 CMakeGUI와 일부 패리티를 제공합니다.

- Visual Studio는 Linux 머신에 호환되는 CMake 버전이 있는지 및 설치하도록 제안하지 않는지 검색하여 Linux에서 CMake를 사용하여 C++ 개발을 부트스트랩하도록 도와줍니다.

- 일치하지 않는 아키텍처 또는 호환되지 않는 CMake 생성기 설정과 같은 CMakeSettings의 호환되지 않는 설정은 JSON 편집기의 오류 표시선과 오류 목록의 오류를 표시합니다.

- `vcpkg integrate install`이 실행된 후 IDE에서 열리는 CMake 프로젝트에 대해 vcpkg 도구 체인이 자동으로 검색되고 활성화됩니다. 이 동작은 CMakeSettings에서 빈 도구 체인 파일을 지정하여 해제할 수 있습니다.

- 이제 CMake 프로젝트는 기본적으로 내 코드만 디버깅을 활성화합니다.

- 이제 정적 분석 경고는 백그라운드에서 처리되어 CMake 프로젝트에 대한 편집기에 표시될 수 있습니다.

- CMake 프로젝트에 대한 '시작' 및 '종료' 메시지를 명확하게 빌드 및 구성하고, Visual Studio의 빌드 진행 UI를 지원합니다. 또한 이제 출력 창에서 CMake 빌드 및 구성 메시지의 세부 수준을 사용자 지정하는 **도구 > 옵션**의 CMake 세부 정보 설정이 있습니다.

- 이제 `cmakeToolchain` 설정이 CMakeSettings.json에서 지원되어 CMake 명령줄을 수동으로 수정하지 않고도 도구 체인을 지정할 수 있습니다.

- 새 **모두 빌드** 메뉴 바로 가기 **Ctrl+Shift+B**입니다.

## <a name="debugging"></a>디버깅

- Windows에서 실행되는 C++ 애플리케이션의 경우 PDB 파일은 이제 별도의 64비트 프로세스로 로드됩니다. 이 변경 내용은 많은 수의 모듈과 PDB 파일이 포함된 애플리케이션을 디버그할 때 메모리가 부족한 디버거 실행으로 인해 발생하는 다양한 충돌을 해결합니다.

## <a name="windows-desktop-development-with-c"></a>C++를 사용한 Windows 데스크톱 개발

- 이러한 C++ ATL/MFC 마법사는 더 이상 사용할 수 없습니다.

  - ATL COM+ 1.0 구성 요소 마법사
  - ATL Active Server Pages 구성 요소 마법사
  - ATL OLE DB 공급자 마법사
  - ATL 속성 페이지 마법사
  - ATL OLE DB 소비자 마법사
  - MFC ODBC 소비자
  - ActiveX 컨트롤의 MFC 클래스
  - TypeLib의 MFC 클래스

  이러한 기술에 대한 샘플 코드는 Microsoft Docs 및 VCSamples GitHub 리포지토리에 보관됩니다.

- Windows 8.1 SDK는 Visual Studio 설치 관리자에서 더 이상 사용할 수 없습니다. C++ 프로젝트를 최신 Windows 10 SDK로 업그레이드하는 것이 좋습니다. 8.1에 대한 종속성이 높은 경우 Windows SDK 아카이브에서 다운로드할 수 있습니다.

- Windows XP 대상은 최신 C++ 도구 세트에서 더 이상 사용할 수 없습니다. VS 2017 수준 MSVC 컴파일러 및 라이브러리가 있는 XP 대상은 여전히 지원되며 "개별 구성 요소"를 통해 설치할 수 있습니다.

- 설명서에서는 Visual C++ 런타임 배포를 위한 병합 모듈의 사용을 적극적으로 권장하지 않습니다. MSM이 사용되지 않는 것으로 표시하는 이번 릴리스의 추가 단계를 진행하고 있습니다. VCRuntime 중앙 배포를 MSM에서 재배포 가능 패키지로 마이그레이션하는 것이 좋습니다.

## <a name="mobile-development-with-c-android-and-ios"></a>C++를 사용한 모바일 개발(Android 및 iOS)

C++ Android 환경은 이제 기본적으로 Android SDK 25와 Android NDK 16b로 설정됩니다.

## <a name="clangc2-platform-toolset"></a>Clang/C2 플랫폼 도구 집합

Clang/C2 실험적 구성 요소가 제거되었습니다. C++ 표준을 완전하게 준수할 수 있도록 `/permissive-` 및 `/std:c++17` 또는 Windows용 Clang/LLVM 도구 체인이 포함된 MSVC 도구 집합을 사용합니다.

## <a name="code-analysis"></a>코드 분석

- 이제 코드 분석이 백그라운드에서 자동으로 실행됩니다. 입력하는 동안 경고가 녹색 물결선으로 표시됩니다. 자세한 내용은 [Visual Studio 2019 Preview 2의 편집기 내 코드 분석](https://devblogs.microsoft.com/cppblog/in-editor-code-analysis-in-visual-studio-2019-preview-2/)을 참조하세요.

- \<mutex> 헤더에서 잘 알려진 표준 라이브러리 형식에 대한 새로운 실험적 ConcurrencyCheck 규칙 자세한 내용은 [Visual Studio 2019의 동시성 코드 분석](https://devblogs.microsoft.com/cppblog/concurrency-code-analysis-in-visual-studio-2019/)을 참조하세요.

- [수명 프로필 검사기](https://herbsutter.com/2018/09/20/lifetime-profile-v1-0-posted/)의 업데이트된 부분 구현은 매달려 있는 포인터 및 참조를 검색합니다. 자세한 내용은 [Visual Studio 2019 Preview 2의 수명 프로필 업데이트](https://devblogs.microsoft.com/cppblog/lifetime-profile-update-in-visual-studio-2019-preview-2/)를 참조하세요.

- C26138, C26810, C26811 및 실험적 규칙 C26800을 포함한 추가 코루틴 관련 검사 자세한 내용은 [Visual Studio 2019의 새 코드 분석 검사: use-after-move 및 코루틴](https://devblogs.microsoft.com/cppblog/new-code-analysis-checks-in-visual-studio-2019-use-after-move-and-coroutine/)을 참조하세요.

## <a name="unit-testing"></a>단위 테스트

관리되는 C++ 테스트 프로젝트 템플릿을 더 이상 사용할 수 없습니다. 기존 프로젝트에서 관리형 C++ 테스트 프레임워크를 사용하여 진행할 수 있습니다. 새 단위 테스트의 경우, Visual Studio에서 템플릿(MSTest, Google Test) 또는 관리형 C# 테스트 프로젝트 템플릿을 제공하는 기본 프레임워크 중 하나를 사용하는 것이 좋습니다.
