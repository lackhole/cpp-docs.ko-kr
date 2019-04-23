---
title: 끌어서 놓기(OLE)
ms.date: 11/04/2016
helpviewer_keywords:
- OLE server applications [MFC], drag and drop
- drag and drop [MFC]
- OLE applications [MFC], drag and drop
- File Manager drag and drop support [MFC]
- drag and drop [MFC], about OLE drag and drop
- OLE drag and drop [MFC]
ms.assetid: a4595350-ca06-4400-88a1-f0175c76b77b
ms.openlocfilehash: 98bd58745e56a62bf5700e9b5fe4963a7b584953
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58766809"
---
# <a name="drag-and-drop-ole"></a>끌어서 놓기(OLE)

Ole 끌어서 놓기 기능은 기본적으로 데이터 복사 및 붙여넣기에 대 한 바로 가기입니다. 클립보드로 복사 하거나 붙여넣을 데이터를 사용 하 여 다양 한 단계는 필요 합니다. 데이터 선택, 클릭 **잘라내기** 또는 **복사본** 에서 합니다 **편집** 메뉴에서 대상 파일, 창 또는 응용 프로그램으로 이동 클릭 확인 하 고 원하는 위치에 커서를 놓고 **붙여넣기** 에서 합니다 **편집** 메뉴.

OLE 끌어서 놓기 파일 이름을 처리할 수 있으며 파일 이름이 응용 프로그램에 전달 하도록 특별히 설계 파일 관리자 끌어서 놓기 메커니즘을 다릅니다. OLE 끌어서 놓기는 훨씬 더 일반적인 합니다. 끌어서 놓기 데이터를 클립보드에 배치 될 수도 있습니다.

OLE 끌어서 놓기를 사용 하면 프로세스에서 두 단계를 제거 합니다. 소스 창 ("놓기 소스가")에서 데이터를 선택, ("놓기 대상")에서 원하는 대상에 놓습니다 하 마우스 단추에서 손을 떼기 여 삭제 합니다. 작업 메뉴에 대 한 필요성을 제거 하 고 복사/붙여넣기 시퀀스 보다 빠릅니다. 유일한 요구 사항은 열려 있고 화면에서 적어도 부분적으로 표시 놓기 소스와 놓기 대상 이어야 합니다.

OLE 끌어서 놓기 사용 데이터 전송할 수 있습니다 한 위치에서 다른 응용 프로그램 간 또는 서로 다른 문서는 문서 내입니다. 컨테이너 또는 서버 응용 프로그램을 구현할 수 있습니다 하 고 모든 응용 프로그램 놓기 소스, 놓기 대상 또는 둘 다를 수 있습니다. 응용 프로그램에서 지원할 경우에 놓기 소스와 놓기 대상 구현, 끌어서 놓기 자식 창 사이 또는 단일 창에서 사용 됩니다. 이 기능은 가능 응용 프로그램 사용 하기가 훨씬 쉬워졌습니다.

OLE 끌어서 놓기 기능을 사용 하려는 경우 참조 [끌어다 놓습니다. 사용자 지정](../mfc/drag-and-drop-customizing.md)합니다. 놓기 소스 비 OLE 응용 프로그램에 해당 문서에 설명 된 기법을 사용할 수 있습니다. 문서 [끌어다 놓습니다. 놓기 대상 구현](../mfc/drag-and-drop-implementing-a-drop-target.md) OLE 응용 프로그램과 비 OLE 응용 프로그램에 대 한 대상 놓기 지원을 구현 하는 방법에 설명 합니다. MFC OLE 샘플을 검사 하는 데 도움이 됩니다 [OCLIENT](../overview/visual-cpp-samples.md) 하 고 [HIERSVR](../overview/visual-cpp-samples.md)합니다.

읽지 않은 경우는 [데이터 개체 및 데이터 소스 (OLE)](../mfc/data-objects-and-data-sources-ole.md) 지금 하려는 아티클의 제품군입니다. 이 문서에서는 데이터 전송 및 응용 프로그램에서 구현 하는 방법의 기본적인 사항을 설명 합니다.

끌어서 놓기에 대 한 자세한 내용은 다음을 참조 하세요.

- [끌어서 놓기: 놓기 소스 구현](../mfc/drag-and-drop-implementing-a-drop-source.md)

- [끌어서 놓기: 놓기 대상 구현](../mfc/drag-and-drop-implementing-a-drop-target.md)

- [끌어서 놓기: 사용자 지정](../mfc/drag-and-drop-customizing.md)

## <a name="see-also"></a>참고자료

[OLE](../mfc/ole-in-mfc.md)<br/>
[데이터 개체 및 데이터 소스(OLE)](../mfc/data-objects-and-data-sources-ole.md)
