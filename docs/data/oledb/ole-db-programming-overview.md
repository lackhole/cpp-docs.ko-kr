---
title: OLE DB 프로그래밍 개요
ms.date: 10/22/2018
helpviewer_keywords:
- Universal Data Access
- OLE DB, about OLE DB
ms.assetid: a5a69730-2793-4277-a67d-6f3c8edab6df
ms.openlocfilehash: 68ada06514defe0f7f5332288ad8e91a7d8d9351
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59035532"
---
# <a name="ole-db-programming-overview"></a>OLE DB 프로그래밍 개요

OLE DB는 데이터베이스 성능이 우수 하 고 COM 기반 기술입니다. 저장 되는 형식에 관계 없이 데이터를 액세스 하는 일반적인 방법을 제공 합니다. 일반적인 비즈니스 상황에서는 방대한 양의 정보를 회사 데이터베이스에 저장 되지 않습니다. 이 정보는 인덱싱된 순차 파일 (예: 액세스) 개인 데이터베이스, 스프레드시트 (예: Excel), 프로젝트 계획 및 응용 프로그램 (예: 프로젝트의 경우) (예: Outlook) 전자 메일 (예: FAT 또는 NTFS)을 파일 시스템에 있습니다. OLE DB 데이터 저장소에 OLE DB 공급자와 동일한 방식으로 모든 종류의 데이터 저장소에 액세스할 수 있습니다.

OLE DB를 사용 하면 여부 DBMS이 든 상관 없이 다양 한 데이터 원본에 액세스 하는 응용 프로그램을 개발할 수 있습니다. OLE DB는 지정 된 데이터 원본에 대 한 해당 DBMS 기능을 지 원하는 COM 인터페이스를 사용 하 여 가능 범용 액세스 하 게 합니다. COM은 서비스의 불필요 한 중복을 줄이고 데이터 원본 뿐만 아니라 다른 응용 프로그램 간의 상호 운용성을 최대화 합니다.

## <a name="benefits-of-com"></a>COM의 이점

COM 제공 되는 위치입니다. OLE DB는 COM 인터페이스 집합입니다. 균일 한 인터페이스 집합을 통해 데이터에 액세스 하면 구성 요소 조합 행렬으로 데이터베이스를 구성할 수 있습니다.

COM 사양에 따라 OLE DB는 팩터링 하 고 일관 되 고 재사용 가능한 부분 DBMS 기능을 캡슐화 하는 인터페이스의 확장 가능 하 고 유지 관리 가능한 컬렉션을 정의 합니다. 이러한 인터페이스의 다양 한 정보 원본에 대 한 균일 한 트랜잭션 액세스를 사용 하도록 설정 하는 트랜잭션 코디네이터 행 컨테이너, 쿼리 프로세서 등의 DBMS 구성 요소 경계를 정의 합니다.

## <a name="see-also"></a>참고자료

[OLE DB 프로그래밍](../../data/oledb/ole-db-programming.md)<br/>
[OLE DB 소비자 템플릿(C++)](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB 템플릿](../../data/oledb/ole-db-templates.md)