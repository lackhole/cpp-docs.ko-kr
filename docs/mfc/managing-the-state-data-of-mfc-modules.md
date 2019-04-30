---
title: MFC 모듈의 상태 데이터 관리
ms.date: 11/19/2018
helpviewer_keywords:
- global state [MFC]
- data management [MFC], MFC modules
- window procedure entry points [MFC]
- exported interfaces and global state [MFC]
- module states [MFC], saving and restoring
- data management [MFC]
- MFC, managing state data
- multiple modules [MFC]
- module state restored [MFC]
ms.assetid: 81889c11-0101-4a66-ab3c-f81cf199e1bb
ms.openlocfilehash: 0cdb368dc70b73ba70b3721fecdaf47de36686d5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62338371"
---
# <a name="managing-the-state-data-of-mfc-modules"></a>MFC 모듈의 상태 데이터 관리

이 문서에서는 MFC 모듈 및 흐름 실행 (path 코드는 응용 프로그램을 통해 실행 하는 경우)을 입력 하 고 모듈을 벗어날 때이 상태는 업데이트 하는 방법의 상태 데이터를 설명 합니다. AFX_MANAGE_STATE 및 METHOD_PROLOGUE 매크로 사용 하 여 모듈 상태 전환도 설명 합니다.

> [!NOTE]
>  용어 "모듈" 여기 실행 프로그램 또는 DLL (또는 Dll 집합이) 응용 프로그램의 나머지 부분과 별개로 작동 하는, 나타내지만 공유 MFC DLL의 복사본을 사용 합니다. ActiveX 컨트롤에는 모듈의 일반적인 예입니다.

다음 그림에 표시 된 것과 같이 MFC 응용 프로그램에서 사용 되는 각 모듈에 대 한 상태 데이터를 갖습니다. 이 데이터의 예로 Windows 인스턴스 핸들 (리소스 로드를 위한 사용), 현재 포인터 `CWinApp` 고 `CWinThread` 응용 프로그램, OLE 모듈 참조 횟수 및 다양 한 간의 연결을 유지 관리 하는 맵 개체 Windows 핸들 및 MFC 개체의 해당 인스턴스 개체입니다. 그러나 응용 프로그램에서는 여러 모듈 상태 데이터를 각 모듈의 경우 응용 프로그램 다양 합니다. 대신, 각 모듈에 MFC의 상태 데이터의 고유한 개인 복사본이 있습니다.

![단일 모듈의 데이터 상태 &#40;응용 프로그램&#41;](../mfc/media/vc387n1.gif "단일 모듈의 데이터 상태 &#40;응용 프로그램&#41;") <br/>
단일 모듈(응용 프로그램)의 상태 데이터

모듈의 상태 데이터 구조에 포함 되어 있으며는 항상 해당 구조에 대 한 포인터를 통해 사용할 수 있습니다. 들어가면 실행 흐름을 특정 모듈의 경우, 다음 그림에 나와 있는 것 처럼, 해당 모듈의 상태는 "현재" 또는 "효율적인" 상태 여야 합니다. 따라서 각 스레드 개체에 해당 응용 프로그램의 유효한 상태 구조체에 대 한 포인터입니다. 전혀 업데이트 this이 포인터를 유지 시간에 매우 중요 응용 프로그램의 전역 상태를 관리 하 고 각 모듈의 상태의 무결성을 유지 합니다. 잘못 된 관리 전역 상태를 예측할 수 없는 응용 프로그램 동작이 발생할 수 있습니다.

![여러 모듈의 데이터 상태](../mfc/media/vc387n2.gif "여러 모듈의 데이터 상태") <br/>
여러 모듈의 상태 데이터

즉, 각 모듈은 올바르게 해당 진입점의 모든 모듈 상태를 전환 하는 일을 담당 합니다. "진입점"은 실행 흐름을 모듈의 코드를 입력할 수 있는 곳입니다. 진입점은 다음과 같습니다.

- [DLL에서 내보낸된 함수](../mfc/exported-dll-function-entry-points.md)

- [COM 인터페이스의 멤버 함수](../mfc/com-interface-entry-points.md)

- [창 프로시저](../mfc/window-procedure-entry-points.md)

## <a name="see-also"></a>참고자료

[일반 MFC 항목](../mfc/general-mfc-topics.md)
