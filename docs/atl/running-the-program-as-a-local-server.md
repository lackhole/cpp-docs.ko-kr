---
title: 로컬 서버로 프로그램 실행
ms.date: 11/04/2016
helpviewer_keywords:
- debugging [ATL], running services as local server
- ATL services, running as local servers
ms.assetid: eb9701e6-e2a8-4666-897f-0c893aec8ac7
ms.openlocfilehash: a412814fc5f3900a248f779501e2720b72287e57
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62196524"
---
# <a name="running-the-program-as-a-local-server"></a>로컬 서버로 프로그램 실행

서비스 프로그램 실행을 편리 하 게 없으면 프로그램이 정상적인 로컬 서버로 실행 될 수 있도록 레지스트리를 일시적으로 변경할 수 있습니다. 단순히 이름 바꾸기는 `LocalService` 프로그램 AppID 아래에 값 `_LocalService` 확인 하 고는 `LocalServer32` 사용자의 CLSID 아래에 키가 올바르게 설정 합니다. (참고는 DCOMCNFG를 사용 하 여 다른 컴퓨터에서 응용 프로그램을 실행 해야는 지정의 이름을 바꿉니다 하 `LocalServer32` 키를 `_LocalServer32`.) 때문에 로컬 서버 시작 시 몇 초를 사용 하는 대로 프로그램 실행에 대 한 호출 `StartServiceCtrlDispatcher` 에서 `CAtlServiceModuleT::Start` 실패 하기 전에 몇 초 정도 걸립니다.

## <a name="see-also"></a>참고자료

[디버깅 팁](../atl/debugging-tips.md)
