---
title: 인터넷 보안(C++)
ms.date: 11/04/2016
helpviewer_keywords:
- code signing [MFC], Internet security
- sandboxing [MFC]
- digital signatures [MFC], Internet security
- code signing [MFC]
- Web application security [MFC]
- code access security [MFC], Internet security considerations
- security [MFC]
- security [MFC], Internet
- Internet applications [MFC], security
- Web application security [MFC], Internet security approaches
ms.assetid: bf0da697-81bc-41f0-83fa-d7f82ed83df8
ms.openlocfilehash: 184c8edf3e4a81be1f8b2a282a0db9758a75253f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62310905"
---
# <a name="internet-security-c"></a>인터넷 보안(C++)

코드 보안에는 인터넷 응용 프로그램의 사용자 및 개발자를 위한 주요 문제입니다. 위험이 있습니다: 악성 코드, 변조, 코드 및 작성자 또는 알 수 없는 사이트에서 코드입니다.

두 가지 기본 보안을 인터넷에 대 한 개발 하는 경우. 첫 번째 "샌드 박싱 합니다." 라고 합니다. 이 방법에서는 응용 프로그램 Api의 특정 집합으로 제한 이며 프로그램 사용자의 컴퓨터에서 데이터를 손상 될 수 있습니다 위치 하는 파일 I/O와 같은 잠재적으로 위험한 것에서 제외 합니다. 두 번째는 디지털 서명을 사용 하 여 구현 됩니다. 이 접근 방식 이라고 "shrinkwrap" 인터넷에 대 한 합니다. 코드 확인 되 고 개인 키/공개 키 기술을 사용 하 여 서명 합니다. 코드를 실행 하기 전에 알려진된 인증 된 원본에서 코드를 코드 서명 된 이후 변경 되지 않았음을 확인 하는 디지털 서명을 확인 합니다.

첫 번째 경우, 응용 프로그램에 나쁜 영향을 미치지 수행 하지 것입니다 하 고 응용 프로그램의 출처를 신뢰할 신뢰 합니다. 두 번째는 디지털 서명에 신뢰성 확인을 위해 사용 됩니다. 디지털 서명은 식별 하 고 코드의 게시자에 대 한 세부 정보를 제공 하는 데 사용 하는 산업 표준입니다. 해당 기술 RSA 등 X.509 표준을 기반으로 합니다. 브라우저는 일반적으로 다운로드 하 고 출처를 알 수 없는 코드의 실행을 선택할 수가 있습니다.

## <a name="see-also"></a>참고자료

[MFC 인터넷 프로그래밍 작업](../mfc/mfc-internet-programming-tasks.md)<br/>
[MFC 인터넷 프로그래밍 기본 사항](../mfc/mfc-internet-programming-basics.md)
