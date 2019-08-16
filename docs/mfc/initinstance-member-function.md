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
ms.openlocfilehash: c1f83f794cc40fa7f4d290fa4a147fe9f7e074be
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69508366"
---
# <a name="initinstance-member-function"></a>InitInstance 멤버 함수

Windows 운영 체제에서는 동일한 응용 프로그램의 복사본을 두 개 이상 실행 하거나 "인스턴스"를 실행할 수 있습니다. `WinMain`응용 프로그램의 새 인스턴스가 시작 될 때마다 [InitInstance](../mfc/reference/cwinapp-class.md#initinstance) 를 호출 합니다.

MFC 응용 `InitInstance` 프로그램 마법사에서 만든 표준 구현에서는 다음 작업을 수행 합니다.

- 는 중앙 작업으로 문서, 뷰 및 프레임 창을 만드는 문서 템플릿을 만듭니다. 이 프로세스에 대 한 설명은 [문서 템플릿 만들기](../mfc/document-template-creation.md)를 참조 하세요.

- 는 가장 최근에 사용한 파일의 이름을 포함 하 여 .ini 파일이 나 Windows 레지스트리에서 표준 파일 옵션을 로드 합니다.

- 하나 이상의 문서 템플릿을 등록 합니다.

- MDI 응용 프로그램의 경우 주 프레임 창을 만듭니다.

- 명령줄을 처리 하 여 명령줄에 지정 된 문서를 열거나 비어 있는 새 문서를 엽니다.

사용자 고유의 초기화 코드를 추가 하거나 마법사에서 작성 한 코드를 수정할 수 있습니다.

> [!NOTE]
>  MFC 응용 프로그램을 STA (단일 스레드 아파트)로 초기화 해야 합니다. `InitInstance` 재정의에서 [CoInitializeEx](/windows/win32/api/combaseapi/nf-combaseapi-coinitializeex) 를 호출 하는 경우 COINIT_MULTITHREADED 대신 COINIT_APARTMENTTHREADED를 지정 합니다.

## <a name="see-also"></a>참고자료

[CWinApp: 애플리케이션 클래스](../mfc/cwinapp-the-application-class.md)
