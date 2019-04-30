---
title: 구성 요소
ms.date: 04/08/2019
f1_keywords:
- vc-pragma.component
- component_CPP
helpviewer_keywords:
- component pragma
- pragmas, component
ms.assetid: 7b66355e-3201-4c14-8190-f4a2a81a604a
ms.openlocfilehash: 4870860650a39d27639ad18100ba37ba14aa15c0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62366916"
---
# <a name="component"></a>구성 요소

찾아보기 정보 또는 소스 파일 내에서 종속성 정보 컬렉션을 제어합니다.

## <a name="syntax"></a>구문

> **#pragma component( browser,** { **on** | **off** }[**,** **references** [**,** *name* ]] **)** \
> **#pragma component( minrebuild, on** | **off )** \
> **#pragma component( mintypeinfo, on** | **off )**

## <a name="remarks"></a>설명

### <a name="browser"></a>브라우저

수집을 설정하거나 해제할 수 있으며 정보가 수집됨에 따라 특정 이름을 무시하도록 지정할 수 있습니다.

설정 또는 해제를 사용하면 pragma 정방향에서의 찾아보기 정보 수집을 제어합니다. 예를 들어:

```cpp
#pragma component(browser, off)
```

컴파일러에서 찾아보기 정보 수집을 중지합니다.

> [!NOTE]
> 이 pragma 사용 하 여 찾아보기 정보 수집을 켜려면 [찾아보기 정보를 먼저 활성화 해야](../build/reference/building-browse-information-files-overview.md)합니다.

합니다 `references` 유무에 관계 없이 옵션을 사용할 수 있습니다 합니다 *이름* 인수입니다. 하지만 사용 하 여 `references` 없이 *이름* 참조 수집을 해제 하거나 (다른 찾아보기 정보가 계속 수집 되도록). 예를 들어:

```cpp
#pragma component(browser, off, references)
```

컴파일러에서 참조 정보 수집을 중지합니다.

사용 하 여 `references` 사용 하 여 *이름* 하 고 `off` 에 대 한 참조를 방지 *이름* 찾아보기 정보 창에 나타나지 않습니다. 관심 없는 이름 및 형식을 무시하고 찾아보기 정보 파일의 크기를 줄이려면 이 구문을 사용합니다. 예를 들어:

```cpp
#pragma component(browser, off, references, DWORD)
```

이 시점에서 DWORD에 대 한 참조를 무시합니다. 사용 하 여 다시 DWORD에 대 한 참조 수집을 끌 수 있습니다 `on`:

```cpp
#pragma component(browser, on, references, DWORD)
```

에 대 한 참조 수집을 다시 시작 하는 유일한 방법은 이것이 *이름을*;에서 명시적으로 설정 해야 *이름* 해제 있다는입니다.

전처리기 확장 하지 못하도록 *이름을* 주위에 따옴표를 배치 (예: NULL을 0으로)를 확장 합니다.

```cpp
#pragma component(browser, off, references, "NULL")
```

### <a name="minimal-rebuild"></a>최소 다시 빌드

사용 되지 않는 [/Gm (최소 다시 빌드 사용)](../build/reference/gm-enable-minimal-rebuild.md) 기능을 사용 하려면 컴파일러와 저장소를 만들 C++ 종속성 정보를 디스크 공간을 사용 하는 클래스입니다. 디스크 공간을 절약 하려면 사용할 수 있습니다 `#pragma component( minrebuild, off )` 때마다 종속성 정보를 예를 들어 변하지 않는 헤더 파일에 수집할 필요가 없습니다. 삽입 `#pragma component(minrebuild, on)` 후 종속성 컬렉션을 설정 하는 변경 되지 않는 클래스에 백업 합니다.

### <a name="reduce-type-information"></a>형식 정보 감소

`mintypeinfo` 옵션에 지정 된 지역에 대 한 디버깅 정보가 감소 합니다. 이 정보의 양이 상당하므로 .pdb 및 .obj 파일에 영향을 줍니다. mintypeinfo 영역에서 클래스 및 구조체를 디버깅할 수 없습니다. mintypeinfo 옵션을 사용하면 다음 경고가 발생하지 않도록 하는 데 도움이 될 수 있습니다.

```cmd
LINK : warning LNK4018: too many type indexes in PDB "filename", discarding subsequent type information
```

자세한 내용은 참조는 [/Gm (최소 다시 빌드 사용)](../build/reference/gm-enable-minimal-rebuild.md) 컴파일러 옵션입니다.

## <a name="see-also"></a>참고자료

[Pragma 지시문 및 __Pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)