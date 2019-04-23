---
title: OLE DB 서비스 사용 및 사용 안 함
ms.date: 10/29/2018
helpviewer_keywords:
- OLE DB services [OLE DB], enabling and disabling
- service providers [OLE DB]
ms.assetid: 445f97eb-32a8-41c2-ad26-1169f78a074f
ms.openlocfilehash: df17a55950b03d4d63dea2199e3bc19bedb8a7e3
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59028956"
---
# <a name="enabling-and-disabling-ole-db-services"></a>OLE DB 서비스 사용 및 사용 안 함

OLE DB 서비스 구성 요소 관리자는 소비자가 요청한 확장된 기능을 충족 하기 위해 개별 서비스 구성 요소를 사용할 수 있는지 여부를 확인 하려면 공급자가 지 원하는 속성에는 소비자가 지정한 속성을 비교 합니다. 예를 들어 응용 프로그램이 스크롤 가능 커서를 요청 하는 경우 공급자는 정방향 전용 커서 지원 서비스 구성 요소 관리자를 스크롤할 수 있는 기능을 제공 하도록 Client Cursor Engine 서비스 구성 요소를 사용 합니다. 응용 프로그램은 공급자의 행 집합에서 기본적으로 지원 되는 확장된 기능에 의존 하므로 응용 프로그램에는 명시적으로 그렇지 않은 경우에 기능을 기능 나타나지 않을 수 있습니다 클라이언트에서 반환 된 행에서 요청 속성을 설정 합니다. 커서 엔진입니다. 상호 운용성을 위해 응용 프로그램은 항상 속성을 설정 하는 확장된 기능을 명시적으로 요청 필요한 경우.

경우에 따라 기존 응용 프로그램 공급자의 특성에 대 한 가정을 함께 사용할 수 있는 개별 OLE DB 서비스를 사용 하지 않도록 설정 해야 할 수도 있습니다. OLE DB 서비스는 개별 서비스나 연결 하 여 연결 단위로 또는 단일 공급자를 사용 하 여 모든 응용 프로그램에 대 한 모든 서비스를 사용 하지 않도록 설정 하는 기능을 제공 합니다.

## <a name="see-also"></a>참고자료

[OLE DB 리소스 풀링 및 서비스](../../data/oledb/ole-db-resource-pooling-and-services.md)