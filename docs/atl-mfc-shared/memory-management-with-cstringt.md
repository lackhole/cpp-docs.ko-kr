---
title: CStringT 사용한 메모리 관리
ms.date: 11/04/2016
f1_keywords:
- CStringT
- ATL::CStringT
- ATL.CStringT
helpviewer_keywords:
- CString objects, memory management
- memory [C++], usage
- IAtlStringMgr class, using
- strings [C++], custom memory management
- CFixedStringT class, description of
- strings [C++], memory management
- CStringT class, memory management
ms.assetid: 88b8342d-19b5-48c4-9cf6-e4c44cece21e
ms.openlocfilehash: 8f83b088becf97ca3d8779a537e42369b4a8c832
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62235200"
---
# <a name="memory-management-with-cstringt"></a>CStringT 사용한 메모리 관리

클래스 [CStringT](../atl-mfc-shared/reference/cstringt-class.md) 가변 길이 문자 문자열을 조작 하는 데 사용 하는 템플릿 클래스입니다. 이러한 문자열을 저장할 메모리를 할당 하 고 각 인스턴스와 연결 된 문자열 manager 개체를 통해 출시 `CStringT`합니다. MFC 및 ATL 제공의 기본 인스턴스 `CStringT`라는 `CString`를 `CStringA`, 및 `CStringW`, 다른 문자 형식의 문자열을 조작 하는 합니다. 이러한 문자 유형은 TCHAR로 형식의 **char**, 및 `wchar_t`, 각각. 이러한 기본 문자열 형식 (ATL)에서 프로세스 힙을 또는 MFC의 CRT 힙 메모리를 할당 하는 문자열 관리자를 사용 합니다. 일반적인 응용 프로그램의 경우 이러한 메모리 할당 체계가으로 충분 합니다. 그러나 코드 집약적인 기본 메모리 관리자를 최적으로 수행 되지 않을 수 있습니다 문자열 (또는 다중 스레드 코드) 사용 합니다. 이 항목의 기본 메모리 관리 동작을 재정의 하는 방법에 설명 합니다 `CStringT`, 당면한 작업에 대 한 액세스에 최적화 된 특히 할당자를 작성 합니다.

- [사용자 지정 문자열 관리자 구현(기본 방법)](../atl-mfc-shared/implementation-of-a-custom-string-manager-basic-method.md)

- [힙 경합 방지](../atl-mfc-shared/avoidance-of-heap-contention.md)

- [사용자 지정 문자열 관리자 구현(고급 방법)](../atl-mfc-shared/implementation-of-a-custom-string-manager-advanced-method.md)

- [CFixedStringT: 사용자 지정 문자열 관리자의 예](../atl-mfc-shared/cfixedstringt-example-of-a-custom-string-manager.md)

## <a name="see-also"></a>참고자료

[CustomString 샘플](../overview/visual-cpp-samples.md)
