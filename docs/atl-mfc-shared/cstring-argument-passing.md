---
title: CString 인수 전달
ms.date: 11/04/2016
helpviewer_keywords:
- strings [C++], as function input/output
- argument passing [C++]
- arguments [C++], passing
- functions [C++], strings as input/output
- argument passing [C++], C strings
- passing arguments, C strings
- CString objects, passing arguments
- string arguments
ms.assetid: a67bebff-edf1-4cf4-bbff-d1cc6a901099
ms.openlocfilehash: 1729167786d71c107fe6a4369d5a0c7e7c8594f1
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57742199"
---
# <a name="cstring-argument-passing"></a>CString 인수 전달

이 문서를 전달 하는 방법에 설명 [CString](../atl-mfc-shared/reference/cstringt-class.md) 함수를 반환 하는 방법을 개체 `CString` 함수에서 개체입니다.

##  <a name="_core_cstring_argument.2d.passing_conventions"></a> CString 인수 전달 규칙

클래스 인터페이스를 정의 하는 경우에 멤버 함수에 대 한 인수 전달 규칙을 결정 합니다. 전달 및 반환에 대 한 표준 규칙이 일부 `CString` 개체입니다. 에 설명 된 규칙을 따르는 경우 [함수 입력으로 문자열](#_core_strings_as_function_inputs) 하 고 [함수는 출력으로 문자열](#_core_strings_as_function_outputs), 효율적이 고 올바른 코드를 갖습니다.

##  <a name="_core_strings_as_function_inputs"></a> 함수 입력으로 문자열

가장 효율적이 고 안전한 방법을 사용 하는 `CString` 개체가 호출된 된 함수에 전달 하는 것을 `CString` 함수 개체입니다. 이름에도 불구 하 고는 `CString` 개체 null 종결자가 하는 C 스타일 문자열로 문자열을 내부적으로 저장 하지는 않습니다. 대신는 `CString` 개체 신중 하 게 추적에는 문자 수를 유지 합니다. 필요 `CString` null로 끝나는 문자열로 LPCTSTR 포인터가 작은 양의 코드를 지속적으로 작업을 수행 해야 하는 경우에 상당히 커질 수 있습니다 하는 작업을 제공 합니다. 변경 하기 때문에 결과 임시는 `CString` 내용을 이전 복사본 LPCTSTR 포인터를 무효화 합니다.

합리적일 C 스타일 문자열을 제공 하는 경우도 있습니다. 예를 들어 호출된 된 함수는 C로 작성 된 않았고 개체를 지원 하지 않습니다 상황이 있을 수 있습니다. 이 경우 강제 된 `CString` LPCTSTR을를 함수 매개 변수는 C 스타일 null로 끝나는 문자열을 받습니다. 또한 반대로 이동 하 고 만들 수 있습니다는 `CString` 사용 하 여 개체를 `CString` C 스타일 문자열 매개 변수를 받아들이는 생성자입니다.

문자열 콘텐츠는 함수에 의해 변경 될 경우는 nonconstant으로 매개 변수를 선언 `CString` 참조 (`CString&`).

##  <a name="_core_strings_as_function_outputs"></a> 함수는 출력으로 문자열

일반적으로 반환할 수 있습니다 `CString` 함수에서 개체 `CString` 개체 기본 형식과 마찬가지로 값 의미 체계를 따릅니다. 읽기 전용 문자열을 반환 하는 상수를 사용 하 여 `CString` 참조 (`const CString&`). 다음 예제에서는 `CString` 매개 변수 및 반환 형식:

[!code-cpp[NVC_ATLMFC_Utilities#197](../atl-mfc-shared/codesnippet/cpp/cstring-argument-passing_1.cpp)]

[!code-cpp[NVC_ATLMFC_Utilities#198](../atl-mfc-shared/codesnippet/cpp/cstring-argument-passing_2.cpp)]

## <a name="see-also"></a>참고자료

[문자열 (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)
