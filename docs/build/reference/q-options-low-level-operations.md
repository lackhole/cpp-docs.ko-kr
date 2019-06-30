---
title: /Q 옵션(하위 수준 작업)
ms.date: 1/23/2018
f1_keywords:
- /q
helpviewer_keywords:
- Q compiler option [C++]
- -Q compiler option [C++]
- /Q compiler option [C++]
ms.openlocfilehash: 5bbb63b4f437f8aefd5c84c1c1c4bd20bdb965cb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62319397"
---
# <a name="q-options-low-level-operations"></a>/Q 옵션(하위 수준 작업)

**/Q** 컴파일러 옵션을 사용하여 다음과 같은 저수준 컴파일러 작업을 수행 할 수 있습니다.

- [/Qfast_transcendentals (빠른 초월수 강제 적용)](qfast-transcendentals-force-fast-transcendentals.md): 빠른 초월수를 생성합니다.

- [/Qifist (_ftol 사용)](qifist-suppress-ftol.md): 부동 소수점 형식에서 정수 형식으로 변환해야 할 때 `_ftol`을 사용하지 않습니다. (x86 전용)

- [/Qimprecise_fwaits (Try 블록내의 fwait 제거)](qimprecise-fwaits-remove-fwaits-inside-try-blocks.md): `try` 블록 내에 있는 `fwait` 명령을 제거합니다.

- [/Qpar (자동 병렬화 도우미)](qpar-auto-parallelizer.md): [#pragma loop()](../../preprocessor/loop.md) 지시문으로 표시되는 루프의 자동 병렬화를 사용하도록 설정합니다.

- [/Qpar-report (자동 병렬화 보고 수준)](qpar-report-auto-parallelizer-reporting-level.md): 자동 병렬화 수준을 보고하도록 설정합니다.

- [/Qsafe_fp_loads](qsafe-fp-loads.md): 부동 소수점 레지스터 로드 및 메모리와 MMX 레지스터 사이의 이동에 대한 최적화를 억제합니다.

- [/Qspectre](qspectre.md): 특정 스펙터 보안 취약성을 완화하는 지침을 생성합니다.

- [/Qvec-report (자동 벡터화 보고 수준)](qvec-report-auto-vectorizer-reporting-level.md): 자동 벡터화에 수준을 보고하도록 설정합니다.

## <a name="see-also"></a>참고자료

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
