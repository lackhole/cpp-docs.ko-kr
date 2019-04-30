---
title: InitInstance 멤버 함수
ms.date: 11/04/2016
f1_keywords:
- InitInstance
helpviewer_keywords:
- InitInstance method [MFC]
- applications [MFC], initializing
- MFC, initializing
- initializing MFC applications
ms.assetid: 4ef09267-ff7f-4c39-91a0-57454a264f83
ms.openlocfilehash: c96d009cf19981a475209233ee397af1cdcb352d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62219522"
---
# <a name="initinstance-member-function"></a>InitInstance 멤버 함수

Windows 운영 체제를 사용 하면 둘 이상의 복사 또는 "인스턴스"를 동일한 응용 프로그램을 실행할 수 있습니다. `WinMain` 호출 [InitInstance](../mfc/reference/cwinapp-class.md#initinstance) 될 때마다 응용 프로그램의 새 인스턴스를 시작 합니다.

표준 `InitInstance` 구현 MFC 응용 프로그램 마법사로 만든 다음 작업을 수행 합니다.

- 주요 작업으로 문서, 뷰 및 프레임 창에서 만든 문서 서식 파일을 만듭니다. 이 프로세스에 대 한 참조 [문서 템플릿 만들기](../mfc/document-template-creation.md)합니다.

- 가장 최근에 사용한 파일의 이름을 포함 하 여 Windows 레지스트리 또는.ini 파일에서 표준 파일 옵션을 로드 합니다.

- 하나 이상의 문서 템플릿이 등록합니다.

- MDI 응용 프로그램에 대 한 주 프레임 창을 만듭니다.

- 명령줄에서 지정 된 문서와 새 빈 문서를 열려면 명령줄을 처리 합니다.

고유한 초기화 코드를 추가할 수도 있고 마법사에서 작성 한 코드를 수정할 수 있습니다.

> [!NOTE]
>  MFC 응용 프로그램은 단일 스레드 아파트 (STA)로 초기화 되어야 합니다. 호출 하는 경우 [CoInitializeEx](/windows/desktop/api/combaseapi/nf-combaseapi-coinitializeex) 에서 프로그램 `InitInstance` 재정의 COINIT_APARTMENTTHREADED (COINIT_MULTITHREADED 아님)를 지정 합니다.

## <a name="see-also"></a>참고자료

[CWinApp: 애플리케이션 클래스](../mfc/cwinapp-the-application-class.md)
