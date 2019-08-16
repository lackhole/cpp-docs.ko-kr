---
title: 'CAtlServiceModuleT:: Start 함수'
ms.date: 11/04/2016
helpviewer_keywords:
- Start method
ms.assetid: b5193a23-41bc-42d2-8d55-3eb43dc62238
ms.openlocfilehash: e6de15f40e89bfffba504db04ee7a16b2a68cac9
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69491661"
---
# <a name="catlservicemoduletstart-function"></a>CAtlServiceModuleT:: Start 함수

서비스가 실행 `_tWinMain` `CAtlServiceModuleT::Start`되 면는를 호출 하 여을 호출 합니다. `CAtlServiceModuleT::WinMain`

`CAtlServiceModuleT::Start`각 서비스를 시작 함수 `SERVICE_TABLE_ENTRY` 에 매핑하는 구조체의 배열을 설정 합니다. 그런 다음이 배열은 Win32 API 함수 [startservicectrldispatcher가](/windows/win32/api/winsvc/nf-winsvc-startservicectrldispatcherw)에 전달 됩니다. 이론적으로 한 EXE는 여러 서비스를 처리할 수 있으며 배열에는 여러 `SERVICE_TABLE_ENTRY` 개의 구조가 있을 수 있습니다. 그러나 현재는 ATL 생성 서비스가 EXE 당 하나의 서비스만 지원 합니다. 따라서 배열에는 서비스 이름과 `_ServiceMain` 시작 함수를 포함 하는 단일 항목이 있습니다. `_ServiceMain`는 비정적 멤버 함수를 `CAtlServiceModuleT` `ServiceMain`호출 하는의 정적 멤버 함수입니다.

> [!NOTE]
>  `StartServiceCtrlDispatcher` SCM (서비스 제어 관리자)에 연결 하지 못하면 프로그램이 서비스로 실행 되 고 있지 않을 수 있습니다. 이 경우 프로그램에서 직접를 호출 `CAtlServiceModuleT::Run` 하 여 프로그램이 로컬 서버로 실행 될 수 있도록 합니다. 로컬 서버로 프로그램을 실행 하는 방법에 대 한 자세한 내용은 [디버깅 팁](../atl/debugging-tips.md)을 참조 하십시오.

## <a name="see-also"></a>참고자료

[Services](../atl/atl-services.md)<br/>
[CAtlServiceModuleT::Start](../atl/reference/catlservicemodulet-class.md#start)
