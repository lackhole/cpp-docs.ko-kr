---
title: 'CAtlServiceModuleT:: ServiceMain 함수'
ms.date: 11/04/2016
helpviewer_keywords:
- ServiceMain method
ms.assetid: f21408c1-1919-4dec-88d8-bf5b39ac9808
ms.openlocfilehash: b79767d4c1696174f90a325ea152ccc7939ed9fe
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69491716"
---
# <a name="catlservicemoduletservicemain-function"></a>CAtlServiceModuleT:: ServiceMain 함수

SCM (서비스 제어 관리자)은 서비스 `ServiceMain` 제어판 응용 프로그램을 열고 서비스를 선택 하 고 **시작**을 클릭 하면 호출 됩니다.

Scm이 호출 `ServiceMain`되 면 서비스는 scm에 처리기 함수를 제공 해야 합니다. 이 함수를 통해 SCM은 서비스의 상태를 가져오고 특정 지침 (예: 일시 중지 또는 중지)을 전달할 수 있습니다. SCM은 서비스가 Win32 API 함수 `_Handler` [RegisterServiceCtrlHandler](/windows/win32/api/winsvc/nf-winsvc-registerservicectrlhandlerw)에 전달 될 때이 함수를 가져옵니다. `_Handler`는 비정적 멤버 함수 [처리기](../atl/reference/catlservicemodulet-class.md#handler)를 호출 하는 정적 멤버 함수입니다.

시작할 때 서비스는 SCM에 현재 상태를 알려야 합니다. 이를 위해 SERVICE_START_PENDING를 Win32 API 함수 [SetServiceStatus](/windows/win32/api/winsvc/nf-winsvc-setservicestatus)에 전달 합니다.

`ServiceMain`그런 다음 [CoInitializeEx](/windows/win32/api/combaseapi/nf-combaseapi-coinitializeex)함수를 호출 하는 Win32 API 함수 를호출합니다.`CAtlExeModuleT::InitializeCom` 기본적으로는 `InitializeCom` 함수에 COINIT_MULTITHREADED 플래그를 전달 합니다. 이 플래그는 프로그램이 자유 스레드된 서버 임을 나타냅니다.

이제 서비스의 주요 작업을 수행 하기 위해 가호출됩니다.`CAtlServiceModuleT::Run` `Run`서비스가 중지 될 때까지 계속 실행 됩니다.

## <a name="see-also"></a>참고자료

[Services](../atl/atl-services.md)<br/>
[CAtlServiceModuleT::ServiceMain](../atl/reference/catlservicemodulet-class.md#servicemain)
