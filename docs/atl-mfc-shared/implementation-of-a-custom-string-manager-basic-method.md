---
title: 사용자 지정 문자열 관리자 구현 (기본 방법)
ms.date: 11/04/2016
helpviewer_keywords:
- IAtlStringMgr class, using
ms.assetid: eac5d13e-cbb4-4e82-b01e-f5f2dbcb962a
ms.openlocfilehash: c30c08217a09f600f8801bec9f50c4341e983a6b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62235903"
---
# <a name="implementation-of-a-custom-string-manager-basic-method"></a>사용자 지정 문자열 관리자 구현 (기본 방법)

문자열 데이터는 ATL 제공를 사용 하는 것에 대 한 메모리 할당 체계를 사용자 지정 하는 가장 쉬운 방법은 `CAtlStringMgr` 클래스 이지만 고유한 메모리 할당 루틴을 제공 합니다. 에 대 한 생성자 `CAtlStringMgr` 단일 매개 변수:에 대 한 포인터를 `IAtlMemMgr` 개체입니다. `IAtlMemMgr` 힙에 대 한 제네릭 인터페이스를 제공 하는 추상 기본 클래스 이며 사용 하는 `IAtlMemMgr` 인터페이스는 `CAtlStringMgr` 할당을 다시 할당 하 고 문자열 데이터를 저장 하는 데 사용 된 메모리를 해제 합니다. 구현 하거나는 `IAtlMemMgr` 인터페이스를 직접, 또는 다섯 가지 ATL에서 제공한 메모리 관리자 클래스 중 하나를 사용 합니다. ATL에서 제공한 메모리 관리자를 단순히 기존 메모리 할당 기능을 래핑합니다.

- [CCRTHeap](../atl/reference/ccrtheap-class.md) 표준 CRT 힙 함수를 래핑합니다 ([malloc](../c-runtime-library/reference/malloc.md)하십시오 [무료](../c-runtime-library/reference/free.md), 및 [realloc](../c-runtime-library/reference/realloc.md))

- [CWin32Heap](../atl/reference/cwin32heap-class.md) 사용 하 여 Win32 힙에 처리 래핑합니다 [HeapAlloc](/windows/desktop/api/heapapi/nf-heapapi-heapalloc)합니다 [HeapFree](/windows/desktop/api/heapapi/nf-heapapi-heapfree), 및 [HeapRealloc](/windows/desktop/api/heapapi/nf-heapapi-heaprealloc)

- [CLocalHeap](../atl/reference/clocalheap-class.md) Win32 Api를 래핑합니다. [LocalAlloc](/windows/desktop/api/winbase/nf-winbase-localalloc)하십시오 [LocalFree](/windows/desktop/api/winbase/nf-winbase-localfree), 및 [LocalRealloc](/windows/desktop/api/winbase/nf-winbase-localrealloc)

- [CGlobalHeap](../atl/reference/cglobalheap-class.md) Win32 Api를 래핑합니다. [GlobalAlloc](/windows/desktop/api/winbase/nf-winbase-globalalloc)하십시오 [GlobalFree](/windows/desktop/api/winbase/nf-winbase-globalfree), 및 [GlobalRealloc](/windows/desktop/api/winbase/nf-winbase-globalrealloc)합니다.

- [CComHeap](../atl/reference/ccomheap-class.md) COM 작업 할당자 Api를 래핑합니다. [CoTaskMemAlloc](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemalloc), [CoTaskMemFree](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemfree), and [CoTaskMemRealloc](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemrealloc)

가장 유용한 클래스는 문자열 메모리 관리를 위해 `CWin32Heap` 있으므로 여러 개의 독립적인 힙을 만들 수 있습니다. 예를 들어 문자열에 대 한 별도 힙에 사용 하려는 경우 다음을 수행할 수 있습니다.:

[!code-cpp[NVC_ATLMFC_Utilities#180](../atl-mfc-shared/codesnippet/cpp/implementation-of-a-custom-string-manager-basic-method_1.cpp)]

이 전용 string 관리자에 대 한 메모리 관리를 사용 하는 `CString` 변수를 매개 변수로 관리자에 대 한 포인터를 전달 합니다 `CString` 변수의 생성자:

[!code-cpp[NVC_ATLMFC_Utilities#181](../atl-mfc-shared/codesnippet/cpp/implementation-of-a-custom-string-manager-basic-method_2.cpp)]

## <a name="see-also"></a>참고자료

[CStringT를 사용한 메모리 관리](../atl-mfc-shared/memory-management-with-cstringt.md)
