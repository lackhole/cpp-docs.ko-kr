---
title: 유니코드 프로그래밍 요약
ms.date: 11/04/2016
helpviewer_keywords:
- Unicode [C++], programming with
- Unicode [C++], MFC and C run-time functions
ms.assetid: a4c9770f-6c9c-447c-996b-980920288bed
ms.openlocfilehash: 130c9027a882de2aae7fb339e4761b0cc81b3a6a
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57747958"
---
# <a name="unicode-programming-summary"></a>유니코드 프로그래밍 요약

MFC 및 C 런타임의 유니코드 지원을 이용하려면 다음의 내용을 숙지합니다.

- `_UNICODE` 상수를 정의합니다.

   `_UNICODE` 상수를 미리 정의하고 프로그램을 빌드합니다.

- 진입점을 지정 합니다.

   에 **고급** 페이지의 **링커** 프로젝트의 폴더 [속성 페이지](../ide/property-pages-visual-cpp.md) 대화 상자에서를 **진입점** 기호`wWinMainCRTStartup`.

- 이식 가능한 런타임 함수 및 형식을 사용합니다.

   유니코드 문자열 처리에 적합한 C 런타임 함수를 사용합니다. 와이드 문자 기반으로 `wcs`로 시작하는 함수를 사용할 수도 있지만 추후 국제적으로 사용 가능하도록 쉽게 이식하기 위해 `_TCHAR` 매크로를 우선 고려합니다. 이 매크로 기반 함수는 모두 앞이 `_tcs`로 시작하며 `str`로 시작하는 문자열 관련 함수군을 대체합니다. 이 함수들은 *런타임 라이브러리 참조*의 [국제화](../c-runtime-library/internationalization.md) 지원 섹션에서 자세히 설명합니다. 자세한 내용은 [tchar.h의 제네릭 텍스트 매핑](../text/generic-text-mappings-in-tchar-h.md)을 참조하십시오.

   `_TCHAR`와 관련된 이식 가능한 데이터 형식은 [유니코드 지원](../text/support-for-unicode.md)에서 다루고 있습니다.

- 리터럴 문자열을 올바르게 처리합니다.

   Visual C++ 컴파일러는 다음과 같은 코드를 아래와 같은 리터럴 문자열로 해석합니다.

    ```cpp
    L"this is a literal string"
    ```

   이것은 유니코드 문자의 문자열을 의미합니다. 리터럴 문자에 대하여 동일한 접두사를 사용할 수 있습니다. 리터럴 문자열은 일반적으로 `_T` 매크로를 사용하여 유니코드 환경에서는 문자열을 유니코드로, 유니코드가 아닌 환경에서는 멀티바이트 문자 집합을 포함하는 ANSI문자열로 취급할 수 있습니다. 예를 들어 이렇게 직접 문자열을 넘기는 대신,

    ```cpp
    pWnd->SetWindowText( "Hello" );
    ```

   매크로를 이용하면

    ```cpp
    pWnd->SetWindowText( _T("Hello") );
    ```

   `_UNICODE` 상수가 정의된 환경에서 `_T` 매크로는 `L` 접두사가 붙어 리터럴 문자열이 변환되고, 그렇지 않은 경우 `_T` 매크로는 'L' 접두사 없는 일반적인 ANSI 및 멀티바이트 문자 집합 기반 문자열로 취급합니다.

    > [!TIP]
    >  `_T`와 `_TEXT`는 동일한 매크로입니다.

- 함수에 문자열의 길이를 전달할 때 주의하세요.

   어떤 함수는 인수로 문자열을 구성하는 문자의 갯수를 원합니다. 어떤 함수는 바이트 수를 인수로 받습니다. 예를 들어 `_UNICODE` 상수가 정의된 환경에서 `CArchive` 개체의 맴버를 다음과 같이 호출하면 올바르게 작동하지 않습니다. `str` 변수는 `CString` 형식입니다.

    ```cpp
    archive.Write( str, str.GetLength( ) );    // invalid
    ```

   유니코드 응용 프로그램에서 길이는 문자의 갯수지만, 바이트 크기를 의미하지 않습니다. 각 문자는 와이드 문자로 2바이트를 차지합니다. 따라서 다음과 같이 사용해야 합니다.

    ```cpp
    archive.Write( str, str.GetLength( ) * sizeof( _TCHAR ) );    // valid
    ```

   바이트 크기를 잘 계산해서 인자로 전달합니다.

   MFC 맴버 함수들은 바이트 크기를 받지 않고 문자 갯수를 받기 때문에 추가적인 코딩이 필요 없습니다.

    ```cpp
    pDC->TextOut( str, str.GetLength( ) );
    ```

   `CDC::TextOut`은 바이트 크기가 아닌 문자 갯수를 받습니다.

- [fopen_s, _wfopen_s](../c-runtime-library/reference/fopen-s-wfopen-s.md) 함수를 사용하여 유니코드 파일을 열 수 있습니다.

요약하자면, MFC와 런타임 라이브러리는 유니코드 프로그래밍을 위해 다음과 같은 기법들을 지원합니다.

- 데이터베이스 클래스 멤버 함수를 제외한 모든 MFC 함수 및 `CString`은 유니코드를 지원합니다. `CString`은 유니코드와 ANSI간 변환 함수를 제공합니다.

- 런타임 라이브러리는 모든 문자열 처리 함수의 유니코드 버전을 제공합니다. (런타임 라이브러리는 유니코드 및 멀티바이트 문자 집합(MBCS) 버전과 이를 쉽게 이식할 수 있는 방법 또한 제공하며, 이는 `_tcs` 매크로입니다.)

- tchar.h에서는 이식 가능한 데이터 형식을 제공하며 리터럴 문자열과 문자를 쉽게 이식하기 위한 `_T` 매크로를 제공합니다. 자세한 내용은 [tchar.h를 이용한 제네릭 텍스트 매핑](../text/generic-text-mappings-in-tchar-h.md)을 참조합니다.

- 런타임 라이브러리의 `main`의 와이드 문자 기반 버전을 제공합니다. `wmain`을 사용하여 응용 프로그램이 바로 유니코드를 인식할 수 있게 만드세요.

## <a name="see-also"></a>참고자료

[유니코드 지원](../text/support-for-unicode.md)
