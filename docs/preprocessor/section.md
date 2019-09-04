---
title: 섹션 pragma
ms.date: 08/29/2019
f1_keywords:
- section_CPP
- vc-pragma.section
helpviewer_keywords:
- pragmas, section
- section pragma
ms.assetid: c67215e9-2c4a-4b0f-b691-2414d2e2d96f
ms.openlocfilehash: 47ae2ff2503317e937e2b3a497357afbd5522a64
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70216604"
---
# <a name="section-pragma"></a>섹션 pragma

.obj 파일에서 섹션을 만듭니다.

## <a name="syntax"></a>구문

> **#pragma 섹션 (** "*섹션-이름*" [ **,** *특성* ] **)**

## <a name="remarks"></a>설명

이 문서에서 *세그먼트* 와 *섹션* 은 동일한 의미를 갖습니다.

섹션이 정의되면 컴파일의 나머지 단계에서 유효한 상태로 유지됩니다. 그러나 [__declspec (allocate)](../cpp/allocate.md)를 사용 하거나 섹션에 아무 것도 배치 하지 않아야 합니다.

*섹션* 이름은 섹션 이름이 되는 필수 매개 변수입니다. 이 이름은 모든 표준 섹션 이름과 충돌하지 않아야 합니다. 섹션을 만들 때 사용할 수 없는 이름 목록은 [/SECTION](../build/reference/section-specify-section-attributes.md) 를 참조 하세요.

*특성* 은 섹션에 할당할 하나 이상의 쉼표로 구분 된 특성으로 구성 된 선택적 매개 변수입니다. 가능한 *특성* 은 다음과 같습니다.

|특성|Description|
|-|-|
|**read**|데이터에 대한 읽기 작업을 허용합니다.|
|**write**|데이터에 대한 쓰기 작업을 허용합니다.|
|**execute**|코드가 실행될 수 있도록 합니다.|
|**shared**|이미지를 로드하는 모든 프로세스에서 섹션을 공유합니다.|
|**nopage**|섹션을 페이징할 수 없는 것으로 표시 합니다. Win32 장치 드라이버에 유용 합니다.|
|**nocache**|섹션을 캐시할 수 없음으로 표시 합니다. Win32 장치 드라이버에 유용 합니다.|
|**discard**|섹션을 삭제 가능한로 표시 합니다. Win32 장치 드라이버에 유용 합니다.|
|**remove**|섹션을 메모리 상주 하지 않는 것으로 표시 합니다. 가상 장치 드라이버 (V*x*D)에만 해당 됩니다.|

특성을 지정 하지 않는 경우 섹션에는 **읽기** 및 **쓰기** 특성이 있습니다.

## <a name="example"></a>예제

이 예제에서 첫 번째 섹션 pragma는 섹션과 해당 특성을 식별 합니다. 정수 `j` 는를 사용 하 여 `mysec` `__declspec(allocate)`선언 되지 않았으므로에 배치 되지 않습니다. 대신, `j` 데이터 섹션으로 이동 합니다. 정수 `i`는 `mysec` 스토리지 클래스 특성의 결과로 `__declspec(allocate)`로 이동합니다.

```cpp
// pragma_section.cpp
#pragma section("mysec",read,write)
int j = 0;

__declspec(allocate("mysec"))
int i = 0;

int main(){}
```

## <a name="see-also"></a>참고자료

[Pragma 지시문 및 __pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
