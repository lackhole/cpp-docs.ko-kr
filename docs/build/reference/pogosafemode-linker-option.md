---
title: / POGOSAFEMODE (스레드 안전 모드에서 PGO 실행)
ms.date: 03/14/2018
f1_keywords:
- POGOSAFEMODE
ms.openlocfilehash: bbb328bf67d7823305a43f1d61252747cf5ea29e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62319722"
---
# <a name="pogosafemode-run-pgo-in-thread-safe-mode"></a>/ POGOSAFEMODE (스레드 안전 모드에서 PGO 실행)

**Visual Studio 2015부터 /POGOSAFEMODE 옵션 되지**합니다. 사용 된 [/GENPROFILE: 정확한](genprofile-fastgenprofile-generate-profiling-instrumented-build.md) 및 **/GENPROFILE:NOEXACT** 대신 옵션입니다. 합니다 **/POGOSAFEMODE** 링커 옵션 (PGO) 프로필 기반 최적화 중 프로필 데이터 캡처 교육 실행에 대 한 스레드 안전 모드를 사용 하 여 계측 된 빌드 만들어지도록 지정 합니다.

## <a name="syntax"></a>구문

> **/POGOSAFEMODE**

## <a name="remarks"></a>설명

프로필 기반 최적화 PGO ()는 두 가지 가능한 모드는 프로 파일링 단계: *고속 모드* 하 고 *안전 모드*합니다. 프로 파일링 모드에 있으면 빠른 데이터 카운터를 늘리려면 증분 명령을 사용 합니다. 증분 명령은 빠르지만 스레드로부터 안전한 아닙니다. 프로 파일링 하는 것은 안전 모드로 때 데이터 카운터를 늘리려면 연동 증분 명령을 사용 합니다. 이 명령은 기능이 같은 증분 명령에 이며 스레드로부터 안전 하지만 느립니다.

합니다 **/POGOSAFEMODE** 안전 모드를 사용 하 여 계측 된 빌드를 설정 하는 옵션입니다. 이 옵션은만 때 사용 되는 사용 되지 않는 [/ltcg: pginstrument](ltcg-link-time-code-generation.md) PGO 계측 링커 단계를 지정 합니다.

기본적으로 PGO 프로 파일링은 빠른 모드로 작동 합니다. **/ POGOSAFEMODE** 는 안전 모드를 사용 하려는 경우에 필요 합니다.

안전 모드에서 PGO 프로 파일링을 실행 하려면 하나를 사용 해야 **/GENPROFILE: 정확한** (기본 설정), 환경 변수를 사용 하거나 [PogoSafeMode](../environment-variables-for-profile-guided-optimizations.md) 링커 스위치 또는 **/POGOSAFEMODE**시스템에 따라 합니다. 수행 하는 경우 x64에서 프로 파일링 컴퓨터 링커 스위치를 사용 해야 합니다. 수행 하는 경우 x86에서 프로 파일링 컴퓨터 링커 스위치를 사용 하거나 PGO 계측 프로세스를 시작 하기 전에 환경 변수 값으로 정의할 수 있습니다.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. 선택 된 **구성 속성** > **링커** > **최적화** 속성 페이지.

1. 에 **링크 타임 코드 생성** 속성인 선택 **프로필 기반 최적화-계측 (/: pginstrument)** 합니다.

1. 선택 된 **구성 속성** > **링커** > **명령줄** 속성 페이지.

1. 입력 된 **/POGOSAFEMODE** 옵션에 **추가 옵션** 상자입니다. **확인**을 선택하여 변경 내용을 저장합니다.

### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[/GENPROFILE 및 /fastgenprofile은](genprofile-fastgenprofile-generate-profiling-instrumented-build.md)<br/>
[/LTCG](ltcg-link-time-code-generation.md)<br/>
[프로필 기반 최적화](../profile-guided-optimizations.md)<br/>
[프로필 기반 최적화 환경 변수](../environment-variables-for-profile-guided-optimizations.md)<br/>
