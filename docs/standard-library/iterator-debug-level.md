---
title: _ITERATOR_DEBUG_LEVEL
ms.date: 11/04/2016
f1_keywords:
- _ITERATOR_DEBUG_LEVEL
helpviewer_keywords:
- _ITERATOR_DEBUG_LEVEL
ms.assetid: 718549cd-a9a9-4ab3-867b-aac00b321e67
ms.openlocfilehash: a584fe5a97e251205e750507b27e53e6e7b9a20e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62224196"
---
# <a name="iteratordebuglevel"></a>_ITERATOR_DEBUG_LEVEL

_ITERATOR_DEBUG_LEVEL 매크로 컨트롤 여부 [확인 된 반복기](../standard-library/checked-iterators.md) 및 [디버그 반복기 지원](../standard-library/debug-iterator-support.md) 활성화 됩니다. 이 매크로 대체 하 고 이전의 _SECURE_SCL 및 _HAS_ITERATOR_DEBUGGING 매크로의 기능을 결합 합니다.

## <a name="macro-values"></a>매크로 값

다음 표에서 _ITERATOR_DEBUG_LEVEL 매크로 대 한 가능한 값을 보여 줍니다.

|컴파일 모드|매크로 값|설명|
|----------------------|----------------|-----------------|
|**디버그**|||
||0|확인된 반복기와 반복기 디버깅을 사용하지 않도록 설정합니다.|
||1|확인된 반복기를 사용하도록 설정하고 반복기 디버깅을 사용하지 않도록 설정합니다.|
||2(기본값)|반복기 디버깅을 사용하도록 설정하며 확인된 반복기는 관련이 없습니다.|
|**릴리스**|||
||0(기본값)|확인된 반복기를 사용하지 않도록 설정합니다.|
||1|확인된 반복기를 사용하도록 설정하며 반복기 디버깅은 관련이 없습니다.|

릴리스 모드에서 _ITERATOR_DEBUG_LEVEL 2로 지정 하는 경우 컴파일러는 오류를 생성 합니다.

## <a name="remarks"></a>설명

_ITERATOR_DEBUG_LEVEL 매크로 컨트롤 여부를 [확인 된 반복기](../standard-library/checked-iterators.md) 는 활성화 하 고 디버그 모드에서 든 관계 없이 [디버그 반복기 지원](../standard-library/debug-iterator-support.md) 사용 가능. _ITERATOR_DEBUG_LEVEL 1 또는 2로 정의 된 경우 확인 된 반복기는 컨테이너의 경계를 덮어쓰지 않았는지 확인 합니다. _ITERATOR_DEBUG_LEVEL 0 인 경우 반복기는 확인 하지 않습니다. _ITERATOR_DEBUG_LEVEL을 1로 정의 된 경우 모든 안전 하지 않은 반복기 사용으로 인해 런타임 오류가 발생 하 고 프로그램이 종료 됩니다. _ITERATOR_DEBUG_LEVEL을 2로 정의 된 경우 안전 하지 않은 반복기 하면 디버거를 중단 하는 어설션 및 수 있는 런타임 오류 대화 상자를 사용 합니다.

_ITERATOR_DEBUG_LEVEL 매크로 _SECURE_SCL 및 _HAS_ITERATOR_DEBUGGING 매크로 비슷한 기능을 지원 하므로 있습니다 하지 않을 수 매크로 및 매크로 특정 상황에서 사용할 값입니다. 혼동을 방지 하려면만 _ITERATOR_DEBUG_LEVEL 매크로 사용 하는 것이 좋습니다. 이 표에서 _SECURE_SCL 및 _HAS_ITERATOR_DEBUGGING 기존 코드에서의 다양 한 값에 사용할 해당 _ITERATOR_DEBUG_LEVEL 매크로 값을 설명 합니다.

|**_ITERATOR_DEBUG_LEVEL** |**_SECURE_SCL** |**_HAS_ITERATOR_DEBUGGING**|
|---|---|---|
|0(릴리스 기본값)|0(사용 안 함)|0(사용 안 함)|
|1|1(사용)|0(사용 안 함)|
|2(디버그 기본값)|(관련 없음)|1(디버그 모드에서 사용)|

확인된 반복기에 대한 경고를 사용하지 않도록 설정하는 방법에 대한 자세한 내용은 [_SCL_SECURE_NO_WARNINGS](../standard-library/scl-secure-no-warnings.md)을 참조하세요.

### <a name="example"></a>예제

_ITERATOR_DEBUG_LEVEL 매크로 대 한 값을 지정 하려면 사용을 [/D](../build/reference/d-preprocessor-definitions.md) 컴파일러 옵션을 사용 하 여 또는 명령줄에서 정의 `#define` 전에 C++ 표준 라이브러리 헤더는 원본 파일에 포함 됩니다. 컴파일하는 데 명령줄의 예를 들어 *sample.cpp* 디버그 모드에서 컴파일하고 디버그 반복기 지원을 사용 하려면 _ITERATOR_DEBUG_LEVEL 매크로 정의 지정할 수 있습니다.

`cl /EHsc /Zi /MDd /D_ITERATOR_DEBUG_LEVEL=1 sample.cpp`

소스 파일에서 반복기를 정의하는 표준 라이브러리 헤더 앞에 매크로를 지정합니다.

```cpp
// sample.cpp

#define _ITERATOR_DEBUG_LEVEL 1

#include <vector>

// ...
```

## <a name="see-also"></a>참고자료

[Checked Iterators](../standard-library/checked-iterators.md)<br/>
[Debug Iterator Support](../standard-library/debug-iterator-support.md)<br/>
[안전한 라이브러리: C++ 표준 라이브러리](../standard-library/safe-libraries-cpp-standard-library.md)<br/>
