---
title: ATL 모듈 클래스
ms.date: 11/04/2016
helpviewer_keywords:
- CComModule class, what's changed
- ATL, module classes
- module classes
ms.assetid: fd75382d-c955-46ba-a38e-37728b7fa00f
ms.openlocfilehash: 2fe659b47893f821aab4cda31ab1a4e9a6788ec6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62252072"
---
# <a name="atl-module-classes"></a>ATL 모듈 클래스

이 항목에서는 ATL 7.0에 새로 추가 된 모듈 클래스를 설명 합니다.

## <a name="ccommodule-replacement-classes"></a>CComModule 대체 클래스

이전 버전 사용 되는 ATL의 `CComModule`합니다. ATL 7.0에 `CComModule` 기능 몇 가지 클래스로 대체 됩니다.

- [CAtlBaseModule](../atl/reference/catlbasemodule-class.md) ATL.를 사용 하는 대부분의 응용 프로그램에 필요한 정보를 포함 합니다. 모듈 및 리소스 인스턴스의 HINSTANCE를 포함 되어 있습니다.

- [CAtlComModule](../atl/reference/catlcommodule-class.md) ATL에서 COM 클래스에 필요한 정보를 포함 합니다.

- [CAtlWinModule](../atl/reference/catlwinmodule-class.md) ATL에서 창 작업 클래스에서 필요한 정보를 포함 합니다.

- [CAtlDebugInterfacesModule](../atl/reference/catldebuginterfacesmodule-class.md) 인터페이스 디버깅에 대 한 지원이 포함 되어 있습니다.

- [CAtlModule](../atl/reference/catlmodule-class.md) 다음 `CAtlModule`-파생된 클래스는 특정 응용 프로그램 형식에 필요한 정보를 포함 하는 사용자 지정 됩니다. 이러한 클래스의 대부분의 멤버를 재정의할 수 있습니다.

   - [CAtlDllModuleT](../atl/reference/catldllmodulet-class.md) DLL 응용 프로그램에서 사용 합니다. 표준 내보내기에 대 한 코드를 제공합니다.

   - [CAtlExeModuleT](../atl/reference/catlexemodulet-class.md) EXE 응용 프로그램에서 사용 합니다. EXE에 필요한 코드를 제공 합니다.

   - [CAtlServiceModuleT](../atl/reference/catlservicemodulet-class.md) Windows NT 및 Windows 2000 서비스 만들기에 대 한 지원을 제공 합니다.

`CComModule` 이전 버전과 호환성을 위해 여전히 표시 됩니다.

## <a name="reasons-for-distributing-ccommodule-functionality"></a>CComModule 기능을 배포 하는 이유

기능의 `CComModule` 가 다음과 같은 이유로 여러 가지 새로운 클래스가에 배포 합니다.

- 기능을 확인 `CComModule` 세분화 합니다.

   COM, windowing, 인터페이스, 디버깅 및 응용 프로그램별 (DLL 또는 EXE) 기능에 대 한 지원은 이제 별도 클래스입니다.

- 이러한 각 모듈의 전역 인스턴스를 자동으로 선언 합니다.

   필수 모듈 클래스의 전역 인스턴스를 프로젝트에 연결 됩니다.

- Init 및 용어 메서드를 호출 하는 필요성을 제거 합니다.

   Init 및 용어 메서드는 모듈 클래스에 대 한 생성자 및 소멸자로 이동 되어 더 이상 없기 Init 및 용어를 호출 해야 합니다.

## <a name="see-also"></a>참고자료

[개념](../atl/active-template-library-atl-concepts.md)<br/>
[클래스 개요](../atl/atl-class-overview.md)
