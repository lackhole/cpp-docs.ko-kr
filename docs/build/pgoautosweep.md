---
title: PgoAutoSweep
ms.date: 03/14/2018
f1_keywords:
- PgoAutoSweep
- PogoAutoSweepA
- PogoAutoSweepW
ms.openlocfilehash: 2d9804e5ce90663d44ac389ab4f71d10290e6470
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62295337"
---
# <a name="pgoautosweep"></a>PgoAutoSweep

`PgoAutoSweep` 파일에 현재 프로필 카운터 정보를 저장 하 고 카운터를 다시 설정 합니다. 함수를 사용 하 여 나중에 사용할 최적화 빌드에서.pgc 파일에 실행 중인 프로그램에서 모든 프로필 데이터를 쓸 학습 하는 프로필 기반 최적화 중입니다.

## <a name="syntax"></a>구문

```cpp
void PgoAutoSweep(const char* name);    // ANSI/MBCS
void PgoAutoSweep(const wchar_t* name); // UNICODE
```

### <a name="parameters"></a>매개 변수

*name*<br/>
저장 된.pgc 파일을 식별 하는 문자열입니다.

## <a name="remarks"></a>설명

호출할 수 있습니다 `PgoAutoSweep` 응용 프로그램에서 저장 하 고 응용 프로그램 실행 중 언제 든 지 프로필 데이터를 다시 설정 합니다. 계측된 된 빌드에 `PgoAutoSweep` 현재 프로 파일링 데이터를 캡처, 파일에서 저장 및 프로필 카운터 다시 설정 합니다. 호출에 해당 하는 것은 [pgosweep](pgosweep.md) 실행 파일의 특정 지점에서 명령을 합니다. 최적화 된 빌드에 `PgoAutoSweep` 는 작동 하지 않습니다.

라는 파일에 저장 된 프로필 카운터 데이터를 놓입니다 *base_name*-*이름*! *값*.pgc, 여기서 *base_name* 실행 파일의 기본 이름인 *이름* 에 전달 되는 매개 변수 `PgoAutoSweep`, 및 *값* 일반적으로 증가 하는 숫자, 파일 이름 충돌을 방지 하는 고유 값이입니다.

만든.pgc 파일 `PgoAutoSweep` .pgd 파일로 최적화 된 실행 파일을 만드는 데 사용할에 병합 해야 합니다. 사용할 수는 [pgomgr](pgomgr.md) 병합을 수행 하는 명령입니다.

사용 하 여 최적화 빌드하는 동안 병합된.pgd 파일의 이름을 링커에 전달할 수는 **PGD =**_filename_ 인수를 [/USEPROFILE](reference/useprofile.md) 링커 옵션 또는 사용 되지 않는 **/PGD** 링커 옵션입니다. 라는 파일에.pgc 파일을 병합 하는 경우 *base_name*.pgd를 필요가 없습니다 명령줄에서 파일 이름을 지정 하는 링커 기본적으로이 파일 이름을 선택 하기 때문에 있습니다.

`PgoAutoSweep` 함수 계측 된 빌드를 만들 때 지정한 스레드로부터의 안전성 설정이 유지 관리 합니다. 기본 설정을 사용 하거나 지정 하는 경우는 **NOEXACT** 인수를 [/GENPROFILE 또는 /FASTGENPROFILE]() 링커 옵션을 호출 `PgoAutoSweep` 는 스레드로부터 안전 하지 않습니다. 합니다 **EXACT** 인수 만듭니다 스레드로부터 안전 하 고 더 정확 하지만 느린 계측 된 실행 파일입니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|`PgoAutoSweep`|\<pgobootrun.h>|

실행 파일에 연결 된 라이브러리 pgobootrun.lib 파일을 포함 해야 합니다. 이 파일은 지원 되는 각 아키텍처에 대해 VC 라이브러리 디렉터리에서 Visual Studio 설치에 포함 됩니다.

## <a name="example"></a>예제

사용 하 여 아래 예제에서는 `PgoAutoSweep` 두를 만들려고 합니다. 실행 하는 동안 여러 시점에서 PGC 파일입니다. 될 때까지 런타임 동작을 설명 하는 데이터를 포함 하는 첫 번째 `count` 가 3, 두 번째 응용 프로그램 종료 직전까지이 시점 이후에 수집 된 데이터를 포함 합니다.

```cpp
// pgoautosweep.cpp
// Compile by using: cl /c /GL /W4 /EHsc /O2 pgoautosweep.cpp
// Link to instrument: link /LTCG /genprofile pgobootrun.lib pgoautosweep.obj
// Run to generate data: pgoautosweep
// Merge data by using command line pgomgr tool:
// pgomgr /merge pgoautosweep-func1!1.pgc pgoautosweep-func2!1.pgc pgoautosweep.pgd
// Link to optimize: link /LTCG /useprofile pgobootrun.lib pgoautosweep.obj

#include <iostream>
#include <windows.h>
#include <pgobootrun.h>

void func2(int count)
{
    std::cout << "hello from func2 " << count << std::endl;
    Sleep(2000);
}

void func1(int count)
{
    std::cout << "hello from func1 " << count << std::endl;
    Sleep(2000);
}

int main()
{
    int count = 10;
    while (count--)
    {
        if (count < 3)
            func2(count);
        else
        {
            func1(count);
            if (count == 3)
            {
                PgoAutoSweep("func1");
            }
        }
    }
    PgoAutoSweep("func2");
}
```

개발자 명령 프롬프트에서이 명령을 사용 하 여 개체 파일에 코드를 컴파일하십시오.

`cl /c /GL /W4 /EHsc /O2 pgoautosweep.cpp`

그런 다음이 명령을 사용 하 여 학습을 위한 계측된 된 빌드를 생성 합니다.

`link /LTCG /genprofile pgobootrun.lib pgoautosweep.obj`

학습 데이터를 캡처하기 위해 계측 된 실행 파일을 실행 합니다. 에 대 한 호출으로 데이터 출력 `PgoAutoSweep` pgoautosweep func1 라는 파일에 저장 됩니다! 1.pgc 및 pgoautosweep func2! 1.pgc 합니다. 프로그램의 출력은 실행 될 때 다음과 같이 표시 됩니다.

```Output
hello from func1 9
hello from func1 8
hello from func1 7
hello from func1 6
hello from func1 5
hello from func1 4
hello from func1 3
hello from func2 2
hello from func2 1
hello from func2 0
```

실행 하 여 프로필 교육 데이터베이스에 저장된 된 데이터를 병합 합니다 **pgomgr** 명령:

`pgoautosweep-func1!1.pgc pgoautosweep-func2!1.pgc`

이 명령의 출력이 같습니다.

```Output
Microsoft (R) Profile Guided Optimization Manager 14.13.26128.0
Copyright (C) Microsoft Corporation. All rights reserved.

Merging pgoautosweep-func1!1.pgc
pgoautosweep-func1!1.pgc: Used  3.8% (22304 / 589824) of total space reserved.  0.0% of the counts were dropped due to overflow.
Merging pgoautosweep-func2!1.pgc
pgoautosweep-func2!1.pgc: Used  3.8% (22424 / 589824) of total space reserved.  0.0% of the counts were dropped due to overflow.
```

이제 최적화 된 빌드를 생성 하려면이 학습 데이터를 사용할 수 있습니다. 이 명령을 사용 하 여 최적화 된 실행 파일을 빌드합니다.

`link /LTCG /useprofile pgobootrun.lib pgoautosweep.obj`

```Output
Microsoft (R) Incremental Linker Version 14.13.26128.0
Copyright (C) Microsoft Corporation.  All rights reserved.

Merging pgoautosweep!1.pgc
pgoautosweep!1.pgc: Used  3.9% (22904 / 589824) of total space reserved.  0.0% of the counts were dropped due to overflow.
  Reading PGD file 1: pgoautosweep.pgd
Generating code

0 of 0 ( 0.0%) original invalid call sites were matched.
0 new call sites were added.
294 of 294 (100.00%) profiled functions will be compiled for speed
348 of 1239 inline instances were from dead/cold paths
294 of 294 functions (100.0%) were optimized using profile data
16870 of 16870 instructions (100.0%) were optimized using profile data
Finished generating code
```

## <a name="see-also"></a>참고자료

[프로필 기반 최적화](profile-guided-optimizations.md)<br/>
[pgosweep](pgosweep.md)<br/>
