---
title: CComBSTR을 사용한 프로그래밍(ATL)
ms.date: 11/04/2016
helpviewer_keywords:
- CComBSTR class, programming with
- Unicode, using CComBSTR [ATL]
ms.assetid: d3bd0851-d132-4be9-9c4c-6ccba17acb2b
ms.openlocfilehash: 806d23730a0657fc1e0c154e20dc9abd62f7e8af
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62261815"
---
# <a name="programming-with-ccombstr-atl"></a>CComBSTR을 사용한 프로그래밍(ATL)

ATL 클래스 [CComBSTR](../atl/reference/ccombstr-class.md) BSTR 데이터 형식 래퍼를 제공 합니다. 하지만 `CComBSTR` 는 유용한 도구, 주의 필요로 하는 몇 가지 경우가 있습니다.

- [변환 문제](#programmingwithccombstr_conversionissues)

- [범위 문제](#programmingwithccombstr_scopeissues)

- [CComBSTR 개체를 명시적으로 해제](#programmingwithccombstr_explicitlyfreeing)

- [CComBSTR 개체를 사용 하 여 루프에서](#programmingwithccombstr_usingloops)

- [메모리 누수 문제](#programmingwithccombstr_memoryleaks)

##  <a name="programmingwithccombstr_conversionissues"></a> 변환 문제

하지만 여러 `CComBSTR` 메서드는 자동으로 변환 ANSI 문자열 인수로 유니코드, 메서드는 항상 유니코드 형식으로 문자열을 반환 합니다. 출력 문자열 다시 ANSI로 변환 하려면 ATL 변환 클래스를 사용 합니다. ATL 변환 클래스에 대 한 자세한 내용은 참조 하세요. [ATL 및 MFC 문자열 변환 매크로](reference/string-conversion-macros.md)합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#114](../atl/codesnippet/cpp/programming-with-ccombstr-atl_1.cpp)]

문자열 리터럴을 사용 하 여 수정 하는 경우는 `CComBSTR` 개체, 와이드 문자 문자열을 사용 합니다. 이렇게 하면 불필요 한 변환을 줄어듭니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#115](../atl/codesnippet/cpp/programming-with-ccombstr-atl_2.cpp)]

##  <a name="programmingwithccombstr_scopeissues"></a> 범위 문제

모든 커지긴 클래스와 마찬가지로 `CComBSTR` 범위를 벗어나면 해당 리소스를 해제 합니다. 함수에 대 한 포인터를 반환 하는 경우는 `CComBSTR` 문자열 포인터가 이미 해제 된 메모리 참조는 같은 문제가 수반 될 수 있습니다이 있습니다. 이 경우에 사용 된 `Copy` 메서드를 아래와 같이 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#116](../atl/codesnippet/cpp/programming-with-ccombstr-atl_3.cpp)]

##  <a name="programmingwithccombstr_explicitlyfreeing"></a> CComBSTR 개체를 명시적으로 해제

에 포함 된 문자열을 명시적으로 해제할 수 있기를 `CComBSTR` 범위를 벗어나기 전에 개체입니다. 문자열이 해제 됩니다 하는 경우는 `CComBSTR` 개체가 잘못 되었습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#117](../atl/codesnippet/cpp/programming-with-ccombstr-atl_4.cpp)]

##  <a name="programmingwithccombstr_usingloops"></a> CComBSTR 개체를 사용 하 여 루프에서

로 `CComBSTR` 클래스와 같은 특정 작업을 수행 하는 버퍼를 할당 합니다 `+=` 연산자 또는 `Append` 메서드인 것은 바람직하지 긴밀 한 루프 내에서 문자열 조작 수행 하는 합니다. 이러한 상황에서는 `CStringT` 더 나은 성능을 제공 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#118](../atl/codesnippet/cpp/programming-with-ccombstr-atl_5.cpp)]

##  <a name="programmingwithccombstr_memoryleaks"></a> 메모리 누수 문제

초기화의 주소를 전달 `CComBSTR` 서 함수에는 **[out]** 매개 변수는 메모리 누수가 발생 합니다.

아래 예제에서는 문자열에 할당할 때 문자열을 포함할 `"Initialized"` 때 손실 됩니다 함수 `MyGoodFunction` 문자열을 대체 합니다.

[!code-cpp[NVC_ATL_Utilities#119](../atl/codesnippet/cpp/programming-with-ccombstr-atl_6.cpp)]

누수를 방지 하려면 호출을 `Empty` 기존 메서드 `CComBSTR` 주소를 전달 하기 전에 개체를 **[out]** 매개 변수입니다.

동일한 코드를 함수 매개 변수 되었으면 누수가 발생 하지는 유의 **[에서 out]** 합니다.

## <a name="see-also"></a>참고자료

[개념](../atl/active-template-library-atl-concepts.md)<br/>
[CStringT 클래스](../atl-mfc-shared/reference/cstringt-class.md)<br/>
[wstring](../standard-library/basic-string-class.md)<br/>
[문자열 변환 매크로](../atl/reference/string-conversion-macros.md)
