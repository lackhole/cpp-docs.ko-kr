---
title: OpenMP 라이브러리 참조
ms.date: 03/20/2019
ms.assetid: a25188c6-edde-43d0-84b5-780e797b08fc
ms.openlocfilehash: 6f4bbeca54bff1fc44a3576362edca9c30926d5a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62362519"
---
# <a name="openmp-library-reference"></a>OpenMP 라이브러리 참조

OpenMP API에서 사용 하는 구문에 대 한 링크를 제공 합니다.

시각적 개체 C++ OpenMP 표준의 구현에는 다음과 같은 구문이 포함 됩니다.

|구문|설명|
|---------------|-----------------|
|[지시문](openmp-directives.md)|OpenMP API에서 사용 되는 지시문에 대 한 링크를 제공 합니다.|
|[절](openmp-directives.md)|OpenMP API에서 사용 하는 절에 대 한 링크를 제공 합니다.|
|[함수](openmp-functions.md)|OpenMP API에서 사용 되는 함수에 대 한 링크를 제공 합니다.|
|[환경 변수](openmp-environment-variables.md)|OpenMP API에서 사용 되는 환경 변수를 제공 합니다.|

시각적 개체 C++ OpenMP에서 런타임 라이브러리 함수는 다음과 같은 라이브러리에 포함 됩니다.

|OpenMP에서 런타임 라이브러리|특성|
|------------------------------|---------------------|
|VCOMP.LIB|다중 스레드, 동적 링크 (VCOMP에 대 한 가져오기 라이브러리입니다. LIB)입니다.|
|VCOMPD.LIB|다중 스레드, 동적 링크 (VCOMPD에 대 한 가져오기 라이브러리입니다. 커버) (디버그)|

컴파일에서 _DEBUG이 정의 하는 경우 `#include omp.h` VCOMPD 소스 코드에 있습니다. LIB 기본 lib, 그렇지 않으면 VCOMP 됩니다. LIB 사용 됩니다.

사용할 수 있습니다 [/NODEFAULTLIB (라이브러리 무시)](../../../build/reference/nodefaultlib-ignore-libraries.md) 기본 lib 제거한 사용자가 선택한 라이브러리를 사용 하 여 명시적으로 연결 합니다.

시각적 개체에서 OpenMP Dll은 C++ 재배포 가능 패키지 디렉터리와 OpenMP를 사용 하는 응용 프로그램과 함께 배포 해야 합니다.

## <a name="see-also"></a>참고자료

[OpenMP](../../../parallel/openmp/openmp-in-visual-cpp.md)