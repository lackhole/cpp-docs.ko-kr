---
title: SEGMENT
ms.date: 08/30/2018
f1_keywords:
- SEGMENT
helpviewer_keywords:
- SEGMENT directive
ms.assetid: e6f68367-6714-4f06-a79c-edfa88014430
ms.openlocfilehash: f37be47b92a71e20821cd1e40f8cf1350dfedaff
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62210377"
---
# <a name="segment"></a>SEGMENT

호출 프로그램 세그먼트를 정의 *이름을* 세그먼트 특성이

## <a name="syntax"></a>구문

> *이름을* 세그먼트 [[읽기 전용]] [[*맞춤*]] [[*결합*]] [[*사용 하 여*]] [[*특징*]] 별칭 (*문자열*) [['*클래스*']]<br/>
> *statements*<br/>
> *name* ENDS

#### <a name="parameters"></a>매개 변수

*align(C++)*<br/>
범위는 세그먼트의 시작 주소를을 선택할 수 있는 메모리 주소입니다. 맞춤 유형 중 하나를 수 있습니다.

|유형 맞춤|시작 주소|
|----------------|----------------------|
|**BYTE**|다음 사용 가능한 바이트 주소입니다.|
|**WORD**|다음 사용 가능한 word 주소 (단어 당 2 바이트)입니다.|
|**DWORD**|다음 사용 가능한 2 배 워드 주소 (2 배 워드 당 4 바이트)입니다.|
|**PARA**|다음 단락을 사용할 수 있는 주소 (단락 당 16 바이트)입니다.|
|**PAGE**|다음 사용 가능한 페이지 주소 (페이지당 256 바이트)입니다.|
|**ALIGN**(*n*)|다음 사용 가능한 *n*번째 바이트 주소입니다. 자세한 내용은 설명 섹션을 참조 하세요.|

이 매개 변수를 지정 하지 않으면 **반** 기본적으로 사용 됩니다.

*combine*<br/>
**PUBLIC**, **STACK**, **COMMON**, **MEMORY**, **AT**<em>address</em>, **PRIVATE**

*use*<br/>
**USE16**, **USE32**, **FLAT**

*characteristics*<br/>
**정보**, **읽을**, **작성**를 **EXECUTE**, **공유**를 **NOPAGE**, **NOCACHE**, 및 **삭제**

비슷한 이름의 COFF 섹션 특성에 해당 및 COFF에 대해서만 지원 됩니다 (예를 들어 **공유** IMAGE_SCN_MEM_SHARED에 해당). 읽기는 IMAGE_SCN_MEM_READ 플래그를 설정합니다. 사용 되지 않는 읽기 전용 플래그 IMG_SCN_MEM_WRITE 플래그를 지우려면 섹션을 발생 합니다. 있는 경우 *특징* 는 설정, 기본 특성은 사용 되지 않으며 프로그래머가 지정한 플래그만 적용 됩니다.

`ALIAS(` *string* `)`<br/>
이 문자열은 내보낸된 COFF 개체의 섹션 이름으로 사용 됩니다.  같은 이름의 외부, 서로 다른 MASM 세그먼트 이름 가진 여러 섹션을 만듭니다.

지원 되지 않습니다 **/omf**합니다.

*class*<br/>
세그먼트 해야 결합 및 어셈블된 파일의 정렬 방법을 지정 합니다. 일반적인 값은 `'DATA'`하십시오 `'CODE'`, `'CONST'` 및 `'STACK'`

## <a name="remarks"></a>설명

에 대 한 `ALIGN(n)`하십시오 *n* 8192 개로 1에서 2의 배수가 될 수 있으며 지원 되지 않습니다 **/omf**합니다.

## <a name="see-also"></a>참고자료

[지시문 참조](../../assembler/masm/directives-reference.md)<br/>