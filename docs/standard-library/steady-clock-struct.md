---
title: steady_clock 구조체
ms.date: 05/22/2018
f1_keywords:
- chrono/std::chrono::steady_clock
ms.assetid: 970d12ec-fc80-4391-a2f7-b57b2aec668d
ms.openlocfilehash: 19e9f5c4dcfc7306b989605894e9a0787e0920ff
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62412399"
---
# <a name="steadyclock-struct"></a>steady_clock 구조체

나타냅니다는 *안정적인* 시계입니다.

## <a name="syntax"></a>구문

```cpp
struct steady_clock;
```

## <a name="remarks"></a>설명

Windows에 온 `steady_clock` 래핑하는 `QueryPerformanceCounter` 함수.

`now`에 대한 첫 번째 호출에서 반환되는 값이 항상 `now`에 대한 순차적 호출에서 반환되는 값보다 작거나 같을 경우 클록은 *단조*입니다. 클록이 *단조*이고 클록 틱 간 시간이 지속적이면 해당 클록은 *지속*입니다.

`high_resolution_clock` 에 대 한 typedef `steady_clock`합니다.

### <a name="public-typedefs"></a>공용 typedefs

|이름|설명|
|----------|-----------------|
|`steady_clock::duration`|에 대 한 동의어 `nanoseconds`에 정의 된 \<chrono >.|
|`steady_clock::period`|에 대 한 동의어 `nano`에 정의 된 \<비율 >.|
|`steady_clock::rep`|에 대 한 동의어 **긴** **긴**의 포함 된 인스턴스화에서 클록 틱 수를 나타내는 데 사용 되는 형식을 `duration`합니다.|
|`steady_clock::time_point`|`chrono::time_point<steady_clock>`의 동의어입니다.|

## <a name="public-functions"></a>공용 함수

|함수|설명|
|--------------|-----------------|
|`now`|반환 된 현재 시간을 `time_point` 값입니다.|

## <a name="public-constants"></a>공용 상수

|이름|설명|
|----------|-----------------|
|`steady_clock::is_steady`|보유 **true**합니다. `steady_clock`은 *지속*입니다.|

## <a name="requirements"></a>요구 사항

**헤더:** \<chrono >

**네임스페이스:** std::chrono

## <a name="see-also"></a>참고자료

- [헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)
- [\<chrono>](../standard-library/chrono.md)
- [system_clock 구조체](../standard-library/system-clock-structure.md)
