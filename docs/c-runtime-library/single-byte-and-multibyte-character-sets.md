---
title: 싱글바이트 및 멀티바이트 문자 집합
ms.date: 11/04/2016
f1_keywords:
- c.character.multibyte
helpviewer_keywords:
- SBCS (single byte character set)
- MBCS [C++], about MBCS
- character sets [C++], multibyte
- character sets [C++], single byte
ms.assetid: 2cbc78ea-33c0-4cfb-b0df-7ce2458431ce
ms.openlocfilehash: 1e2d3f26891257101b4a9511f4e0b10f03113309
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57745334"
---
# <a name="single-byte-and-multibyte-character-sets"></a>싱글바이트 및 멀티바이트 문자 집합

ASCII 문자 집합은 0x00 - 0x7F 범위의 문자를 정의합니다. 주로 유럽의 많은 문자 집합은 ASCII 문자 집합과 동일하게 0x00 - 0x7F 범위 내 문자를 정의할 뿐만 아니라 0x80 - 0xFF 범위의 확장명 문자 집합도 정의합니다. 따라서 8비트 SBCS(싱글바이트 문자 집합)는 ASCII 문자 집합과 많은 유럽 언어의 문자 집합을 나타내는 데 충분합니다. 그러나 한국어와 같은 일부 비유럽 문자 집합에는 싱글바이트 코딩 구성표로 표현할 수 있는 것보다 더 많은 문자가 포함되므로 MBCS(멀티바이트 문자 집합) 인코딩이 필요합니다.

> [!NOTE]
> Microsoft 런타임 라이브러리의 많은 SBCS 루틴에서는 멀티바이트 바이트, 문자 및 문자열을 적절하게 처리합니다. 많은 멀티바이트 문자 집합은 ASCII 문자 집합을 하위 집합으로 정의합니다. 많은 멀티바이트 문자 집합에서 0x00 - 0x7F 범위의 각 문자는 ASCII 문자 집합에 동일한 값을 가진 문자와 같습니다. 예를 들어 ASCII 및 MBCS 문자열 모두에서 1바이트 null 문자('\0')는 0x00 값을 가지며 종료 null 문자를 나타냅니다.

멀티바이트 문자 집합은 1바이트 문자와 2바이트 문자 모두로 구성할 수 있습니다. 따라서 멀티바이트 문자열은 싱글바이트 및 더블바이트 문자를 혼합하여 포함할 수 있습니다. 2바이트 멀티바이트 문자는 후행 바이트와 선행 바이트를 가집니다. 특정 멀티바이트 문자 집합에서 선행 바이트는 후행 바이트와 마찬가지로 특정 범위 내에 속합니다. 이러한 범위가 겹치는 경우에는 지정된 바이트가 선행 바이트 또는 후행 바이트로 작동하는지 여부를 특정 상황에 따라 판단해야 합니다.

## <a name="see-also"></a>참고 항목

[국제화](../c-runtime-library/internationalization.md)<br/>
[범주별 유버니설 C 런타임 루틴](../c-runtime-library/run-time-routines-by-category.md)<br/>
