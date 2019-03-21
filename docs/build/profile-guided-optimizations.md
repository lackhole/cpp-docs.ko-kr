---
title: 프로필 기반 최적화
ms.date: 03/14/2018
helpviewer_keywords:
- profile-guided optimizations
- optimization, profile-guided [C++]
ms.assetid: 2225c307-d3ae-42c1-8345-a5a959d132dc
ms.openlocfilehash: f4e9af0b2e08dfa4082ebe71caf788ed1188ab7b
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57827042"
---
# <a name="profile-guided-optimizations"></a>프로필 기반 최적화

최적화 프로그램이 .exe 또는 .dll 파일의 테스트 실행 데이터를 사용하는 프로필 기반 최적화를 사용하면 출력 파일을 최적화할 수 있습니다. 데이터는 프로그램이 프로덕션 환경에서 수행될 가능성이 있는 방법을 나타냅니다.

프로필 기반 최적화만 x86 또는 x64 네이티브 대상에 제공 됩니다. 프로필 기반 최적화에서 공용 언어 런타임에서 실행 되는 출력 파일에 대 한 제공 되지 않습니다. 혼합된 네이티브 및 관리 되는 코드를 사용 하 여 어셈블리를 생성 하는 경우에 (사용 하 여 합니다 **/clr** 컴파일러 옵션), 네이티브 코드 에서만 프로필 기반 최적화를 사용할 수 없습니다. IDE에서 설정 된 이러한 옵션을 사용 하 여 프로젝트를 빌드 하려는 경우 빌드 오류가 발생 합니다.

> [!NOTE]
> 프로 파일링 테스트 실행에서 수집 되는 정보를 지정 하는 경우 적용에서 되는 최적화를 재정의 **/Ob**하십시오 **/Os**, 또는 **/Ot**합니다. 자세한 내용은 [/Ob (인라인 함수 확장)](reference/ob-inline-function-expansion.md) 하 고 [/Os, /Ot (크기 우선 코드, 속도 우선 코드)](reference/os-ot-favor-small-code-favor-fast-code.md)합니다.

## <a name="steps-to-optimize-your-app"></a>앱을 최적화 하는 단계

프로필 기반 최적화를 사용 하려면 앱을 최적화 하기 위해 다음이 단계를 수행 합니다.

- 사용 하 여 하나 이상의 소스 코드 파일을 컴파일할 [/GL](reference/gl-whole-program-optimization.md)합니다.

   각 모듈을 사용 하 여 빌드한 **/GL** 런타임 동작을 캡처할 프로필 기반 최적화 테스트 실행 중 검사할 수 있습니다. 프로필 기반 최적화 빌드의 모든 모듈을 사용 하 여 컴파일할 필요가 없습니다 **/GL**합니다. 그러나 컴파일된 모듈만 **/GL** 계측 되어 나중에 사용할 수 있는 프로필 기반 최적화 됩니다.

- 사용 하 여 연결 [/LTCG](reference/ltcg-link-time-code-generation.md) 하 고 [/GENPROFILE 또는 /FASTGENPROFILE](reference/genprofile-fastgenprofile-generate-profiling-instrumented-build.md)합니다.

   모두 사용 하 여 **/LTCG** 하 고 **/GENPROFILE** 하거나 **/FASTGENPROFILE** 계측 된 앱이 실행 되는 경우.pgd 파일을 만듭니다. 테스트 실행 데이터가 .pgd 파일에 추가된 후에는 다음 링크 단계(최적화된 이미지 만들기)에 대한 입력으로 사용할 수 있습니다. 지정 하는 경우 **/GENPROFILE**를 추가할 수도 있습니다는 **PGD =**_filename_ 기본값이 아닌 이름이 나.pgd 파일의 위치를 지정 하는 인수입니다. 조합 **/LTCG** 하 고 **/GENPROFILE** 하거나 **/FASTGENPROFILE** 링커 옵션을 사용 되지 않는 대체 **/ltcg: pginstrument** 링커 옵션입니다.

- 응용 프로그램을 프로파일링합니다.

   때마다 프로 파일링 된 EXE 세션이 종료 또는 프로 파일링 된 DLL을 로드 한 *appname*! #.pgc 파일이 만들어집니다. .pgc 파일에는 특정 응용 프로그램 테스트 실행에 대한 정보가 포함됩니다. #은 다른의 수에 따라 증가 하는 1부터 시작 하는 숫자로 *appname*! #.pgc 파일 디렉터리에 있습니다. 테스트 실행이 최적화하려는 시나리오를 나타내지 않는 경우 .pgc 파일을 삭제할 수 있습니다.

   테스트 실행 하는 동안 현재 열려 있는.pgc 파일을 사용 하 여 새.pgc 파일 만들기를 강제할 수 있습니다 합니다 [pgosweep](pgosweep.md) 유틸리티 (예를 들어 경우 테스트 시나리오를 끝 응용 프로그램 종료와 일치 하지 않습니다).

   응용 프로그램 PGO 함수를 직접 호출할 수 있습니다 [PgoAutoSweep](pgoautosweep.md),.pgc 파일 호출 시 프로필 데이터를 캡처할 수 있습니다. 이.pgc 파일에서 캡처된 데이터를 포함 하는 코드를 보다 세부적으로 제어를 제공할 수 있습니다. 이 함수를 사용 하는 방법의 예제를 참조 합니다 [PgoAutoSweep](pgoautosweep.md) 설명서.

   기본적으로 계측 된 빌드를 만들 때 데이터 컬렉션은 빠르게 되지만 완전히 정확 하지 않을 스레드 안전 하지 않은 모드에서 수행 됩니다. 사용 하 여는 **정확한 수치** 인수 **/GENPROFILE** 또는 **/FASTGENPROFILE**, 더 정확 하지만 느린 스레드로부터 안전한 모드에서 데이터 수집을 지정할 수 있습니다. 이 옵션은 사용 되지 않는 설정 하는 경우 사용할 수 있는 데도 [PogoSafeMode](environment-variables-for-profile-guided-optimizations.md#pogosafemode) 환경 변수 또는 사용 되지 않는 **/POGOSAFEMODE** 링커 옵션을 계측 된 빌드를 만들 때.

- 사용 하 여 연결 **/LTCG** 하 고 **/USEPROFILE**합니다.

   둘 다 사용 합니다 **/LTCG** 하 고 [/USEPROFILE](reference/useprofile.md) 최적화 된 이미지를 만드는 링커 옵션. 이 단계에서는 입력으로 .pgd 파일을 사용합니다. 지정 하는 경우 **/USEPROFILE**를 추가할 수도 있습니다는 **PGD =**_filename_ 기본이 아닌 이름 또는.pgd 파일의 위치를 지정 하는 인수입니다. 사용 되지 않는 사용 하 여이 이름을 지정할 수도 있습니다 **/PGD** 링커 옵션입니다. 조합 **/LTCG** 하 고 **/USEPROFILE** 사용 되지 않는 대체 **/ltcg: pgoptimize** 하 고 **/ltcg: pgupdate** 링커 옵션입니다.

최적화된 출력 파일을 만들고 나중에 보다 최적화된 이미지를 만드는 데 추가 프로파일링이 유용한지를 확인할 수 있습니다. 계측된 된 이미지와 해당.pgd 파일을 사용할 수 있는 경우 추가 테스트 실행을 수행 하는 동일한를 사용 하 여 최신.pgd 파일을 사용 하 여 최적화 된 이미지를 다시 작성 **/LTCG** 하 고 **/USEPROFILE** 링커 옵션 .

## <a name="optimizations-performed-by-pgo"></a>PGO에서 수행한 최적화

다음은 프로필 기반 최적화 목록입니다.

- **인라인** -예를 들어 있으면 함수는 호출 함수 B를 자주 함수 B는 상대적으로 작은 경우 하 고 프로필 기반 최적화에서는 함수 A에서에서 B 인라인 함수는

- **가상 호출 추론** -프로필 기반 최적화 대상 함수를 조건부로 실행할 직접 호출을 삽입할 수 있습니다 가상 호출 또는 함수 포인터를 통해 다른 호출에 특정 기능을 자주 대상이 일 경우 및 직접 호출은 인라인 처리할 수 있습니다.

- **레지스터 할당** -더 나은 레지스터 할당의 프로필 데이터 결과 사용 하 여 최적화 합니다.

- **기본 블록 최적화** -기본 블록 최적화에서는 페이지 (위치)의 동일한 집합에 배치 되도록 지정된 된 프레임 내에서 일시적으로 실행 되는 기본 요소를 일반적으로 실행된 합니다. 따라서 사용되는 페이지 수가 최소화되므로 메모리 오버헤드도 최소홥니다.

- **크기/속도 최적화** -속도 대 한 프로그램에서 자주 사용 되는 함수를 최적화할 수 있습니다.

- **함수 레이아웃** 호출 그래프를 기반으로 하며 호출자/호출 수신자 동작을 프로 파일링-동일한 실행 경로를 따르는 경향이 있는 함수가 동일한 섹션에 배치 됩니다.

- **조건부 분기 최적화** -값 프로브를 프로필 기반 최적화에서 switch 문에 지정된 된 값은 다른 값 보다 더 자주 사용 하는 경우를 찾을 수 있습니다.  그런 다음 switch 문에서 이 값을 끌어올 수 있습니다.  더 자주 true가 되는 블록에 따라 if 도는 else 블록이 먼저 배치되도록 최적화 프로그램에서 if/else의 순서를 지정할 수 있는 if/else 명령을 사용하여 동일한 작업을 수행할 수 있습니다.

- **데드 코드 분리** -프로 파일링 중 호출 하지 않은 코드를 섹션 집합의 끝에 추가 되는 별도 섹션으로 이동 합니다. 그러면 이 섹션이 자주 사용되는 페이지에서 효과적으로 유지됩니다.

- **EH 코드 분리** -예외적으로 실행 되는 EH 코드 옮길 수 있습니다는 별도 섹션으로 프로필 기반 최적화 예외 조건 에서만 발생 하는지를 확인할 수 있습니다.

- **메모리 내장** -내장 함수의 확장 내장 함수가 자주 호출 되는지 확인할 수 있으면 더 잘 결정할 수 있습니다. 또한 내장 함수는 이동 또는 복사의 블록 크기에 따라 최적화할 수 있습니다.

Visual Studio 2013을 사용 하는 경우 자동화 된 사용할 수 있습니다 [프로필 기반 최적화 플러그 인](profile-guided-optimization-in-the-performance-and-diagnostics-hub.md) Visual c + + 성능 및 진단 허브를 Visual Studio 내의 최적화 프로세스를 간소화 합니다. 이 플러그 인 Visual Studio의 이후 버전에서 제공 되지 않습니다.

## <a name="next-steps"></a>다음 단계

이러한 환경 변수, 함수 및 프로필 기반 최적화에 사용할 수 있는 도구에 대해 읽어보세요.

[프로필 기반 최적화 환경 변수](environment-variables-for-profile-guided-optimizations.md)<br/>
테스트 시나리오의 런타임 동작을 지정 하려면 이러한 변수를 사용할 수 있습니다. 이러한 사용 되지 않고 있으므로 새 링커 옵션 링커 옵션 환경 변수에서 이동할 수 있도록이 읽습니다.

[PgoAutoSweep](pgoautosweep.md)<br/>
함수를 세분화 된.pgc 파일 데이터 캡처 제어할 수 있도록 앱에 추가할 수 있습니다.

[pgosweep](pgosweep.md)<br/>
.Pgc 파일에 모든 프로필 데이터를 기록 하는 명령줄 유틸리티.pgc 파일을 닫고 새.pgc 파일을 엽니다.

[pgomgr](pgomgr.md)<br/>
.Pgd 파일에 하나 이상의.pgc 파일에서 프로필 데이터를 추가 하는 명령줄 유틸리티입니다.

[방법: 여러 개의 PGO 프로필을 단일 프로필로 병합](how-to-merge-multiple-pgo-profiles-into-a-single-profile.md)<br/>
예가 **pgomgr** 사용 합니다.

## <a name="see-also"></a>참고자료

[추가 MSVC 빌드 도구](reference/c-cpp-build-tools.md)
