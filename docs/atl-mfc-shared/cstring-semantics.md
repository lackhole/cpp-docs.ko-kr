---
title: CString 의미 체계
ms.date: 11/04/2016
helpviewer_keywords:
- semantics in Cstring
- CString objects, assignment semantics
- assignment statements, assigning CString objects
ms.assetid: d4023480-526f-499a-85f6-324b4de5b85f
ms.openlocfilehash: b5398f8a0f17ffcc93c7f5f6158ecc56606e9279
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57750183"
---
# <a name="cstring-semantics"></a>CString 의미 체계

경우에 [CString](../atl-mfc-shared/reference/cstringt-class.md) 개체는 증가할 수 있는 동적 개체, 기본 제공 기본 유형 및 단순 클래스와 같은 하 게 작동 합니다. 각 `CString` 개체 고유 값을 나타냅니다. `CString` 개체는 실제 문자열로 아니라 문자열에 대 한 포인터의 생각해 야 합니다.

하나를 할당 `CString` 다른 개체입니다. 그러나 수정 하면 두 가지 `CString` 개체를 다른 `CString` 개체 수정 되지 않으면 다음 예제와 같이:

[!code-cpp[NVC_ATLMFC_Utilities#188](../atl-mfc-shared/codesnippet/cpp/cstring-semantics_1.cpp)]

참고 예제에서는 두 `CString` 동일한 문자열 멀 기 때문에 개체 "equal" 라고 합니다. `CString` 클래스에는 같음 연산자 오버 로드 (`==`) 두 개를 비교 하 `CString` 개체 id (주소) 하는 대신 해당 값 (내용)에 기반 합니다.

## <a name="see-also"></a>참고자료

[문자열 (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)
