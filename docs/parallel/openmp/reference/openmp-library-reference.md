---
title: OpenMP 라이브러리 참조
ms.date: 07/30/2019
ms.assetid: a25188c6-edde-43d0-84b5-780e797b08fc
ms.openlocfilehash: c78c2677741714ab48d49a4443ad753369ec4500
ms.sourcegitcommit: 725e86dabe2901175ecc63261c3bf05802dddff4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/31/2019
ms.locfileid: "68682587"
---
# <a name="openmp-library-reference"></a>OpenMP 라이브러리 참조

OpenMP API에서 사용되는 구문에 대한 링크를 제공 합니다.

OpenMP 표준의 Visual C++ 구현에는 다음 구문이 포함 됩니다.

|구문|설명|
|---------------|-----------------|
|[지시문](openmp-directives.md)|OpenMP API에서 사용되는 지시문에 대한 링크를 제공 합니다.|
|[절](openmp-clauses.md)|OpenMP API에서 사용되는 절에 대한 링크를 제공 합니다.|
|[함수](openmp-functions.md)|OpenMP API에서 사용되는 함수에 대한 링크를 제공 합니다.|
|[환경 변수](openmp-environment-variables.md)|OpenMP API에서 사용되는 환경 변수에 대한 링크를 제공 합니다.|

Visual C++ OpenMP 런타임 라이브러리 함수는 다음 라이브러리에 포함 되어 있습니다.

|OpenMP 런타임 라이브러리|특징|
|------------------------------|---------------------|
|VCOMP.LIB|다중 스레드, 동적 링크 (VCOMP.LIB 라이브러리를 임포트).|
|VCOMPD.LIB|다중 스레드, 동적 링크 (VCOMPD.LIB 라이브러리를 임포트) LID) (디버그)|

_Debug가 컴파일에서 정의되어 있고 `#include <omp.h>`가 소스코드에 있는 경우 VCOMPD.LIB가 기본 라이브러리가 되고, 그렇지 않은 경우 VCOMP.LIB가 사용 됩니다.

[/NODEFAULTLIB (라이브러리 무시)](../../../build/reference/nodefaultlib-ignore-libraries.md)를 사용하여 기본 라이브러리를 제거하고 원하는 라이브러리와 명시적으로 연결할 수 있습니다.

OpenMP Dll은 Visual C++ 재배포 패키지 디렉터리에 있으며 OpenMP를 사용하는 응용 프로그램과 함께 배포해야 합니다.

## <a name="see-also"></a>참고자료

[OpenMP](../../../parallel/openmp/openmp-in-visual-cpp.md)
