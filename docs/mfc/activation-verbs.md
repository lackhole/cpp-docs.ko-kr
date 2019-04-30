---
title: '활성화: 동사'
ms.date: 11/04/2016
helpviewer_keywords:
- verbs [MFC]
- OLE [MFC], activation
- edit verb [MFC]
- activation [MFC], verbs
- OLE [MFC], editing
- Primary verb [MFC]
- OLE activation {MFC]
ms.assetid: eb56ff23-1de8-43ad-abeb-dc7346ba7b70
ms.openlocfilehash: baf8e0ac3527407b2e5ba77dfdf3921419217fd7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62392910"
---
# <a name="activation-verbs"></a>활성화: 동사

이 문서에서는 OLE의 역할 기본 및 보조 동사 play 설명 [활성화](../mfc/activation-cpp.md)합니다.

일반적으로 포함 된 항목을 두 번 클릭 하 여 편집 사용자 수 있습니다. 그러나 특정 항목에는 이러한 방식으로 다르게 합니다. 예를 들어 녹음기 응용 프로그램을 사용 하 여 만든 항목을 두 번 클릭 하면 열리지 않으면 서버는 별도 창에서 대신, 소리를 재생 합니다.

이 동작 차이 대 한 이유는는 녹음기 항목을 다른 "기본 동사입니다." 기본 동사에는 OLE 항목을 두 번 클릭할 때 수행할 동작입니다. OLE 항목의 대부분의 형식에 대 한 기본 동사는 항목을 만든 서버를 시작 하는 편집 합니다. 녹음기 항목과 같은 항목의 일부 형식에 대 한 기본 동사는 재생을 사용 합니다.

다양 한 유형의 OLE 항목 하나만 동사를 지원 하 고 편집은 가장 일반적인 것입니다. 그러나 일부 유형의 항목 여러 동사를 지원합니다. 예를 들어 항목 지원 녹음기 보조 동사로 편집 합니다.

자주 사용 되는 다른 동사는 Open입니다. Open 동사는 서버 응용 프로그램은 별도 창에서 실행 됩니다 점을 제외 하 고 편집을 동일 합니다. 컨테이너 응용 프로그램 또는 서버 응용 프로그램이 내부 활성화를 지원 하지 않는 경우이 동사를 사용 해야 합니다.

항목이 선택 될 때 기본 동사 이외의 모든 동사 메뉴 명령을 통해 호출 되어야 합니다. 이 하위 메뉴 항목을 지 원하는 모든 동사를 포함 하 고 일반적으로 도달 하는 *typename* **개체** 명령을 합니다 **편집** 메뉴. 에 대 한 정보에 대 한 합니다 *typename* **개체** 명령 문서를 참조 하십시오 [메뉴 및 리소스: 컨테이너 추가](../mfc/menus-and-resources-container-additions.md)합니다.

서버 응용 프로그램에서 지원 되는 동사는 Windows 등록 데이터베이스에 나열 됩니다. 서버 응용 프로그램이 Microsoft Foundation Class 라이브러리를 사용 하 여 기록 되는 경우 서버 시작 될 때 모든 동사를 자동으로 등록 됩니다 것입니다. 그렇지 않은 경우 서버 응용 프로그램의 초기화 단계 중 등록 해야 합니다. 자세한 내용은 문서 참조 [등록](../mfc/registration.md)합니다.

## <a name="see-also"></a>참고자료

[활성화](../mfc/activation-cpp.md)<br/>
[컨테이너](../mfc/containers.md)<br/>
[서버](../mfc/servers.md)
