---
title: CStringT를 사용 하 여 문자열 클래스 내보내기
ms.date: 11/04/2016
helpviewer_keywords:
- CStringT class, exporting strings
ms.assetid: bdfc441e-8d2a-461c-9885-46178066c09f
ms.openlocfilehash: a4ee73d2ae5cfb7bf9834fb23eed8470b7d29445
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57750235"
---
# <a name="exporting-string-classes-using-cstringt"></a>CStringT를 사용 하 여 문자열 클래스 내보내기

과거에는 MFC 개발자가에서 파생 된 `CString` 를 자체 문자열 클래스를 특수화 합니다. Microsoft Visual c + +.net (MFC 8.0)는 [CString](../atl-mfc-shared/using-cstring.md) 클래스 라는 템플릿 클래스로 대체 되었습니다 [CStringT](../atl-mfc-shared/reference/cstringt-class.md)합니다. 이 같은 여러 이점을 제공 합니다.

- MFC를 허용 하기 `CString` 큰 MFC 정적 라이브러리 또는 DLL에 연결 하지 않고 프로젝트 ATL에서 사용 하는 클래스입니다.

- 새 `CStringT` 템플릿 클래스를 사용자 지정할 수 있습니다 `CString` c + + 표준 라이브러리의 템플릿에 유사한 문자 특성을 지정 하는 템플릿 매개 변수를 사용 하 여 동작 합니다.

- 사용 하 여 DLL에서 고유한 문자열 클래스를 내보내면 `CStringT`, 컴파일러도 자동으로 내보냅니다.는 `CString` 기본 클래스입니다. 하므로 `CString` 템플릿 클래스는 그 자체가 컴파일러에서 인식 하지 않는 한 컴파일러를 사용 하 여 인스턴스화할 수 있습니다는 `CString` DLL에서 가져왔습니다. 마이그레이션한 경우 프로젝트를 Visual c + + 6.0에서에서 Visual c + +.net, 보았을 링커에서 기호 오류 곱하기 정의한 `CString` 의 충돌 때문에 `CString` 로컬로 인스턴스화된 버전과 DLL에서 가져온입니다. 이 작업을 수행 하는 적절 한 방법은 아래 설명 되어 있습니다.

다음 시나리오는 여러 번 정의 된 클래스에 대 한 기호 오류를 생성 하도록 링커에 발생 합니다. 내보내는 경우를 가정 된 `CString`-파생 클래스 (`CMyString`)는 MFC 확장 DLL에서에서:

[!code-cpp[NVC_MFC_DLL#6](../atl-mfc-shared/codesnippet/cpp/exporting-string-classes-using-cstringt_1.cpp)]

소비자 코드를 사용 하 여 혼합 `CString` 고 `CMyString`입니다. "MyString.h" 미리 컴파일된 헤더 및 일부 사용에 포함 되지 않습니다 `CString` 되지 않은 `CMyString` 표시 합니다.

사용 한다고 가정 합니다 `CString` 및 `CMyString` Source1.cpp 및 Source2.cpp 별도 소스 파일에는 클래스입니다. Source1.cpp를 사용 하 여 `CMyString` 및 #include MyString.h 합니다. Source2.cpp를 사용 하 여 `CString`, 하는데 호환 되지 않으면 #include MyString.h 합니다. 이 경우 링커는 불만 `CStringT` 되 고 여러 번 정의 되었습니다. 이 문제의 원인은 `CString` 둘 다를 내보내는 DLL에서 가져온 되 `CMyString`를 통해 컴파일러에서 로컬로 인스턴스화합니다를 `CStringT` 템플릿.

이 문제를 해결 하려면 다음을 수행 합니다.

내보낼 `CStringA` 고 `CStringW` (및 필요한 기본 클래스가) MFC90에서. DLL입니다. MFC를 포함 하는 프로젝트는 항상 내보낸 MFC DLL 사용 `CStringA` 고 `CStringW`이전 MFC 구현 에서처럼 합니다.

만든 다음 사용 하 여 내보낼 수 있는 파생된 클래스는 `CStringT` 템플릿을으로 `CStringT_Exported` 예를 들어 아래는:

[!code-cpp[NVC_MFC_DLL#7](../atl-mfc-shared/codesnippet/cpp/exporting-string-classes-using-cstringt_2.cpp)]

AfxStr.h, 이전으로 바꿉니다 `CString`, `CStringA`, 및 `CStringW` 다음과 같은 형식 정의:

[!code-cpp[NVC_MFC_DLL#8](../atl-mfc-shared/codesnippet/cpp/exporting-string-classes-using-cstringt_3.cpp)]

가지 몇 가지 주의 사항이 있습니다.

- 내보낼 수 없습니다 `CStringT` 자체는 특수 한 내보내려면 ATL 전용 프로젝트 발생할 수 있으므로 `CStringT` 클래스입니다.

- 파생 된 클래스를 내보낼 수를 사용 하 여 `CStringT` 다시 구현 하지 않아도 최소화 `CStringT` 기능입니다. 추가 코드는 생성자에 전달 하는 제한 된 `CStringT` 기본 클래스입니다.

- `CString`를 `CStringA`, 및 `CStringW` 만 표시 되어야 합니다 `__declspec(dllexport/dllimport)` MFC를 사용 하 여 작성 하는 경우 DLL을 공유 합니다. 경우에 MFC 정적 라이브러리를 사용 하 여 연결 하지로 표시 해야 이러한 클래스 내보내는; 사용이 고, 내부 그렇지 `CString`, `CStringA`, 및 `CStringW` 사용자 Dll 내에서 표시 `CString` 내보내는 방법으로 합니다.

## <a name="related-topics"></a>관련 항목

[CStringT 클래스](../atl-mfc-shared/reference/cstringt-class.md)

## <a name="see-also"></a>참고자료

[CStringT 사용](../atl-mfc-shared/using-cstringt.md)<br/>
[CString 사용](../atl-mfc-shared/using-cstring.md)
