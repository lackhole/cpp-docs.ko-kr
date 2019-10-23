---
title: OpenMP 라이브러리 참조
ms.date: 07/30/2019
ms.assetid: a25188c6-edde-43d0-84b5-780e797b08fc
ms.openlocfilehash: c63ae5ba7f04d8ee6bd02418792804373fa71e6b
ms.sourcegitcommit: 170f5de63b0fec8e38c252b6afdc08343f4243a6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72348219"
---
# <a name="openmp-library-reference"></a>OpenMP 라이브러리 참조

OpenMP API에서 사용되는 구문에 대한 링크를 제공합니다.

OpenMP 표준의 Visual C++ 구현에는 다음 구문이 포함됩니다.

|구문|설명|
|---------------|-----------------|
|[지시문](openmp-directives.md)|OpenMP API에서 사용 되는 지시문에 대 한 링크를 제공 합니다.|
|[절](openmp-clauses.md)|OpenMP API에서 사용 되는 절에 대 한 링크를 제공 합니다.|
|[함수](openmp-functions.md)|OpenMP API에서 사용 되는 함수에 대 한 링크를 제공 합니다.|
|[환경 변수](openmp-environment-variables.md)|OpenMP API에서 사용 되는 환경 변수에 대 한 링크를 제공 합니다.|

Visual C++ OpenMP 런타임 라이브러리 함수는 다음 라이브러리에 포함 되어 있습니다.

|OpenMP 런타임 라이브러리|특징|
|------------------------------|---------------------|
|VCOMP. LIB|다중 스레드, 동적 링크 (VCOMP 용 가져오기 라이브러리) LIB).|
|VCOMPD. LIB|다중 스레드, 동적 링크 (VCOMPD 용 가져오기 라이브러리) LID) (디버그)|

_DEBUG가 컴파일에서 정의 되 고 `#include <omp.h>`이 소스 코드에 있는 경우 VCOMPD입니다. LIB는 기본 lib가 됩니다 (그렇지 않은 경우 VCOMP). LIB가 사용 됩니다.

[/Nodefaultlib (라이브러리 무시)](../../../build/reference/nodefaultlib-ignore-libraries.md) 를 사용 하 여 기본 lib를 제거 하 고 원하는 lib와 명시적으로 연결할 수 있습니다.

OpenMP Dll은 Visual C++ 재배포 가능 디렉터리에 있으며 openmp를 사용 하는 응용 프로그램과 함께 배포 해야 합니다.

## <a name="see-also"></a>참조

[OpenMP](../../../parallel/openmp/openmp-in-visual-cpp.md)
