---
title: section
ms.date: 11/04/2016
f1_keywords:
- section_CPP
- vc-pragma.section
helpviewer_keywords:
- pragmas, section
- section pragma
ms.assetid: c67215e9-2c4a-4b0f-b691-2414d2e2d96f
ms.openlocfilehash: 41479d7d8767438d0e59fbe6beb7e435459dcb1b
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59023245"
---
# <a name="section"></a>section

.obj 파일에서 섹션을 만듭니다.

## <a name="syntax"></a>구문

```
#pragma section( "section-name" [, attributes] )
```

## <a name="remarks"></a>설명

의미 *세그먼트* 하 고 *섹션* 이 항목에서 서로 바꿀 수 있습니다.

섹션이 정의되면 컴파일의 나머지 단계에서 유효한 상태로 유지됩니다. 그러나 사용 해야 합니다 [__declspec(allocate)](../cpp/allocate.md) 또는 아무 것도 섹션에 배치 됩니다.

*섹션 이름* 는 필수 매개 변수 섹션의 이름입니다. 이 이름은 모든 표준 섹션 이름과 충돌하지 않아야 합니다. 참조 [/section](../build/reference/section-specify-section-attributes.md) 섹션을 만들 때 사용 하지 않아야 하는 이름의 목록에 대 한 합니다.

*특성* 하나 이상의 쉼표로 구분 된 특성의 섹션에 할당 하려는 구성 되는 선택적 매개 변수입니다. 가능한 *특성* 됩니다.

|특성|설명|
|-|-|
|**read**|데이터에 대한 읽기 작업을 허용합니다.|
|**write**|데이터에 대한 쓰기 작업을 허용합니다.|
|**execute**|코드가 실행될 수 있도록 합니다.|
|**shared**|이미지를 로드하는 모든 프로세스에서 섹션을 공유합니다.|
|**nopage**|섹션을 페이징할 수 없는 것으로 표시합니다. Win32 장치 드라이버에 유용합니다.|
|**nocache**|섹션을 캐시할 수 없는 것으로 표시합니다. Win32 장치 드라이버에 유용합니다.|
|**discard**|섹션을 삭제할 수 있는 것으로 표시합니다. Win32 장치 드라이버에 유용합니다.|
|**remove**|해당 섹션을 표시 하지 메모리 상주;로 가상 장치 드라이버 (V*x*D)만 합니다.|

특성을 지정하지 않으면 섹션이 read 및 write 특성을 갖게 됩니다.

## <a name="example"></a>예제

다음 예제에서 첫 번째 명령은 섹션과 해당 특성을 식별합니다. 정수 `j`는 `mysec` 로 선언되지 않았기 때문에 `__declspec(allocate)`에 삽입되지 않습니다. `j`는 데이터 섹션으로 이동합니다. 정수 `i`는 `mysec` 저장소 클래스 특성의 결과로 `__declspec(allocate)`로 이동합니다.

```cpp
// pragma_section.cpp
#pragma section("mysec",read,write)
int j = 0;

__declspec(allocate("mysec"))
int i = 0;

int main(){}
```

## <a name="see-also"></a>참고자료

[Pragma 지시문 및 __Pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)