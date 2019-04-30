---
title: 뷰 사용
ms.date: 11/04/2016
helpviewer_keywords:
- interacting with users and role of view class [MFC]
- drawing [MFC], data
- rendering data
- view classes [MFC], role in managing user interaction
- CView class [MFC], view architecture
- MFC, views
- views [MFC], using
- painting data
- user input [MFC], interpreting through view class [MFC]
- view classes [MFC], role in displaying application data
ms.assetid: dc3de6ad-5c64-4317-8f10-8bdcc38cdbd5
ms.openlocfilehash: 81668f7409f2b1a4480bde958dc06ce1156e03fe
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62411424"
---
# <a name="using-views"></a>뷰 사용

뷰는 사용자에 게 문서의 데이터를 그래픽으로 표시 하 고을 받아들이고 사용자 입력을 문서에 대 한 작업으로 해석 됩니다. 뷰 클래스를 작성 작업 다음과 같습니다.

- 뷰 클래스의 쓰기 [OnDraw](../mfc/reference/cview-class.md#ondraw) 문서의 데이터를 렌더링 하는 멤버 함수입니다.

- 뷰 클래스의 메시지 처리기 멤버 함수에 적절 한 Windows 메시지 및 메뉴 항목과 같은 사용자 인터페이스 개체를 연결 합니다.

- 사용자 입력을 해석 하는 이러한 처리기를 구현 합니다.

다른 재정의 해야 하는 또한 `CView` 파생 된 뷰 클래스의 멤버 함수입니다. 재정의 하려는 특히 [OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate) 뷰에 대 한 특별 한 초기화를 수행 하 고 [OnUpdate](../mfc/reference/cview-class.md#onupdate) 뷰 자신을 다시 그리면 직전 필요한 특별 한 처리 작업을 수행할. 다중 페이지 문서도 재정의 해야 합니다 [OnPreparePrinting](../mfc/reference/cview-class.md#onprepareprinting) 개수 인쇄할 페이지 및 기타 정보를 사용 하 여 인쇄 대화 상자를 초기화 합니다. 재정의 하는 방법은 `CView` 클래스를 참조 하는 멤버 함수 [CView](../mfc/reference/cview-class.md) 에 *MFC 참조*합니다.

## <a name="what-do-you-want-to-know-more-about"></a>자세히 알아볼 항목

- [MFC에서 사용할 수 있는 파생 된 뷰 클래스](../mfc/derived-view-classes-available-in-mfc.md)

- [뷰에 그리기](../mfc/drawing-in-a-view.md)

- [뷰를 통해 사용자 입력 해석](../mfc/interpreting-user-input-through-a-view.md)

- [인쇄에서 뷰의 역할](../mfc/role-of-the-view-in-printing.md)

- [스크롤 뷰 및 크기 조정](../mfc/scrolling-and-scaling-views.md)

- [초기화 하 고 문서 및 뷰 정리](../mfc/initializing-and-cleaning-up-documents-and-views.md)

## <a name="see-also"></a>참고자료

[문서/뷰 아키텍처](../mfc/document-view-architecture.md)<br/>
[CFormView 클래스](../mfc/reference/cformview-class.md)<br/>
[레코드 뷰(MFC Data Access)](../data/record-views-mfc-data-access.md)<br/>
[Serialization 메커니즘 건너뛰기](../mfc/bypassing-the-serialization-mechanism.md)
