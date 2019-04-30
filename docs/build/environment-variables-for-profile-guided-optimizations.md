---
title: 프로필 기반 최적화 환경 변수
ms.date: 03/14/2018
helpviewer_keywords:
- profile-guided optimizations, environment variables
ms.assetid: f95a6d1e-49a4-4802-a144-092026b600a3
ms.openlocfilehash: 099e57f1ac69223adafe7bec1af4cc3452915e86
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62195275"
---
# <a name="environment-variables-for-profile-guided-optimizations"></a>프로필 기반 최적화 환경 변수

사용 하 여 만든 이미지에서 테스트 시나리오에 영향을 주는 세 개의 환경 변수가 **/ltcg: pgi** 프로필 기반 최적화에 대 한 합니다.

- **PogoSafeMode** 응용 프로그램 프로 파일링에 대 한 빠른 모드 또는 안전 모드를 사용할지 여부를 지정 합니다.

- **VCPROFILE_ALLOC_SCALE** 프로파일러 사용에 대 한 추가 메모리를 추가 합니다.

- **VCPROFILE_PATH** .pgc 파일에 사용할 폴더를 지정할 수 있습니다.

**PogoSafeMode 및 VCPROFILE_ALLOC_SCALE 환경 변수는 Visual Studio 2015부터 사용 되지 않습니다.** 링커 옵션 [/GENPROFILE 또는 /FASTGENPROFILE](reference/genprofile-fastgenprofile-generate-profiling-instrumented-build.md) 하 고 [/USEPROFILE](reference/useprofile.md) 이러한 환경 변수로 서 동일한 링커 동작을 지정 합니다.

## <a name="pogosafemode"></a>PogoSafeMode

이 환경 변수를 사용 하는 사용 되지 않습니다. 사용 하 여는 **정확한 수치** 또는 **NOEXACT** 인수를 **/GENPROFILE** 또는 **/FASTGENPROFILE** 이 동작을 제어 합니다.

해제 하거나 설정 합니다 **PogoSafeMode** x86 응용 프로그램 프로 파일링에 대 한 빠른 모드 또는 안전 모드를 사용할지 여부를 지정 하도록 환경 변수 시스템입니다.

프로필 기반 최적화 PGO ()는 두 가지 가능한 모드는 프로 파일링 단계: *고속 모드* 하 고 *안전 모드*합니다. 프로 파일링 하는 것은 빠른 모드에서를 사용 합니다 **INC** 데이터 카운터를 늘리려면 명령입니다. 합니다 **INC** 명령은 빠르지만 스레드로부터 안전한 아닙니다. 프로 파일링 하는 것은 안전 모드에서를 사용 합니다 **LOCK INC** 데이터 카운터를 늘리려면 명령입니다. **LOCK INC** 명령에 동일한 기능을 합니다 **INC** 명령에는 스레드로부터 안전 하며 보다 느립니다 합니다 **INC** 명령 합니다.

기본적으로 PGO 프로 파일링은 빠른 모드로 작동 합니다. **PogoSafeMode** 는 안전 모드를 사용 하려는 경우에 필요 합니다.

안전 모드에서 PGO 프로 파일링 실행을 사용 해야 합니다 하거나 환경 변수 **PogoSafeMode** 또는 링커 스위치 **/PogoSafeMode**시스템에 따라 합니다. 수행 하는 경우 x64에서 프로 파일링 컴퓨터 링커 스위치를 사용 해야 합니다. 수행 하는 경우 x86에서 프로 파일링 컴퓨터 링커를 사용할 수 있습니다 전환 하거나 설정 합니다 **PogoSafeMode** 최적화 프로세스를 시작 하기 전에 값을 환경 변수입니다.

### <a name="pogosafemode-syntax"></a>PogoSafeMode 구문

> **set PogoSafeMode**[**=**_value_]

설정할 **PogoSafeMode** 안전 모드를 사용 하도록 설정 하려면 값으로. 이전 값을 지우고 다시 고속 모드를 사용 하도록 설정 하는 값 없이 설정 합니다.

## <a name="vcprofileallocscale"></a>VCPROFILE_ALLOC_SCALE

이 환경 변수를 사용 하는 사용 되지 않습니다. 사용 하 여는 **MEMMIN** 및 **MEMMAX** 인수 **/GENPROFILE** 또는 **/FASTGENPROFILE** 이 동작을 제어 합니다.

수정 된 **VCPROFILE_ALLOC_SCALE** 프로필 데이터를 보관에 할당 된 메모리 양을 변경 하려면 환경 변수입니다. 드문 경우에서 충분 한 메모리를 지원 하 게 되지 테스트 시나리오를 실행 하는 경우 프로필 데이터를 수집 합니다. 이러한 경우에 설정 하 여 메모리 크기를 늘릴 수 있습니다 **VCPROFILE_ALLOC_SCALE**합니다. 메모리가 부족 하 여 있다고 표시 하는 테스트 실행 도중 오류 메시지가 표시 되 면 더 큰 값을 할당 **VCPROFILE_ALLOC_SCALE**테스트 실행의 메모리 부족 오류 없이 완료 될 때까지, 합니다.

### <a name="vcprofileallocscale-syntax"></a>VCPROFILE_ALLOC_SCALE 구문

> **set VCPROFILE_ALLOC_SCALE**[__=__*scale_value*]

합니다 *scale_value* 매개 변수는 테스트 시나리오를 실행 하기 위한 메모리의 양을 배율 인수입니다.  기본값은 1입니다. 예를 들어 명령줄이 배율 인수를 2로 설정합니다.

`set VCPROFILE_ALLOC_SCALE=2`

## <a name="vcprofilepath"></a>VCPROFILE_PATH

사용 된 **VCPROFILE_PATH** .pgc 파일을 만들 디렉터리를 지정 하려면 환경 변수입니다. 기본적으로 프로 파일링 중인 이진 형식으로 동일한 디렉터리에.pgc 파일이 만들어집니다. 그러나 없으면 이진 파일의 절대 경로 이진 빌드 했던 다른 컴퓨터에서 프로필 시나리오를 실행 하는 경우에 해당 될 수 있으므로, 설정할 수 있습니다 **VCPROFILE_PATH** 대상 컴퓨터에 있는 경로입니다.

### <a name="vcprofilepath-syntax"></a>VCPROFILE_PATH 구문

> **set VCPROFILE_PATH**[**=**_path_]

설정 된 *경로* .pgc 파일을 추가 하는 디렉터리 경로에 매개 변수입니다. 예를 들어 명령줄이 C:\profile에 폴더를 설정 합니다.

`set VCPROFILE_PATH=c:\profile`

## <a name="see-also"></a>참고자료

[프로필 기반 최적화](profile-guided-optimizations.md)<br/>
[/GENPROFILE 및 /fastgenprofile은](reference/genprofile-fastgenprofile-generate-profiling-instrumented-build.md)<br/>
[/USEPROFILE](reference/useprofile.md)<br/>
