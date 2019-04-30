---
title: 인쇄
ms.date: 11/04/2016
helpviewer_keywords:
- view classes [MFC], print operations
- documents [MFC], printing
- printing [MFC], from framework
- printing [MFC]
ms.assetid: be465e8d-b0c9-4fc5-9fa8-d10486064f76
ms.openlocfilehash: e0cd2d6d85cb9820b23495a003068994b13f9c85
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64339584"
---
# <a name="printing"></a>인쇄

Microsoft Windows 장치에 관계 없이 표시를 구현합니다. MFC에서 즉 동일한 그리기 호출에는 `OnDraw` 뷰 클래스의 멤버 함수는 디스플레이 프린터와 같은 다른 장치에서 그리기를 담당 합니다. 인쇄 미리 보기에 대 한 대상 장치는 시뮬레이트된 프린터 출력을 표시 합니다.

##  <a name="_core_your_role_in_printing_vs.._the_framework.92.s_role"></a> 프레임 워크의 역할 및 인쇄에서의 역할

뷰 클래스에 책임은 다음과 같습니다.

- 문서의 페이지 수는 프레임 워크에 알립니다.

- 지정 된 페이지를 인쇄 하려면를 묻는 메시지가 나타나면 문서의 해당 부분을 그립니다.

- 할당 하 고 모든 글꼴 또는 인쇄에 필요한 기타 그래픽 장치 GDI (인터페이스) 리소스의 할당을 취소 합니다.

- 필요한 경우 보내서 페이지 별로에서 인쇄 방향을 변경 하려면, 예를 들어 지정된 된 페이지를 인쇄 하기 전에 프린터 모드를 변경 하는 데 필요한 코드를 이스케이프 합니다.

프레임 워크의 책임은 다음과 같습니다.

- 표시 된 **인쇄** 대화 상자.

- 만들기는 [CDC](../mfc/reference/cdc-class.md) 프린터에 대 한 개체입니다.

- 호출을 [StartDoc](../mfc/reference/cdc-class.md#startdoc) 하 고 [EndDoc](../mfc/reference/cdc-class.md#enddoc) 의 멤버 함수는 `CDC` 개체입니다.

- 반복적으로 호출 합니다 [StartPage](../mfc/reference/cdc-class.md#startpage) 멤버 함수는 `CDC` 개체, 페이지, 출력할 및 호출 뷰 클래스를 알리기 위해를 [EndPage](../mfc/reference/cdc-class.md#endpage) 멤버 함수는 `CDC` 개체.

- 적절 한 시간에서 보기의 재정의 가능 함수를 호출 합니다.

다음 문서를 프레임 워크에서 인쇄 및 인쇄 미리 보기를 지원 하는 방법을 설명 합니다.

### <a name="what-do-you-want-to-know-more-about"></a>자세히 알아볼 항목

- [기본 인쇄가 수행 되는 방법](../mfc/how-default-printing-is-done.md)

- [다중 페이지 문서](../mfc/multipage-documents.md)

- [머리글 및 바닥글](../mfc/headers-and-footers.md)

- [인쇄용 GDI 리소스 할당](../mfc/allocating-gdi-resources.md)

- [인쇄 미리 보기](../mfc/print-preview-architecture.md)

## <a name="see-also"></a>참고자료

[인쇄 및 인쇄 미리 보기](../mfc/printing-and-print-preview.md)
