---
title: 유니코드 및 멀티바이트 문자 집합(MBCS) 지원
ms.date: 1/09/2017
helpviewer_keywords:
- MFC [C++], character set support
- MBCS [C++], strings and MFC support
- strings [C++], MBCS support in MFC
- character sets [C++], multibyte
- Unicode [C++], MFC strings
- Unicode [C++], string objects
- strings [C++], Unicode
- strings [C++], character set support
ms.openlocfilehash: 59e8759ffbe61b80c74d8b5aba5bc50886d6b23d
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57743914"
---
# <a name="unicode-and-multibyte-character-set-mbcs-support"></a>유니코드 및 멀티바이트 문자 집합(MBCS) 지원

예를 들어, 일본어 및 중국어와 일부 언어에서는 큰 문자 집합이. Microsoft Foundation 클래스 라이브러리 (MFC) 수를이 시장에 대 한 프로그래밍을 지원 큰 문자 집합을 처리 하는 두 가지 방법이 있습니다.

- [유니코드](#mfc-support-for-unicode-strings), `wchar_t` 와이드 문자와 u t F-16으로 인코드된 문자열을 기반으로 합니다.

- [멀티 바이트 문자 집합 (MBCS)](#mfc-support-for-mbcs-strings), **char** 단일 또는 더블 바이트 문자 및 로캘별 문자 집합에서 인코딩된 문자열을 기반으로 합니다.

Microsoft가 새로운 개발에 대 한 유니코드 MFC 라이브러리를 권장 하 고 Visual Studio 2013 및 Visual Studio 2015에서 MBCS 라이브러리는 사용 되지 않는 합니다. 이제는 그렇지 않습니다. Visual Studio 2017에서 MBCS 사용 되지 않음 경고가 제거 되었습니다.

## <a name="mfc-support-for-unicode-strings"></a>유니코드 문자열에 대 한 MFC 지원

전체 MFC 클래스 라이브러리는 유니코드 문자 및 와이드 문자에 u t F-16으로 저장 하는 문자열에 대 한 조건에 따라 사용 됩니다. 특히 클래스 [CString](../atl-mfc-shared/reference/cstringt-class.md) 유니코드를 사용 합니다.

이러한 라이브러리, 디버거 및 DLL 파일은 MFC의 유니코드를 지원 하기 위해 사용 됩니다.

|||||
|-|-|-|-|
|UAFXCW.LIB|UAFXCW.PDB|UAFXCWD.LIB|UAFXCWD.PDB|
|MFC*버전*U.LIB|MFC*version*U.PDB|MFC*버전*U.DLL|MFC*버전*UD 합니다. LIB|
|MFC*version*UD.PDB|MFC*version*UD.DLL|MFCS*버전*U.LIB|MFCS*version*U.PDB|
|MFCS*version*UD.LIB|MFCS*version*UD.PDB|MFCM*버전*U.LIB|MFCM*version*U.PDB|
|MFCM*version*U.DLL|MFCM*버전*UD 합니다. LIB|MFCM*version*UD.PDB|MFCM*버전*UD 합니다. DLL|

(*버전* 파일의 버전 번호를 나타내는 예를 들어, '140' 의미 버전 14.0입니다.)

`CString` TCHAR 데이터 형식에 기반 합니다. TCHAR 유형으로 정의 된 기호 _UNICODE 프로그램의 빌드에 대해 정의 된 경우 `wchar_t`, 16 비트 문자 인코딩 형식입니다. TCHAR로 정의 되는 고, 그렇지 **char**, 일반 8 비트 문자 인코딩입니다. 따라서 유니코드에서는 `CString` 16 비트 문자 구성 됩니다. 유니코드 없이 형식 문자의 구성 되어 있을 **char**합니다.

응용 프로그램의 전체 유니코드 프로그래밍에 다음을 수행 해야합니다.

- 코드 조건에 따라 리터럴 문자열을 _T 매크로 사용 하 여 유니코드로 이식 가능 합니다.

- 문자열을 전달 하는 경우 함수 인수 문자에서 길이 또는 길이 (바이트)를 요구 하는지 여부에 주의 합니다. 차이점은 유니코드 문자열을 사용 하는 경우에 중요 합니다.

- 이식 가능한 버전의 C 런타임 문자열 처리 함수를 사용 합니다.

- 문자 및 문자 포인터에 대 한 다음 데이터 형식을 사용 합니다.

   - TCHAR를 사용 하는 위치를 사용 하 여 **char**합니다.

   - LPTSTR 사용 하는 위치를 사용 하 여 **char**<strong>\*</strong>합니다.

   - LPCTSTR을 사용 하는 위치를 사용 하 여 **const char**<strong>\*</strong>합니다. `CString` 연산자 간에 변환할 LPCTSTR `CString` 및 LPCTSTR 합니다.

`CString` 또한 유니코드 인식 생성자, 대입 연산자 및 비교 연산자를 제공합니다.

합니다 [런타임 라이브러리 참조](../c-runtime-library/c-run-time-library-reference.md) 이식 가능한 버전의 모든 문자열 처리 함수를 정의 합니다. 자세한 내용은 참조는 범주 [국제화](../c-runtime-library/internationalization.md)합니다.

## <a name="mfc-support-for-mbcs-strings"></a>MBCS 문자열에 대 한 MFC 지원

클래스 라이브러리는 멀티 바이트 문자 집합에도 사용할 수 있지만 더블 바이트 문자 집합 (DBCS).

멀티 바이트 문자 집합에서 문자 하나 또는 두 개의 바이트를 수 있습니다. 첫째 바이트는 특별 한 "선행 바이트" 2 바이트인 경우 코드에 따라 페이지 사용 되는 특정 범위에서 선택한입니다. 전체적으로 볼 때, 잠재 고객 및 "후행 바이트가" 고유 문자 인코딩을 지정 합니다.

프로그램의 빌드에 대 한 기호 _MBCS 정의 된 경우에 TCHAR로 입력 `CString` 기반, 매핑됩니다 **char**합니다. 바이트를 결정 하는 것을 `CString` 는 선행 바이트와 후행 바이트입니다. C 런타임 라이브러리는이 확인할 수 있도록 함수를 제공 합니다.

Dbcs에서 지정 된 문자열은 싱글바이트 ANSI 문자만, 모든 더블 바이트 문자 또는 두의 조합을 포함할 수 있습니다. 이러한 가능성에 문자열을 구문 분석할 때는 특별히 주의 해야 합니다. 여기에 `CString` 개체입니다.

> [!NOTE]
> MFC의 유니코드 문자열 serialization 실행 중인 응용 프로그램의 버전에 관계 없이 유니코드와 MBCS 문자열을 읽을 수 있습니다. 데이터 파일은 프로그램의 유니코드 및 MBCS 버전 간에 이식 가능 합니다.

`CString` 특별 한 "일반 텍스트" 버전의 C 런타임 함수, 호출을 사용 하 여 멤버 함수 또는 유니코드 인식 함수를 사용 합니다. 따라서 예를 들어 경우는 `CString` 함수를 호출 하는 `strcmp`, 해당 일반 텍스트 함수를 호출 `_tcscmp` 대신 합니다. _UNICODE 및 _MBCS 기호를 정의 하는 방법에 따라 `_tcscmp` 다음과 같이 매핑합니다.

|||
|-|-|
|_MBCS 정의됨|`_mbscmp`|
|_UNICODE 정의됨|`wcscmp`|
|어떤 기호도 정의|`strcmp`|

> [!NOTE]
> _UNICODE 및 _MBCS 기호를은 상호 배타적입니다.

에 설명 되어 모든 런타임 문자열 처리 루틴에 대 한 일반 텍스트 함수 매핑을 [C 런타임 라이브러리 참조](../c-runtime-library/c-run-time-library-reference.md)합니다. 목록에 대해서 [국제화](../c-runtime-library/internationalization.md)합니다.

마찬가지로, `CString` 메서드는 제네릭 데이터 형식 매핑을 사용 하 여 구현 됩니다. 모두 MBCS 및 유니코드를 사용 하려면 MFC 사용에 대 한 TCHAR **char** 또는 `wchar_t`에 대 한 LPTSTR **char** <strong>\*</strong> 또는 `wchar_t*`, 및 LPCTSTR 에대한**const char** <strong>\*</strong> 또는 `const wchar_t*`합니다. 이러한 MBCS 또는 유니코드 중 하나에 대 한 올바른 매핑을 확인 하십시오.

## <a name="see-also"></a>참고자료

[문자열 (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)<br/>
[문자열 조작](../c-runtime-library/string-manipulation-crt.md)
