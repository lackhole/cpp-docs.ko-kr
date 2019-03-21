---
title: 국가별 사용
ms.date: 11/04/2016
helpviewer_keywords:
- globalization [C++], character sets
- strings [C++], international enabling
- localization [C++], character sets
- MBCS [C++], enabling
- Unicode [C++], enabling
ms.assetid: b077f4ca-5865-40ef-a46e-d9e4d686ef21
ms.openlocfilehash: 22f2dba49e894e93cb6791d76a65730f3269199e
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57748010"
---
# <a name="international-enabling"></a>국가별 사용

대부분의 기존 C 및 c + + 코드에서는 국가별 응용 프로그램에 대 한 제대로 작동 하지 않는 문자 및 문자열 조작에 대 한 가정 합니다. 런타임 라이브러리와 MFC MBCS 또는 유니코드를 지원 하지만 아직 해결 방법이 수행할 수 있습니다. 이 섹션에서는 안내, Visual c + +에서 "국가별 사용"의 의미를 설명 합니다.

- 유니코드와 MBCS MFC 함수 매개 변수 목록에서 이식 가능한 데이터 형식을 통해 활성화 됩니다 및 형식을 반환 합니다. 이러한 형식은 빌드 기호를 정의 하는 여부에 따라 적절 한 방법으로 조건부로 정의 됩니다 `_UNICODE` 기호 또는 `_MBCS` (즉 DBCS). MFC 라이브러리의 여러 변형은 빌드 정의 이러한 두 기호에 따라 응용 프로그램을 자동으로 연결 됩니다.

- 클래스 라이브러리 코드를 사용 하 여 이식 가능한 런타임 함수 및 다른 방법 유니코드 또는 MBCS에 대 한 올바른 동작을 확인 합니다.

- 여전히 코드에서 특정 종류의 국제화 작업 처리 해야 합니다.

   - MFC 이식 가능한 환경 중 하나에서 동일한 이식 가능한 런타임 함수를 사용 합니다.

   - 리터럴 문자열 및 문자를 환경 중 하나에서 이식 가능 하도록 사용 하는 `_T` 매크로입니다. 자세한 내용은 [tchar.h의 제네릭 텍스트 매핑](../text/generic-text-mappings-in-tchar-h.md)을 참조하십시오.

   - Mbcs 문자열 구문 분석 하는 경우에 주의 해야 합니다. 유니코드에서 이러한 예방 조치 필요 하지 않습니다. 자세한 내용은 [MBCS 프로그래밍 팁](../text/mbcs-programming-tips.md)합니다.

   - 응용 프로그램에서 ANSI (8 비트) 및 유니코드 (16 비트) 문자를 함께 사용할 경우 주의 해야 합니다. 프로그램의 일부에서 ANSI 문자 및 다른 환경에서는 유니코드 문자를 사용할 수 있지만 동일한 문자열에 혼합할 수 없습니다.

   - 응용 프로그램에서 문자열을 하드 코딩 하지 마십시오. 대신 있도록 STRINGTABLE 리소스 응용 프로그램의.rc 파일을 추가 하 여 합니다. 그런 다음 소스 코드를 변경 하거나 다시 컴파일하지 않고도 응용 프로그램을 지역화할 수 있습니다. STRINGTABLE 리소스에 대 한 자세한 내용은 참조 하세요. [문자열 편집기](../windows/string-editor.md)합니다.

> [!NOTE]
>  유럽 및 MBCS 문자 집합 일부 문자를 0x80 보다 큰 문자 코드를 사용 하 여 악센트 부호가 있는 문자 같은 경우 0x80 보다 큰이 문자 부호 확장으로 변환 하는 경우는 대부분의 코드는 부호 있는 문자를 사용 하므로 **int**합니다. 이 문제가 있는 경우 배열 인덱싱에 대 한 부호 확장 하는 문자, 음수로 인덱스 배열 외부에 있으므로 일본어 같은 MBCS를 사용 하는 언어 역시 고유 합니다. 문자를 1 또는 2 바이트로 구성 될 수, 때문에 동시에 두 바이트에 항상 처리 해야 합니다.

## <a name="see-also"></a>참고자료

[유니코드 및 MBCS](../text/unicode-and-mbcs.md)<br/>
[국제화 전략](../text/internationalization-strategies.md)
