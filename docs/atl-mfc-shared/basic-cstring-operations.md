---
title: 기본 CString 작업
ms.date: 11/04/2016
helpviewer_keywords:
- CString objects, basic operations
- string literals, CString operations
- literal strings, CString operations
- CString objects
- string comparison, CString operations
- characters, accessing in CStrings
ms.assetid: 41db66b2-9427-4bb3-845a-9b6869159a6c
ms.openlocfilehash: 08c496038efc9e24e1c1610da07b6824c3a50b64
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62216859"
---
# <a name="basic-cstring-operations"></a>기본 CString 작업

이 항목에서는 다음과 같은 기본 설명 [CString](../atl-mfc-shared/reference/cstringt-class.md) 작업:

- [표준 C 리터럴 문자열에서 CString 개체 만들기](#_core_creating_cstring_objects_from_standard_c_literal_strings)

- [CString의 개별 문자 액세스](#_core_accessing_individual_characters_in_a_cstring)

- [두 개의 CString 개체를 연결합니다.](#_core_concatenating_two_cstring_objects)

- [CString 개체 비교](#_core_comparing_cstring_objects)

- [CString 개체 변환](#_core_converting_cstring_objects)

`Class CString` 클래스 템플릿을 기반으로 [CStringT 클래스](../atl-mfc-shared/reference/cstringt-class.md)합니다. `CString` **typedef** 의 `CStringT`합니다. 보다 정확 하 게 `CString` 되는 **typedef** 의 *명시적 특수화* 의 `CStringT`, 클래스 템플릿을 사용 하 여 클래스를 정의 하는 일반적인 방법은. 마찬가지로 정의 된 클래스는 `CStringA` 고 `CStringW`입니다.

`CString`하십시오 `CStringA`, 및 `CStringW` atlstr.h에서 정의 됩니다. `CStringT` cstringt.h에서 정의 됩니다.

`CString`를 `CStringA`, 및 `CStringW` 메서드 및 정의 하는 연산자 집합을 가져오려면 각 `CStringT` 지 문자열 데이터를 사용 합니다. 중복 및 경우에 따라 메서드 중 일부를 초과할의 C 런타임 라이브러리 문자열 서비스입니다.

참고: `CString` 기본 클래스입니다. C +에서 사용 되는 string 클래스에 대 한 + 관리 되는 프로젝트를 사용 하 여 CLI `System.String`합니다.

##  <a name="_core_creating_cstring_objects_from_standard_c_literal_strings"></a> 표준 C 리터럴 문자열에서 CString 개체 만들기

C 스타일 리터럴 문자열을 지정할 수 있습니다는 `CString` 하나를 할당 처럼 `CString` 개체를 다른 합니다.

- C 리터럴 문자열의 값을 할당 한 `CString` 개체입니다.

   [!code-cpp[NVC_ATLMFC_Utilities#183](../atl-mfc-shared/codesnippet/cpp/basic-cstring-operations_1.cpp)]

- 하나의 값을 할당 `CString` 간 `CString` 개체입니다.

   [!code-cpp[NVC_ATLMFC_Utilities#184](../atl-mfc-shared/codesnippet/cpp/basic-cstring-operations_2.cpp)]

   콘텐츠를 `CString` 하나 때 복사 되는 개체 `CString` 다른 개체를 할당 합니다. 따라서 두 문자열은 문자열을 구성 하는 실제 문자에 대 한 참조를 공유 하지 않습니다. 사용 하는 방법에 대 한 자세한 내용은 `CString` 값으로 개체 참조 [CString 의미 체계](../atl-mfc-shared/cstring-semantics.md)합니다.

   > [!NOTE]
   > 유니코드 나 ANSI에 컴파일할 수 있도록 응용 프로그램을 작성, 리터럴 문자열을 _T 매크로 사용 하 여 코드입니다. 자세한 내용은 [유니코드 및 멀티 바이트 문자 집합 (MBCS) 지원](../atl-mfc-shared/unicode-and-multibyte-character-set-mbcs-support.md)합니다.

##  <a name="_core_accessing_individual_characters_in_a_cstring"></a> CString의 개별 문자 액세스

개별 문자에 액세스할 수 있습니다는 `CString` 사용 하 여 개체를 `GetAt` 및 `SetAt` 메서드. 배열 요소 또는 아래 첨자 연산자 () 대신 사용할 수도 있습니다 `GetAt` 개별 문자를 가져오려고 합니다. (이 비슷하며 배열 요소에 액세스 하 여 표준 C 스타일 문자열) 인덱스에 대 한 값 `CString` 문자는 0부터 시작 합니다.

##  <a name="_core_concatenating_two_cstring_objects"></a> 두 개의 CString 개체를 연결합니다.

연결할 두 `CString` 연결 연산자를 사용 하는 개체 (+ 또는 + =), 다음과 같이 합니다.

[!code-cpp[NVC_ATLMFC_Utilities#185](../atl-mfc-shared/codesnippet/cpp/basic-cstring-operations_3.cpp)]

연결 연산자는 하나 이상의 인수 (+ 또는 + =) 이어야 합니다는 `CString` 개체를 사용할 수 있습니다 상수 문자열 (예를 들어 `"big"`) 또는 **char** (예: ' x') 다른 인수에 대 한 합니다.

##  <a name="_core_comparing_cstring_objects"></a> CString 개체 비교

합니다 `Compare` 메서드 및 연산자 = = `CString` 동일 합니다. `Compare`하십시오 **연산자 = =**, 및 `CompareNoCase` 는 MBCS 및 유니코드 인식; `CompareNoCase` 대/소문자 이기도 합니다. 합니다 `Collate` 메서드의 `CString` 로캘 구분 되며가 더 느려지므로 자주 `Compare`합니다. 사용 하 여 `Collate` 현재 로캘에 따라 지정 된 대로 규칙만 정렬 하 여 따라야 위치 합니다.

다음 표에서 사용 가능한 [CString](../atl-mfc-shared/reference/cstringt-class.md) 비교 함수 및 C 런타임 라이브러리에서 해당 노트북/MBCS-유니코드 함수와 합니다.

|CString 함수|MBCS 함수|유니코드 함수|
|----------------------|-------------------|----------------------|
|`Compare`|`_mbscmp`|`wcscmp`|
|`CompareNoCase`|`_mbsicmp`|`_wcsicmp`|
|`Collate`|`_mbscoll`|`wcscoll`|

`CStringT` 관계형 연산자를 정의 하는 클래스 템플릿 (<, \<=, > =, >, = =, 및! =)를 사용 하 여 사용할 수 있는 `CString`. 두 개를 비교 `CStrings` 다음 예와에서 같이 이러한 연산자를 사용 하 여 합니다.

[!code-cpp[NVC_ATLMFC_Utilities#186](../atl-mfc-shared/codesnippet/cpp/basic-cstring-operations_4.cpp)]

##  <a name="_core_converting_cstring_objects"></a> CString 개체 변환

CString 개체를 다른 문자열 형식으로 변환 하는 방법에 대 한 내용은 [방법: 다양 한 문자열 형식 간 변환](../text/how-to-convert-between-various-string-types.md)합니다.

## <a name="using-cstring-with-wcout"></a>Wcout CString 사용

CString 사용 하 여는 데 `wcout` 개체를 명시적으로 캐스팅 해야 합니다는 `const wchar_t*` 다음 예와에서 같이:

```cpp
CString cs("meow");

wcout << (const wchar_t*) cs << endl;
```

캐스트를 사용 하지 않고 `cs` 로 처리 됩니다는 `void*` 고 `wcout` 개체의 주소를 출력 합니다. 템플릿 인수 감소 및 오버 로드 확인 되는 올바른 자체와 준수 간의 미묘한 상호 작용 하 여이 문제는 발생 된 C++ 표준입니다.

## <a name="see-also"></a>참고자료

[문자열 (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)<br/>
[CStringT 클래스](../atl-mfc-shared/reference/cstringt-class.md)<br/>
[템플릿 특수화](../cpp/template-specialization-cpp.md)<br/>
[방법: 다양한 문자열 형식 간 변환](../text/how-to-convert-between-various-string-types.md)
