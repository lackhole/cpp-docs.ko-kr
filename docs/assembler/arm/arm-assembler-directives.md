---
title: ARM 어셈블리 지시문
ms.date: 08/30/2018
ms.assetid: 9cfa8896-ec10-4e77-855a-3135c40d7d2a
ms.openlocfilehash: 9124f893b3334e0893073332c9d5f5a1388373d9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62167675"
---
# <a name="arm-assembler-directives"></a>ARM 어셈블리 지시문

Microsoft ARM 어셈블러에서 설명 하는 ARM 어셈블리 언어를 사용 하는 대부분의 경우는 [ARM 컴파일러 armasm 참조 가이드](http://infocenter.arm.com/help/topic/com.arm.doc.dui0802b/index.html)합니다. 그러나 일부 어셈블리 지시문의 Microsoft 구현이 매우 친숙 ARM 어셈블리 지시문에서 다릅니다. 이 문서에서는 차이점을 설명합니다.

## <a name="microsoft-implementations-of-arm-assembly-directives"></a>ARM 어셈블리 지시문의 Microsoft 구현

- 영역

   Microsoft ARM 어셈블러에서 지 원하는 이러한 `AREA` 특성: `ALIGN`, `CODE`, `CODEALIGN`, `DATA`를 `NOINIT`, `READONLY`를 `READWRITE`를 `THUMB`, `ARM`합니다.

   제외한 모든 `THUMB` 하 고 `ARM` 에 설명 된 대로 작동 합니다 [ARM 컴파일러 armasm 참조 가이드](http://infocenter.arm.com/help/topic/com.arm.doc.dui0802b/index.html)합니다.

   Microsoft ARM 어셈블러에서 `THUMB` 나타냅니다는 `CODE` 섹션 Thumb 코드가 포함 되며에 대 한 기본 `CODE` 섹션입니다.  `ARM` 섹션 ARM 코드를 포함 됨을 나타냅니다.

- ATTR

   지원되지 않습니다.

- CODE16

   Microsoft ARM 어셈블러 허용 하지 않는 이전 UAL Thumb 구문 의미 하기 때문에 지원 되지 않습니다.  사용 된 `THUMB` UAL 구문 대신 함께 지시문입니다.

- 일반적인

   일반적인 영역에 대 한 맞춤 사양의 지원 되지 않습니다.

- DCDO

   지원되지 않습니다.

- `DN`, `QN`, `SN`

   형식 또는 별칭은 등록에서 레인 사양 지원 되지 않습니다.

- 항목

   지원되지 않습니다.

- EQU

   정의 된 기호에 대 한 형식의 사양 지원 되지 않습니다.

- `EXPORT` 및 `GLOBAL`

   이 구문을 사용 하 여 내보내기를 지정 합니다.

   > **EXPORT**|**GLOBAL** <em>sym</em>{**[**<em>type</em>**]**}

   *기호* 내보낼 기호입니다.  [*형식*] 지정한 경우 일 수 있습니다 `[DATA]` 기호 데이터를 가리키는지 나타내려면 또는 `[FUNC]` 기호 코드를 가리키는지 나타냅니다. `GLOBAL` 와 `EXPORT`는 동의어입니다.

- EXPORTAS

   지원되지 않습니다.

- 프레임

   지원되지 않습니다.

- `FUNCTION` 및 `PROC`

   어셈블리 구문 사양 사용자 지정을 지원 하지만 레지스터는 호출자가 저장, 호출 수신자 저장 된 다른를 나열 하 여 프로시저에 대 한 호출 규칙 Microsoft ARM 어셈블러 구문을 허용 하지만 무시 등록 목록입니다.  어셈블러에 의해 생성 된 디버그 정보를 기본 호출 규칙을 지원 합니다.

- `IMPORT` 및 `EXTERN`

   이 구문을 사용 하 여 가져오기를 지정 합니다.

   > **IMPORT**|**EXTERN** *sym*{**, WEAK** *alias*{**, TYPE** *t*}}

   *기호* 가져올 기호의 이름입니다.

   하는 경우 `WEAK` *별칭* 을 지정 함을 나타냅니다 *sym* 약한 external입니다. 링크 타임에 대 한 정의가 없습니다가 경우에 대 한 모든 참조에 대신 바인딩합니다 *별칭*합니다.

   하는 경우 `TYPE` *t* 을 지정한 경우 *t* 링커를 해결 하려면 시도해 야 하는 방법을 나타냅니다 *sym*합니다.  이러한 값에 대 한 *t* 가능 합니다.

   |값|설명|
   |-|-|
   |1|에 대 한 라이브러리 검색을 수행 하지 않는 *기호*|
   |2|라이브러리를 검색 *기호*|
   |3|*sym* 별칭인 *별칭* (기본값)|

   `EXTERN` 에 대 한 동의어가 `IMPORT`점을 제외 하 고 *sym* 현재 어셈블리에서에 대 한 참조가 필요한 경우에 가져올 합니다.

- MACRO

   매크로의 상태 코드를 보유할 변수를 사용이 지원 되지 않습니다. 기본값은 매크로 매개 변수는 지원 되지 않습니다.

- NOFP

   지원되지 않습니다.

- `OPT`, `TTL`, `SUBT`

   Microsoft ARM 어셈블러 목록 생성 하지 때문에 지원 되지 않습니다.

- PRESERVE8

   지원되지 않습니다.

- 재배치

   `RELOC n` 명령 또는 데이터 정의 지시문을 따를 수 있습니다. "익명 기호가 없습니다" 수를 옮겨야 하는 경우

- 필요

   지원되지 않습니다.

- REQUIRE8

   지원되지 않습니다.

- THUMBX

   Microsoft ARM 어셈블러 Thumb 2EE 명령 집합을 지원 하지 않으므로 지원 되지 않습니다.

## <a name="see-also"></a>참고자료

[ARM 어셈블러 명령줄 참조](../../assembler/arm/arm-assembler-command-line-reference.md)<br/>
[ARM 어셈블러 진단 메시지](../../assembler/arm/arm-assembler-diagnostic-messages.md)<br/>
