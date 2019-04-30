---
title: 배열, 목록 및 맵 클래스
ms.date: 11/04/2016
f1_keywords:
- vc.classes.mfc
helpviewer_keywords:
- arrays [MFC], classes
- list classes [MFC]
- collection classes [MFC], maps
- map classes [MFC]
- collection classes [MFC], lists
ms.assetid: 81a13a7f-0c2c-4efd-b6bb-b4e624a0743d
ms.openlocfilehash: b89b99abb79fe689274f9e0b89a85bb33643d324
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62394626"
---
# <a name="array-list-and-map-classes"></a>배열, 목록 및 맵 클래스

집계 데이터의 처리에 대 한 클래스 라이브러리는 컬렉션 클래스의 그룹-목록, 배열 및 맵 등 다양 한 개체 및 미리 정의 된 형식이 포함 될 수 있는 합니다. 컬렉션을 동적으로 크기가 조정 됩니다. 또는 Windows 용으로 작성 하는지 여부를 이러한 클래스를 모든 프로그램에서 사용할 수 있습니다. 그러나 이러한는 응용 프로그램 프레임 워크에서 문서 클래스를 정의 하는 데이터 구조를 구현 하기 위한 가장 유용 합니다. 이러한 특수 한 컬렉션 클래스를 파생 시킬 즉시 또는 템플릿 클래스를 기반으로 만들 수 있습니다. 이러한 방법에 대 한 자세한 내용은 문서 참조 [컬렉션](../mfc/collections.md)합니다. 목록을 템플릿 컬렉션 클래스에 대 한 문서를 참조 [배열, 목록 및 맵에 대 한 템플릿 클래스](../mfc/template-classes-for-arrays-lists-and-maps.md)합니다.

배열은 1 차원 데이터 구조를 메모리에 연속적으로 저장 됩니다. 요소의 인덱스는 요소의 크기를 곱하여 배열의 기준 주소에 결과 추가 하 여 지정 된 요소의 메모리 주소를 계산할 수 있습니다 하므로 매우 빠른 임의 액세스를 지원 합니다. 하지만 배열은 삽입할 요소에 대 한 공간을 만들기 위해 이동 해야 하는 삽입 된 요소 이후 지난 전체 배열의 배열 요소를 삽입 해야 할 경우 소모 합니다. 배열 증가 하 고 필요에 따라 축소할 수 있습니다.

목록 배열 유사 하지만 매우 다른 방식으로 저장 됩니다. 목록의 각 요소에는 이중 연결된 목록이 있으므로 이전 및 다음 요소에 대 한 포인터도 포함 됩니다. 추가 또는 반하므로 이렇게만 몇 가지 변경 항목을 삭제 하려면 매우 빠릅니다. 그러나 목록을 검색 수 비용이 많이 드는 목록의 끝 중 하나에 시작 되도록 모든 검색 해야 하기 때문입니다.

지도는 데이터 값에 키 값을 연결합니다. 예를 들어 맵의 키 문자열 및 데이터를 목록에 대 한 포인터를 수 있습니다. 연결 된 특정 문자열 포인터를 제공 하는 맵을 주시기 합니다. 지도 키 조회에 대 한 해시 테이블을 사용 하기 때문에 지도 조회 속도가 빠릅니다. 항목 추가 및 삭제 빠른 이기도 합니다. Maps 보조 인덱스로 기타 데이터 구조를 사용 하 여 자주 사용 됩니다. MFC는 특수 한 유형의 지도 호출을 사용 하는 [메시지 맵을](../mfc/mapping-messages.md) Windows 메시지는 메시지에 대 한 처리기 함수에 대 한 포인터를 매핑할 합니다.

## <a name="see-also"></a>참고자료

[클래스 개요](../mfc/class-library-overview.md)
