---
title: BSTR에 대해 메모리 할당 및 해제
ms.date: 11/04/2016
f1_keywords:
- bstr
helpviewer_keywords:
- BSTRs, memory allocation
- memory deallocation, string memory
- memory [C++], releasing
- memory allocation, BSTRs
- memory deallocation, BSTR memory
- strings [C++], releasing
ms.assetid: 98041e29-3442-4a02-b425-7a4a13e9cc84
ms.openlocfilehash: adc3e1efd032bb3e3e45381da24c5a5b59852375
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62216971"
---
# <a name="allocating-and-releasing-memory-for-a-bstr"></a>BSTR에 대해 메모리 할당 및 해제

만들 때 `BSTR`의COM 개체 간에 전달 하 고 메모리 누수를 방지 하기 위해 사용 하는 메모리를 처리 하는 방법에 주의 해야 합니다. 경우는 `BSTR` 인터페이스 내에서 필요한 유지 되며,이 사용 하 여 완료 되 면 해당 메모리 해제 해야 합니다. 그러나 경우는 `BSTR` 인터페이스에서 통과 수신 개체는 메모리 관리를 담당 합니다.

에 대 한 메모리 할당 및 해제에 대 한 규칙을 할당 하는 일반적으로 `BSTR`s는 다음과 같습니다.

- 필요한 함수를 호출 하는 경우는 `BSTR` 인수에 대 한 메모리를 할당 해야 합니다 `BSTR` 호출 하기 전에 나중에 해제 합니다. 예를 들어:

   [!code-cpp[NVC_ATLMFC_Utilities#192](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_1.cpp)]

   [!code-cpp[NVC_ATLMFC_Utilities#193](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_2.cpp)]

- 반환 하는 함수를 호출 하는 경우는 `BSTR`, 문자열을 직접 해제 해야 합니다. 예를 들어:

   [!code-cpp[NVC_ATLMFC_Utilities#194](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_3.cpp)]

   [!code-cpp[NVC_ATLMFC_Utilities#195](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_4.cpp)]

- 반환 하는 함수를 구현 하는 경우는 `BSTR`문자열이 할당 되지만 해제 하지 마세요. 수신 함수는 메모리를 해제 합니다. 예를 들어:

   [!code-cpp[NVC_ATLMFC_Utilities#196](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_5.cpp)]

## <a name="see-also"></a>참고자료

[문자열 (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)<br/>
[CStringT::AllocSysString](../atl-mfc-shared/reference/cstringt-class.md#allocsysstring)<br/>
[SysAllocString](/windows/desktop/api/oleauto/nf-oleauto-sysallocstring)<br/>
[SysFreeString](/windows/desktop/api/oleauto/nf-oleauto-sysfreestring)
