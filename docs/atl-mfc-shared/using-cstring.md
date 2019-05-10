---
title: CString 사용
ms.date: 06/18/2018
helpviewer_keywords:
- CString objects, C++ string manipulation
- CString objects, reference counting
- CString class (Visual C++)
ms.assetid: ed018aaf-8b10-46f9-828c-f9c092dc7609
ms.openlocfilehash: a84ae21b60d87971cb2f7b758dd369b4078607e6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62199211"
---
# <a name="using-cstring"></a>CString 사용

이 섹션의 항목에서는 `CString`을 사용한 프로그래밍 방법에 대해 설명합니다. 에 대 한 참조 설명서는 `CString` 클래스에 대 한 설명서를 참조 하십시오 [CStringT](../atl-mfc-shared/reference/cstringt-class.md)합니다.

`CString`을 사용하려면 `atlstr.h` 헤더를 포함합니다.

합니다 `CString`, `CStringA`, 및 `CStringW` 클래스는 호출 하는 클래스 템플릿의 특수화 [CStringT](../atl-mfc-shared/reference/cstringt-class.md) 지 원하는 문자 데이터 형식을 기반으로 합니다.

`CStringW` 개체를 포함 합니다 **wchar_t** 입력 하 고 유니코드 문자열을 지원 합니다. A `CStringA` 개체를 포함 합니다 **char** 형식 및 지원 싱글바이트 및 멀티 바이트 (MBCS) 문자열. `CString` 개체 중 하나를 지원 합니다 **char** 형식 또는 `wchar_t` MBCS 기호나 유니코드 기호와 컴파일 타임에 정의 되었는지 여부에 따라 형식입니다.

`CString` 개체는 `CStringData` 개체에 문자 데이터를 보관합니다. `CString` C 스타일 NULL로 끝나는 문자열을 허용합니다. `CString` 추적 문자열 길이가 더 빠른 성능을 제공 하지만 또한 LPCWSTR의 변환을 지원 하기 위해 저장 된 문자 데이터의 NULL 문자를 유지 합니다. `CString` C 스타일 문자열로 내보낼 때 null 종결자를 포함 합니다. 다른 위치에서 NULL을 삽입할 수 있습니다는 `CString`, 예기치 않은 결과 생성할 수 있습니다.

`CAtlString`, `CAtlStringA` 및 `CAtlStringW` 문자열 클래스 집합은 MFC 라이브러리에 연결하지 않고 사용할 수 있습니다(CRT 지원 포함/미포함).

`CString`은 네이티브 프로젝트에 사용됩니다. 관리 코드(C++/CLI) 프로젝트에는 `System::String`을 사용합니다.

`CString`, `CStringA` 또는 `CStringW`에서 현재 제공하는 것보다 많은 기능을 추가하려면 추가 기능이 포함된 `CStringT`를 만들어야 합니다.

다음 코드는 `CString`을 만들어 표준 출력으로 인쇄하는 방법을 보여줍니다.

```cpp
#include <atlstr.h>

int main() {
    CString aCString = CString(_T("A string"));
    _tprintf(_T("%s"), (LPCTSTR) aCString);
}
```

## <a name="in-this-section"></a>섹션 내용

[기본 CString 작업](../atl-mfc-shared/basic-cstring-operations.md)<br/>
C 리터럴 문자열에서 개체를 만들고, `CString`의 개별 문자에 액세스하고, 두 개체를 연결하고, `CString` 개체를 비교하는 작업을 포함한 기본 `CString` 작업을 설명합니다.

[문자열 데이터 관리](../atl-mfc-shared/string-data-management.md)<br/>
`CString`에서 유니코드 및 MBCS를 사용하는 방법을 설명합니다.

[CString 의미 체계](../atl-mfc-shared/cstring-semantics.md)<br/>
`CString` 개체를 사용하는 방법을 설명합니다.

[C 스타일 문자열 관련 CString 작업](../atl-mfc-shared/cstring-operations-relating-to-c-style-strings.md)<br/>
C 스타일의 null로 종료되는 문자열과 같은 `CString` 개체의 콘텐츠를 조작하는 방법을 설명합니다.

[BSTR에 대해 메모리 할당 및 해제](../atl-mfc-shared/allocating-and-releasing-memory-for-a-bstr.md)<br/>
메모리를 사용 하 여 BSTR 및 COM 개체에 대해 설명 합니다.

[CString 예외 정리](../atl-mfc-shared/cstring-exception-cleanup.md)<br/>
MFC 3.0 이상에서는 명시적 정리가 더 이상 필요하지 않은 이유에 대해 설명합니다.

[CString 인수 전달](../atl-mfc-shared/cstring-argument-passing.md)<br/>
CString 개체를 함수에 전달하고 함수에서 `CString` 개체를 반환하는 방법을 설명합니다.

[유니코드 및 멀티바이트 문자 집합(MBCS) 지원](../atl-mfc-shared/unicode-and-multibyte-character-set-mbcs-support.md)<br/>
유니코드 및 MBCS가 지원되도록 MFC를 설정하는 방법을 설명합니다.

## <a name="reference"></a>참조

[CStringT](../atl-mfc-shared/reference/cstringt-class.md)<br/>
`CStringT` 클래스에 대한 참조 정보를 제공합니다.

[CSimpleStringT 클래스](../atl-mfc-shared/reference/csimplestringt-class.md)<br/>
`CSimpleStringT` 클래스에 대한 참조 정보를 제공합니다.

## <a name="related-sections"></a>관련 단원

[문자열 (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)<br/>
문자열 데이터를 관리하는 여러 방법을 설명하는 항목에 대한 링크를 제공합니다.

[문자열 (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)
