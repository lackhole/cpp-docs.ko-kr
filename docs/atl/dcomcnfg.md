---
title: DCOMCNFG
ms.date: 11/04/2016
helpviewer_keywords:
- DCOMCNFG utility
- DCOM, configuring in ATL
ms.assetid: 5a8126e9-ef27-40fb-a66e-9dce8d1a7e80
ms.openlocfilehash: a389a46cd02b40cef46d687743fd3416cc4f3154
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62250786"
---
# <a name="dcomcnfg"></a>DCOMCNFG

DCOMCNFG는 레지스트리에서 다양 한 DCOM 관련 설정을 구성할 수 있도록 Windows NT 4.0 유틸리티. DCOMCNFG 창에 3 개의 페이지가 있습니다. 기본 보안, 기본 속성 및 응용 프로그램입니다. Windows 2000에서 네 번째 페이지에서 기본 프로토콜, 없는 경우

## <a name="default-security-page"></a>기본 보안 페이지

시스템 개체에 대 한 기본 사용 권한을 지정 하는 기본 보안 페이지를 사용할 수 있습니다. 기본 보안 페이지에 세 개의 섹션이 있습니다. 액세스, 시작 및 구성 합니다. 섹션의 기본값을 변경 하려면 해당 **기본값 편집** 단추입니다. 이러한 기본 보안 설정은 레지스트리에 저장 됩니다 `HKEY_LOCAL_MACHINE\Software\Microsoft\OLE`합니다.

## <a name="default-protocols-page"></a>기본 프로토콜 페이지

이 페이지는이 컴퓨터에서 DCOM에 사용 가능한 네트워크 프로토콜의 집합을 나열합니다. 순서는 해당 사용 됩니다; 우선 순위를 반영 합니다. 목록의 첫 번째 가장 높은 우선 순위를 갖습니다. 프로토콜을 추가 하거나이 페이지에서 삭제 될 수 있습니다.

## <a name="default-properties-page"></a>기본 속성 페이지

기본 속성 페이지에서 선택 해야 합니다 **이 컴퓨터에서 DCOM을 사용 하도록 설정** 이 컴퓨터에서 실행 되는 액세스 COM 개체에 다른 컴퓨터에 클라이언트를 하려는 경우 확인란 합니다. 이 옵션을 선택 하 여 `HKEY_LOCAL_MACHINE\Software\Microsoft\OLE\EnableDCOM` 값을 `Y`입니다.

## <a name="applications-page"></a>응용 프로그램 페이지

응용 프로그램 페이지를 사용 하 여 특정 개체에 대 한 설정을 변경할 수 있습니다. 단순히 응용 프로그램 목록에서 선택 하 고 클릭 합니다 **속성** 단추입니다. 속성 창에 5 개 페이지가 있습니다.

- 일반 페이지를 사용 하는 응용 프로그램을 확인 합니다.

- 위치 페이지를 사용 하면 클라이언트가 호출 될 때 응용 프로그램 실행 위치를 지정할 수 있습니다 `CoCreateInstance` 관련 CLSID에 있습니다. 선택 하는 경우는 **컴퓨터에서 응용 프로그램 실행** 확인란을 선택 하 고 컴퓨터 이름을 입력는 `RemoteServerName` appid에 해당 응용 프로그램에 대 한 값이 추가 됩니다. 선택을 취소 합니다 **이 컴퓨터에서 응용 프로그램을 실행** 확인란 이름 바꾸기는 `LocalService` 값을 `_LocalService` 및 따라서 사용 하지 않도록 설정 합니다.

- 보안 페이지를 제외 하 고 이러한 설정은 현재 응용 프로그램에만 적용 DCOMCNFG 창에서 찾을 수 있는 기본 보안 페이지와 비슷합니다. 마찬가지로 해당 개체에 대 한 appid 설정이 저장 됩니다.

- 확인 페이지는 사용자가 응용 프로그램을 실행 하는 데 식별 합니다.

- 끝점 페이지에는 프로토콜 및 선택한 DCOM 서버의 클라이언트에서 사용할 수 있는 끝점의 집합을 나열합니다.

## <a name="see-also"></a>참고자료

[서비스](../atl/atl-services.md)
