---
title: '클립보드: OLE 클립보드 메커니즘 사용'
ms.date: 11/04/2016
helpviewer_keywords:
- applications [OLE], Clipboard
- OLE Clipboard
- Clipboard [MFC], OLE formats
- OLE Clipboard, formats
- formats [MFC], Clipboard for OLE
ms.assetid: 229cc610-5bb1-435e-bd20-2c8b9964d1af
ms.openlocfilehash: d8ef93b306c0968adf2c23c841c792d2f7af5de3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62327045"
---
# <a name="clipboard-using-the-ole-clipboard-mechanism"></a>클립보드: OLE 클립보드 메커니즘 사용

OLE는 클립보드를 통한 데이터 전송에 대 한 표준 형식 및 몇 가지 특정 형식을 사용 합니다.

잘라내거나 응용 프로그램에서 데이터를 복사 하는 경우 데이터 붙여넣기 작업에서 나중에 사용할 클립보드에 저장 됩니다. 이 데이터는 다양 한 형식입니다. 클립보드에서 데이터를 붙여 사용자 선택, 이러한 형식을 사용 하는 응용 프로그램 선택할 수 있습니다. 응용 프로그램 요청 하지 않으면 사용자 특히 특정 형식으로 선택 하 여 붙여넣기를 사용 하 여 대부분의 정보를 제공 하는 형식을 선택 하도록 작성 해야 합니다. 계속 하기 전에 읽을 하려는 합니다 [데이터 개체 및 데이터 소스 (OLE)](../mfc/data-objects-and-data-sources-ole.md) 항목입니다. 데이터 작업을 전송 하는 방법 및 응용 프로그램에서 구현 하는 방법의 기본적인 사항을 설명 합니다.

Windows는 클립보드를 통한 데이터 전송에 사용할 수 있는 표준 형식 수를 정의 합니다. 여기에 메타 파일, 텍스트, 비트맵 및 다른 사용자가 포함 됩니다. OLE 다양 한 특정 형식으로 정의합니다. 이러한 표준 형식으로 지정 된 보다 자세한 정보를 필요로 하는 응용 프로그램에 대 한 것이 자체 사용자 지정 클립보드 형식을 등록 하는 것이 좋습니다. Win32 API 함수를 사용 하 여 [됩니다](/windows/desktop/api/winuser/nf-winuser-registerclipboardformata) 에이 작업을 수행 합니다.

예를 들어 Microsoft Excel 스프레드시트에 대 한 사용자 지정 형식을 등록합니다. 이 형식 등의 경우 보다 훨씬 더 많은 정보를 전달, 비트맵 않습니다. 이 데이터는 스프레드시트 형식으로 지 원하는 응용 프로그램에 붙여넣으면 모든 수식 및 스프레드시트에서 값 유지 됩니다 하 고 필요한 경우에 업데이트할 수 있습니다. OLE 항목으로 붙여 넣을 수 있도록 형식으로 클립보드에 데이터가 또한 저장 합니다. 모든 OLE 문서 컨테이너 포함 된 항목으로이 정보를 붙여넣을 수 있습니다. Microsoft Excel을 사용 하 여이 포함 된 항목을 변경할 수 있습니다. 클립보드는 또한 스프레드시트에서 선택한 범위의 이미지의 간단한 비트맵을 포함합니다. 이 또한 붙여넣을 수 있습니다 OLE 문서 컨테이너 또는 그리기 등의 비트맵 편집기. 그러나 비트맵의 경우 방법이 없습니다 스프레드시트와 데이터를 조작할 수 있습니다.

최대한 많은 정보를 클립보드에서 검색 하려면 응용 프로그램 데이터를 클립보드에서 붙여넣기 전에 이러한 사용자 지정 형식에 대 한 확인 해야 합니다.

예를 들어, 잘라내기 명령을 사용 하려면 작성할 수 있습니다 처리기를 다음과 같이 합니다.

[!code-cpp[NVC_MFCListView#3](../atl/reference/codesnippet/cpp/clipboard-using-the-ole-clipboard-mechanism_1.cpp)]

## <a name="what-do-you-want-to-know-more-about"></a>자세히 알아볼 항목

- [데이터 복사 및 붙여넣기](../mfc/clipboard-copying-and-pasting-data.md)

- [기타 서식 추가](../mfc/clipboard-adding-other-formats.md)

- [Windows 클립보드 사용](../mfc/clipboard-using-the-windows-clipboard.md)

- [OLE](../mfc/ole-background.md)

- [OLE 데이터 개체 및 데이터 원본 및 균일 한 데이터 전송](../mfc/data-objects-and-data-sources-ole.md)

## <a name="see-also"></a>참고자료

[클립보드](../mfc/clipboard.md)
