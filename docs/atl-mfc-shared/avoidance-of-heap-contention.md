---
title: 힙 경합 방지
ms.date: 11/04/2016
helpviewer_keywords:
- heap contention
ms.assetid: 797129d7-5f8c-4b0e-8974-bb93217e9ab5
ms.openlocfilehash: 45510607a63759aad9444959716bef164eda1492
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62210003"
---
# <a name="avoidance-of-heap-contention"></a>힙 경합 방지

MFC와 ATL에서 제공 하는 기본 문자열 관리자는 전역 힙 기반으로 간단한 래퍼입니다. 이 전역 힙은 완벽 하 게 스레드로부터 안전, 즉 여러 스레드가 할당 되 고 힙의 손상 하지 않고 동시에 메모리를 확보 수 있습니다. 스레드 보안을 제공 하려면 힙에 자체에 대 한 액세스를 serialize 해야 합니다. 일반적으로 중요 섹션 또는 비슷한 잠금 메커니즘을 사용 하 여 수행 됩니다. 두 개의 스레드를 힙에 동시에 액세스 하려고 하는 때마다 하나의 스레드가 다른 스레드의 요청이 완료 될 때까지 차단 됩니다. 대부분의 응용 프로그램에 대 한이 상황은 드물게 발생 하 고 힙의 잠금 메커니즘이 성능에 미치는 영향은 매우 적습니다. 그러나 여러 스레드에서 힙에 자주 액세스 하는 응용 프로그램에 대 한 힙의 잠금에 대 한 경합 응용 프로그램을 실행 하는 경우 (여러 Cpu 사용 하 여 컴퓨터)에 단일 스레드 것 보다 더 느리게 발생할 수 있습니다.

사용 하는 응용 프로그램 [CStringT](../atl-mfc-shared/reference/cstringt-class.md) 힙 경합에 특히 취약 하기 때문에 대 한 작업 `CStringT` 개체 문자열 버퍼의 재할당을 필요한 경우가 많습니다.

스레드 간 힙 경합을 완화 하기 위해 한 가지 방법은 문자열 개인, 스레드 로컬 힙에서 할당 하는 각 스레드는 합니다. 문자열을 사용 하 여 할당 된 특정 스레드의 할당자 스레드 에서만 사용 되며, 할당자 스레드로부터 안전한 필요는 없습니다.

## <a name="example"></a>예제

아래 예제에서는 문자열의 해당 스레드에서 사용 하는 고유한 개인 스레드로부터 안전한 힙 할당 하는 스레드 프로시저를 보여 줍니다.

[!code-cpp[NVC_ATLMFC_Utilities#182](../atl-mfc-shared/codesnippet/cpp/avoidance-of-heap-contention_1.cpp)]

## <a name="comments"></a>설명

여러 스레드가 동일한 스레드 절차를 사용 하 여 실행 될 수 있지만 없기 때문에 각 스레드가 자체의 힙이 스레드 간에 경합이 없는 합니다. 또한 각 힙에 스레드로부터 안전 팩트 스레드의 복사본이 하나만 실행 하는 경우에 성능이 많이 향상을 제공 합니다. 동시 액세스 로부터 보호 하는 데 비용이 많이 드는 연동된 작업을 사용 하지 힙의 결과입니다.

더 복잡 한 스레드 프로시저에 대 한 스레드 로컬 저장소 (TLS) 슬롯에서 스레드의 문자열 관리자에 대 한 포인터를 저장 하는 것이 편리할 수 있습니다. 이렇게 하면 스레드 문자열 관리자에 액세스 하려면 스레드 프로시저에 의해 호출 함수도 있습니다.

## <a name="see-also"></a>참고자료

[CStringT를 사용한 메모리 관리](../atl-mfc-shared/memory-management-with-cstringt.md)
