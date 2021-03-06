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
ms.openlocfilehash: a7a82acff959d18dcadd3a2c8516a20d60a617d3
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69491411"
---
# <a name="allocating-and-releasing-memory-for-a-bstr"></a>BSTR에 대해 메모리 할당 및 해제

를 만들고 `BSTR`COM 개체 간에 전달 하는 경우 메모리 누수를 방지 하기 위해 사용 하는 메모리를 처리 해야 합니다. 가 `BSTR` 인터페이스 내에서 유지 되는 경우 작업을 완료 하면 메모리를 해제 해야 합니다. 그러나가 `BSTR` 인터페이스에서 통과 하면 수신 개체는 메모리 관리를 담당 합니다.

일반적으로 s에 `BSTR`할당 된 메모리를 할당 하 고 해제 하는 규칙은 다음과 같습니다.

- `BSTR` 인수가 필요한 함수를 호출 하는 경우에는 `BSTR` 먼저에 대 한 메모리를 할당 하 고 나중에 해제 해야 합니다. 예:

   [!code-cpp[NVC_ATLMFC_Utilities#192](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_1.cpp)]

   [!code-cpp[NVC_ATLMFC_Utilities#193](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_2.cpp)]

- 을 `BSTR`반환 하는 함수를 호출 하는 경우 문자열을 직접 해제 해야 합니다. 예:

   [!code-cpp[NVC_ATLMFC_Utilities#194](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_3.cpp)]

   [!code-cpp[NVC_ATLMFC_Utilities#195](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_4.cpp)]

- 을 `BSTR`반환 하는 함수를 구현 하는 경우 문자열을 할당 하지만 해제 하지는 않습니다. 함수가 수신 하는는 메모리를 해제 합니다. 예를 들어:

   [!code-cpp[NVC_ATLMFC_Utilities#196](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_5.cpp)]

## <a name="see-also"></a>참고자료

[문자열 (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)<br/>
[CStringT::AllocSysString](../atl-mfc-shared/reference/cstringt-class.md#allocsysstring)<br/>
[SysAllocString](/windows/win32/api/oleauto/nf-oleauto-sysallocstring)<br/>
[SysFreeString](/windows/win32/api/oleauto/nf-oleauto-sysfreestring)
