---
title: 문자열 데이터 관리
ms.date: 11/04/2016
helpviewer_keywords:
- Unicode, string objects
ms.assetid: 0b53a542-eeb1-4108-9ada-6700645b6f8f
ms.openlocfilehash: b247e97f5aa6b5e85a6a6b6f57a64224a9e0f435
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57747179"
---
# <a name="string-data-management"></a>문자열 데이터 관리

Visual c + + 문자열 데이터를 관리 하는 여러 방법을 제공 합니다.

- [문자열 조작](../c-runtime-library/string-manipulation-crt.md) C 스타일 null로 끝나는 문자열을 사용 하 여 작업에 대 한

- 문자열을 관리 하기 위한 Win32 API 함수

- MFC의 클래스 [CStringT 클래스](../atl-mfc-shared/reference/cstringt-class.md)를 유연 하 고 크기 조정 가능한 문자열 개체를 제공 하는

- 클래스 [CStringT 클래스](../atl-mfc-shared/reference/cstringt-class.md)와 동일한 기능을 사용 하 여 MFC에 독립적인 문자열 개체를 제공 하는 `CString`

거의 모든 프로그램이 문자열 데이터를 사용하여 작업합니다. MFC의 `CString` 클래스 유연한 문자열 처리를 위한 최선의 솔루션 경우가 많습니다. 버전 7.0부터 `CString` 프로그램 MFC / MFC에 관계 없이 사용할 수 있습니다. 런타임 라이브러리 및 `CString` 유니코드 또는 MBCS 프로그래밍와 같이 멀티 바이트 (와이드) 문자를 포함 하는 문자열을 지원 합니다.

이 문서에서는 문자열 조작에 관련 된 클래스 라이브러리를 제공 하는 범용 서비스를 설명 합니다. 이 문서에서 다루는 항목은 다음과 같습니다.

- [유니코드 및 MBCS 제공 이식성](#_core_unicode_and_mbcs_provide_portability)

- [Cstring 및 const char 포인터](#_core_cstrings_and_const_char_pointers)

- [CString 참조 횟수](#_core_cstring_reference_counting)

합니다 [CStringT 클래스](../atl-mfc-shared/reference/cstringt-class.md) 클래스는 문자열 조작에 대 한 지원을 제공 합니다. 대체 하 고 일반적으로 C 런타임 라이브러리 문자열 패키지에서 제공 하는 기능을 확장 것입니다. `CString` 클래스 멤버 함수 및 간소화 된 문자열 처리, Basic에 있는 것과 비슷한에 대 한 연산자를 제공 합니다. 클래스는 생성자와 연산자를 생성, 할당 및 비교에 대 한 `CString`및 표준 c + + 문자열 데이터 형식입니다. 때문에 `CString` 에서 파생 되지 않은 `CObject`를 사용할 수 있습니다 `CString` 대부분 Microsoft Foundation 클래스 라이브러리 (MFC)의 독립적으로 개체입니다.

`CString` 개체에 따라 "의미 체계를 값입니다." `CString` 개체 고유 값을 나타냅니다. 생각할는 `CString` 는 실제 문자열로, 문자열에 대 한 포인터 아니라 합니다.

`CString` 개체는 다양 한 문자 시퀀스를 나타냅니다. `CString` 개체 문자 배열로 간주할 수 있습니다.

##  <a name="_core_unicode_and_mbcs_provide_portability"></a> 유니코드 및 MBCS 이식성을 제공합니다.

포함 하 여 MFC 버전 3.0 이상에서 MFC를 사용 하 여 `CString`, 유니코드 및 멀티 바이트 문자 집합 (MBCS) 모두 사용 됩니다. 이 지원을 통해 쉽게 유니코드 또는 ANSI 문자를 구축할 수 있도록 이식 가능한 응용 프로그램을 작성할 수 있습니다. 이러한 이식성을 각 문자에 사용할 수 있도록를 `CString` TCHAR로 정의 된 형식의 개체가 `wchar_t` 응용 프로그램을 빌드할 때 기호 _UNICODE를 정의 하는 경우 또는 `char` 그렇지 않은 경우. `wchar_t` 문자는 16 비트 다양 합니다. MBCS는 기호 _MBCS 정의 사용 하 여 작성 하는 경우에 사용 됩니다. MFC 자체 (NAFX 라이브러리용) _MBCS 기호를 사용 하 여 빌드 또는 _UNICODE 기호 (UAFX 라이브러리)를 정의 합니다.

> [!NOTE]
>  `CString` 예제에이 문자열에 함께 제공 되는 문서를 폼에 리터럴 문자열을 변환 _T 매크로 사용 하 여 유니코드 이식성에 대 한 서식이 리터럴 문자열 보여 줍니다.

`L"literal string"`

> [!NOTE]
>  컴파일러가는 유니코드 문자열로 취급 합니다. 예를 들어, 다음 코드는

[!code-cpp[NVC_ATLMFC_Utilities#187](../atl-mfc-shared/codesnippet/cpp/string-data-management_1.cpp)]

> [!NOTE]
>  그렇지 않은 경우 ANSI 문자열 또는 _UNICODE가 정의 된 경우 유니코드 문자열로 변환 됩니다. 자세한 내용은 문서 참조 [유니코드 및 멀티 바이트 문자 집합 (MBCS) 지원](../atl-mfc-shared/unicode-and-multibyte-character-set-mbcs-support.md)합니다.

`CString` INT_MAX (2147483647) 자 개체 저장할 수 있습니다. TCHAR 데이터 형식을 가져오거나 안에 있는 개별 문자를 설정 하는 한 `CString` 개체입니다. 문자 배열과 달리는 `CString` 클래스에 기본 제공 메모리 할당 기능이 있습니다. 따라서 `CString` 필요에 따라 자동으로 증가 하는 개체 (즉, 증가에 대해 걱정할 필요가 없습니다를 `CString` 더 긴 문자열에 맞게 개체).

##  <a name="_core_cstrings_and_const_char_pointers"></a> Cstring 및 const char 포인터

A `CString` 도 개체 리터럴 C 스타일 문자열 처럼 작동할 수 있습니다 (을 `PCXSTR`와 같습니다 **const char** <strong>\*</strong> 유니코드에 포함 되지 않는 경우). 합니다 [CSimpleStringT::operator PCXSTR](../atl-mfc-shared/reference/csimplestringt-class.md#operator_pcxstr) 변환 연산자를 사용 하면 `CString` 자유롭게 함수 호출에서 문자 포인터에 대 한 대체 될 개체입니다. 합니다 **CString (LPCWSTR** `pszSrc` **)** 생성자를 대체할 문자 포인터를 사용 하면 `CString` 개체입니다.

접기 하려고 하지 `CString` 개체입니다. 두 한다면 `CString` 포함 된 개체 `Chicago`, 예를 들어, 문자 `Chicago` 두 위치에 저장 됩니다. (이 아닐 수도 MFC의 이후 버전의 true 있으므로 사용 하지 않아야 합니다.)

> [!NOTE]
>  사용 된 [CSimpleStringT::GetBuffer](../atl-mfc-shared/reference/csimplestringt-class.md#getbuffer) 및 [CSimpleStringT::ReleaseBuffer](../atl-mfc-shared/reference/csimplestringt-class.md#releasebuffer) 멤버 함수에 직접 액세스 해야 하는 경우를 `CString` 비상수 문자 포인터로.

> [!NOTE]
>  사용 합니다 [CStringT::AllocSysString](../atl-mfc-shared/reference/cstringt-class.md#allocsysstring) 하 고 [CStringT::SetSysString](../atl-mfc-shared/reference/cstringt-class.md#setsysstring) 할당 하 고 자동화 (이전의 OLE Automation)에 사용 하는 BSTR 개체를 설정 하는 멤버 함수입니다.

> [!NOTE]
>  가능한 경우 할당 `CString` 프레임이 아닌 힙에 개체입니다. 이 메모리를 절약 하 고 전달 매개 변수를 간소화 합니다.

합니다 `CString` 클래스는 Microsoft Foundation Class 라이브러리 컬렉션 클래스로 하지만 구현 되지 `CString` 개체 컬렉션에 요소로 확실히 저장할 수 있습니다.

##  <a name="_core_cstring_reference_counting"></a> CString 참조 횟수

MFC 버전 4.0부터 때 [CStringT 클래스](../atl-mfc-shared/reference/cstringt-class.md) 개체는 복사, MFC에는 데이터를 복사 하는 것이 아니라 참조 횟수를 증가 시킵니다. 이렇게 하면 값 및 반환 매개 변수 전달 `CString` 값 보다 효율적으로 개체입니다. 이러한 작업으로 인해 한 번 이상 호출 될 복사 생성자입니다. 이러한 일반적인 작업에 대 한 오버 헤드를 줄이고 사용 하 여 참조 횟수를 늘리면 `CString` 더 매력적인 옵션입니다.

각 복사본은 제거 된 것으로 원래 개체의 참조 횟수를 감소 됩니다. 원래 `CString` 참조 개수가 0으로 감소 될 때까지 개체 소멸 되지 않습니다.

사용할 수는 `CString` 멤버 함수 [CSimpleStringT::LockBuffer](../atl-mfc-shared/reference/csimplestringt-class.md#lockbuffer) 및 [CSimpleStringT::UnlockBuffer](../atl-mfc-shared/reference/csimplestringt-class.md#unlockbuffer) 하거나 참조 횟수를 사용 하지 않도록 합니다.

## <a name="see-also"></a>참고자료

[일반 MFC 항목](../mfc/general-mfc-topics.md)
