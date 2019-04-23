---
title: OLE DB 소비자 및 공급자
ms.date: 10/22/2018
helpviewer_keywords:
- OLE DB providers, OLE DB data architecture
- OLE DB providers
- OLE DB consumers, OLE DB data architecture
- OLE DB consumers
- OLE DB, data model
ms.assetid: 886cb39d-652b-4557-93f0-4b1b0754d8bc
ms.openlocfilehash: f5940ca65e42787c3156a9537cb3f3f6694339c0
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59031315"
---
# <a name="ole-db-consumers-and-providers"></a>OLE DB 소비자 및 공급자

OLE DB 아키텍처는 소비자와 공급자의 모델을 사용합니다. 소비자를 사용 하면 데이터에 대 한 요청입니다. 공급자를 표 형식에서 데이터를 배치 하 고 소비자에 게 반환 하 여 이러한 요청에 응답 합니다. 공급자에서 소비자 수 있도록 하는 모든 호출을 구현 되어야 합니다.

엄밀한의 소비자는 모든 시스템 또는 응용 프로그램 코드 (OLE DB 구성 요소 불필요) OLE DB 인터페이스를 통해 데이터에 액세스 하는 합니다. 인터페이스는 공급자에서 구현 됩니다. 따라서 공급자는 OLE DB 데이터에 대 한 액세스를 캡슐화 하 고 다른 개체 (즉, 소비자)를 노출 하는 인터페이스를 구현 하는 소프트웨어 구성 요소입니다.

역할에 대 한 소비자 OLE DB 인터페이스;에서 메서드를 호출 OLE DB 공급자에 필요한 OLE DB 인터페이스를 구현합니다.

OLE DB 이러한 역할 항상 의미가 통하지, n 계층 상황에서 특히 때문에 용어 클라이언트와 서버를 방지 합니다. 소비자 다른 구성 요소를 제공 하는 계층의 구성 요소 일 수 있으므로 호출 클라이언트 구성 요소에 게 혼동 합니다. 또한 공급자 때로는 더 비슷하게 동작 서버 보다 데이터베이스 드라이버입니다.

## <a name="see-also"></a>참고자료

[OLE DB 프로그래밍](../../data/oledb/ole-db-programming.md)<br/>
[OLE DB 프로그래밍 개요](../../data/oledb/ole-db-programming-overview.md)