---
title: 사용자 지정의 보안 의미
ms.date: 11/04/2016
helpviewer_keywords:
- security, MFC Feature Pack
- MFC Feature Pack, security
ms.assetid: 9be96b12-be38-43bd-a133-5d671265f7a1
ms.openlocfilehash: 9164983a6634e069195f3498bea56b595a2a2381
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62308474"
---
# <a name="security-implications-of-customization"></a>사용자 지정의 보안 의미

이 항목에서는 MFC의 잠재적인 보안 취약점을 설명합니다.

## <a name="potential-security-weakness"></a>잠재적인 보안 취약점

MFC를 사용 하면 예를 들어, 단추 및 아이콘 모양 응용 프로그램 사용자 인터페이스의 모양을 사용자 지정 합니다. MFC는 또한 사용자가 셸 명령을 실행 하는 사용자 정의 도구를 지원 합니다. 보안 취약점을 응용 프로그램의 사용자 지정된 설정을 레지스트리에 사용자 프로필에 저장 되기 때문에 발생 합니다. 레지스트리에 액세스할 수 있는 사용자는 누구나 이러한 설정을 편집 하 고 응용 프로그램 모양이 나 동작을 변경할 수 있습니다. 예를 들어 컴퓨터의 관리자는 사용자의 응용 프로그램 (에서도, 네트워크 공유) 임의 프로그램을 실행 하 여 사용자를 가장할 수 있습니다.

## <a name="workarounds"></a>해결 방법

이러한 세 가지 방법으로 레지스트리에서 취약점을 닫으려면이 좋습니다.

- 저장 된 데이터를 암호화 합니다.

- 레지스트리에서 대신 보안 파일에 데이터를 저장 합니다.

   를 수행 하기 위해 먼저 두 가지 중 하나에서 클래스를 파생 [CSettingsStore 클래스](../mfc/reference/csettingsstore-class.md) 암호화 또는 레지스트리 외부 저장소를 구현 하는 해당 메서드를 재정의 합니다.

- 또한 응용 프로그램에서 사용자 지정을 비활성화할 수 있습니다.

## <a name="see-also"></a>참고자료

[MFC에 대한 사용자 지정](../mfc/customization-for-mfc.md)
