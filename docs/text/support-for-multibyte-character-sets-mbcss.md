---
title: MBCS(멀티바이트 문자 집합) 지원
ms.date: 11/04/2016
helpviewer_keywords:
- MBCS [C++], about MBCS
- character sets [C++], multibyte
- multibyte characters [C++]
- MBCS [C++]
ms.assetid: b498733c-a1e1-45e3-8f26-d6da3cb5f2dd
ms.openlocfilehash: c21b5b1ff059f26558749e904894cb5d15572519
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57808406"
---
# <a name="support-for-multibyte-character-sets-mbcss"></a>MBCS(멀티바이트 문자 집합) 지원

MBCS(멀티바이트 문자 집합)는 일본어 및 중국어와 같이 싱글바이트로 표현할 수 없는 문자 집합을 지원하기 위한 이전의 접근 방식입니다. 새 개발을 수행하는 경우 최종 사용자에게 표시되지 않는 시스템 문자열을 제외한 모든 텍스트 문자열에 유니코드를 사용해야 합니다. MBCS는 이전 기술이며 새로운 개발에는 사용하지 않는 것이 좋습니다.

가장 일반적인 MBCS 구현은 DBCS(더블바이트 문자 집합)입니다. DBCS에 대해 일반적으로 Visual C++ 및 특별히 MFC가 완전히 사용하도록 설정됩니다.

샘플에 대해서는 MFC 소스 코드 파일을 참조하세요.

언어에 포함되는 문자의 갯수가 많아 큰 문자 집합이 사용되는 지역 및 국가에서 사용되는 플랫폼이라면 유니코드의 대안으로 멀티바이트 문자 집합(MBCS)을 사용하는 것이 좋습니다. MFC에서는 국제화 가능한 데이터 형식 및 C 런타임 함수를 사용하여 멀티바이트 문자 집합(MBCS)을 지원합니다. 코딩 방법은 같은 방식으로 이루어 집니다.

멀티바이트 문자 집합(MBCS)에서 문자의 크기는 1바이트나 2바이트로 인코딩됩니다. 2바이트 문자에서 앞 바이트, 즉 일반적인 선행 바이트에 따라 후행 바이트가 해석되도록 특별한 의미를 가지고 있습니다. 첫 번째 바이트는 선행 바이트로 사용하도록 미리 정의된 값의 범위가 있습니다. 선행 바이트가 될 수 있는 바이트 범위는 사용 중인 코드 페이지에 따라 다릅니다. 예를들어 일본어 코드 페이지 932에는 0x81부터 0x9F 범위가 선행 바이트로 사용되지만, 한국어 코드 페이지 949에는 다른 범위를 사용합니다.

멀티바이트 문자 집합(MBCS) 프로그래밍에서는 다음 사항을 모두 고려해야 합니다.

멀티바이트 문자 집합(MBCS)으로 이루어진 MBCS 환경에는 파일 및 디렉터리 이름과 같은 문자열이 나타날 수 있습니다.

### <a name="editing-operations"></a>편집 작업

멀티바이트 문자 집합(MBCS) 응용 프로그램에서의 편집 작업은 바이트 크기가 아닌 문자 갯수 단위로 수행되어야 합니다. 키보드에서 **오른쪽 화살표**를 눌렀다면 커서는 오른쪽으로 글자 한개 만큼 이동해야 합니다. **삭제** 했다면 글자 한개를 삭제해야 하며, **실행 취소** 했다면 글자 한개만 다시 삽입 해야 합니다. 한바이트 단위의 문자가 아님을 주의합니다.

### <a name="string-handling"></a>문자열 처리

MBCS를 사용하는 응용 프로그램에서 문자열 처리 시 특수한 문제가 발생합니다. 두 너비의 문자는 단일 문자열로 결합되므로 선행 바이트를 확인해야 합니다.

### <a name="run-time-library-support"></a>런타임 라이브러리 지원

C 런타임 라이브러리 및 MFC는 단일 바이트, 멀티바이트 문자 집합(MBCS) 및 유니코드 프로그래밍을 지원합니다. 단일 바이트 문자열은 `str` 계열의 런타임 함수로 처리되고 멀티바이트 문자 집합(MBCS)은 `_mbs` 계열의 함수로 처리되며 유니코드 문자열은 `wcs` 계열 함수로 처리됩니다. MFC 클래스의 맴버 함수 구현에는 "MBCS/유니코드 이식성"의 설명대로 일반적인 `str` 계열 함수들, MBCS 함수 또는 유니코드 함수에 적절히 매핑되는 이식 가능한 런타임 함수가 사용됩니다.

### <a name="mbcsunicode-portability"></a>MBCS/유니코드 이식성

Tchar.h 헤더 파일을 사용 하 여 빌드할 수 있습니다 단일 바이트, MBCS 및 유니코드 동일한 원본 으로부터의 응용 프로그램입니다. tchar.h에는 `str`, `_mbs` 또는 `wcs` 계열 함수에 적절히 매핑되는 *_tcs* 접두사가 붙은 매크로가 정의되어 있습니다. 멀티바이트 문자 집합(MBCS)으로 빌드하려면 `_MBCS` 상수를 정의하고. 유니코드로 빌드하려면`_UNICODE` 상수를 정의합니다. MFC 응용 프로그램에서는 `_UNICODE`가 기본적으로 정의됩니다. 자세한 내용은 [tchar.h의 제네릭 텍스트 매핑](../text/generic-text-mappings-in-tchar-h.md)을 참조하십시오.

> [!NOTE]
>  `_UNICODE`와 `_MBCS`를 모두 사용한다면 정의되지 않은 동작이 발생할 수 있습니다.

mbctype.h 및 mbstring.h 헤더 파일은 경우에 따라 필요할 수 있는 MBCS 관련 함수 및 매크로가 정의되어 있습니다. 예를 들어 `_ismbblead`는 문자열의 특정 바이트가 선행 바이트인지를 알려줍니다.

국제화 코드 관련 이식성을 위해 [유니코드](../text/support-for-unicode.md) 또는 멀티바이트 문자 집합(MBCS)으로 프로그램을 작성하세요.

## <a name="what-do-you-want-to-do"></a>원하는 작업을 선택하세요.

- [프로그램에서 MBCS 사용](../text/international-enabling.md)

- [프로그램에서 유니코드 및 MBCS를 사용하도록 설정](../text/internationalization-strategies.md)

- [MBCS를 사용하여 국제화된 프로그램 만들기](../text/mbcs-programming-tips.md)

- [MBCS 프로그래밍 요약 참조](../text/mbcs-programming-tips.md)

- [바이트 크기에 따른 이식성을 고려한 일반 텍스트 매핑에 대해 알아보기](../text/generic-text-mappings-in-tchar-h.md)

## <a name="see-also"></a>참고자료

[텍스트 및 문자열](../text/text-and-strings-in-visual-cpp.md)<br/>
[Visual C++에서 MBCS 지원](../text/mbcs-support-in-visual-cpp.md)
