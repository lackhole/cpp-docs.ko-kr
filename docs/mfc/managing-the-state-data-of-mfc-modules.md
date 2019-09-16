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

이 문서에서는 MFC 모듈의 상태 데이터와 및 실행 흐름(응용 프로그램이 실행될 때의 코드 흐름)이 모듈에 들어오고 나갈 때 이 상태가 업데이트되는 방법에 대하여 설명합니다. AFX_MANAGE_STATE 및 METHOD_PROLOGUE 매크로를 사용한 모듈 상태 전환도 설명합니다.

> [!NOTE]
>  여기서 "모듈"이라는 용어는 실행 가능한 프로그램이나 나머지 응용 프로그램과 독립적으로 동작하지만 MFC DLL의 공유 사본을 사용하는 DLL(또는 Dll 집합)을 말합니다. ActiveX 컨트롤은 모듈의 일반적인 예입니다.

다음 그림에 표시된 것과 같이 MFC는 응용 프로그램에서 사용되는 각 모듈에 대한 상태 데이터가 있습니다. 이 데이터의 예로 Windows 인스턴스 핸들(리소스 로드에 사용), 응용 프로그램의 현재 `CWinApp`과 `CWinThread` 개체에 대한 포인터, OLE 모듈 참조 횟수 및 Windows 개체 핸들과 해당 MFC 갸체의 인스턴스 사이의 연결을 유지하는 다양한 맵이 있습니다. 그러나 응용 프로그램이 여러 모듈을 사용하는 경우 각 모듈의 상태 데이터는 전체 응용 프로그램에 해당하는 것은 아닙니다. 대신 각 모듈에는 MFC의 상태 데이터의 전용 자체 복사본이 있습니다.

![단일 모듈의 데이터 상태 &#40;응용 프로그램&#41;](../mfc/media/vc387n1.gif "단일 모듈의 데이터 상태 &#40;응용 프로그램&#41;") <br/>
단일 모듈(애플리케이션)의 상태 데이터

모듈의 상태 데이터는 구조에 포함되어 있으며 언제나 해당 구조의 대한 포인터를 통해 접근할 수 있습니다. 다음 그림에 나와 있는 것처럼, 실행 흐름이 특정 모듈에 진입하면 해당 모듈의 상태는 "현재(current)" 또는 "유효(effective)" 상태가 됩니다. 따라서 각 스레드 개체는 해당 응용 프로그램의 유효한 상태 구조체에 대한 포인터를 가지게 됩니다. 이 포인터를 항상 업데이트 상태로 유지하는 것은 응용 프로그램의 전역 상태를 관리하고 각 모듈 상태의 무결성을 유지하는 데 중요합니다. 전역 상태를 잘못 관리하면 응용 프로그램 동작을 예측할 수 없게 될 수 있습니다.

![여러 모듈의 데이터 상태](../mfc/media/vc387n2.gif "여러 모듈의 데이터 상태") <br/>
여러 모듈의 상태 데이터

즉, 각 모듈은 모든 진입점에서 모듈 상태를 올바르게 전환해야 합니다. "진입점"은 모듈의 코드로 실행 흐름이 진입하게 되는 모든 지점을 의미합니다. 진입점은 다음과 같습니다.

- [DLL에서 내보낸된 함수](../mfc/exported-dll-function-entry-points.md)

- [COM 인터페이스의 멤버 함수](../mfc/com-interface-entry-points.md)

- [창 프로시저](../mfc/window-procedure-entry-points.md)

## <a name="see-also"></a>참고자료

[일반 MFC 항목](../mfc/general-mfc-topics.md)
