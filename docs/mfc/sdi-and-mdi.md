---
title: SDI 및 MDI
ms.date: 11/04/2016
helpviewer_keywords:
- frame windows [MFC], SDI applications
- frame windows [MFC], MDI applications
- MFC, windows
- single document interface (SDI) [MFC], applications
- MDI [MFC], vs. SDI
ms.assetid: bb7239d9-4759-4f63-bfff-44a04b48c067
ms.openlocfilehash: 725249e5a71e8ee097c641e5972e3cc8bb0e3e33
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62308537"
---
# <a name="sdi-and-mdi"></a>SDI 및 MDI

MFC를 사용하면 SDI(단일 문서 인터페이스) 응용 프로그램과 MDI(다중 문서 인터페이스) 응용 프로그램 작업을 쉽게 할 수 있습니다.

SDI 응용 프로그램은 한 번에 하나의 열려있는 문서 프레임 창만 허용합니다. MDI 응용 프로그램의 여러 문서 프레임 창을 동일한 인스턴스의 응용 프로그램에서 열 수 있도록 허용합니다. MDI 응용 프로그램에는 각 개별 문서를 포함하는 프레임 창 자체로 여러개의 MDI 자식창을 열 수 있는 창이 있습니다. 일부 응용 프로그램에서는 자식 창이 차트 창이나 스프레드시트 창와 같은 다양한 형식이 될 수 있습니다. 이 경우 다른 유형의 MDI 자식 창이 활성화되면 메뉴 표시줄이 변경 ​​될 수 있습니다.

> [!NOTE]
>  Windows 95 이상에서는 운영체제가 "문서 중심" 보기를 채택했기 때문에 응용 프로그램은 일반적으로 SDI 입니다.

자세한 내용은 [문서, 뷰 및 프레임 워크](../mfc/documents-views-and-the-framework.md)를 참조합니다.

## <a name="see-also"></a>참고자료

[클래스를 사용하여 Windows 애플리케이션 작성](../mfc/using-the-classes-to-write-applications-for-windows.md)
