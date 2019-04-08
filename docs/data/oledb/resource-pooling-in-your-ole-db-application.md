---
title: OLE DB 응용 프로그램의 리소스 풀링
ms.date: 10/29/2018
helpviewer_keywords:
- OLE DB services [OLE DB], resource pooling
- resource pooling [OLE DB], services
- OLE DB, resource pooling
- OLE DB providers, resource pooling
ms.assetid: 2ead1bcf-bbd4-43ea-a307-bb694b992fc1
ms.openlocfilehash: 786c2b31bb93b0691d80885c86377e2afba8c1dc
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59029306"
---
# <a name="resource-pooling-in-your-ole-db-application"></a>OLE DB 응용 프로그램의 리소스 풀링

응용 프로그램의 풀링을 활용 하려면 데이터 소스를 통과 하 여 OLE DB 서비스를 호출 하는지 확인 해야 `IDataInitialize` 또는 `IDBPromptInitialize`합니다. 직접 사용 하는 경우 `CoCreateInstance` 공급자의 CLSID를 기반으로 하는 공급자를 호출 하려면 OLE DB 서비스가 호출 됩니다.

OLE DB 서비스에 연결 된 데이터 원본에 대 한 참조로 풀 유지 관리 `IDataInitialize` 또는 `IDBPromptInitialize` 보유 또는 사용 중인 연결 하기만 합니다. 풀도 인터넷 정보 서비스 (IIS) 또는 COM + 1.0 Services 환경 내에서 자동으로 유지 됩니다. 응용 프로그램 풀링을 외부 COM + 1.0 서비스 또는 IIS 환경를 활용 하는 경우에 대 한 참조 유지 해야 `IDataInitialize` 또는 `IDBPromptInitialize` 또는 하나 이상의 연결으로 유지 합니다. 풀 응용 프로그램에 대 한 마지막 연결 해제 될 때 소멸 가져오기 하지 있는지, 참조를 보관할 또는 응용 프로그램의 수명에 대 한 연결을 유지 합니다.

OLE DB 서비스는 연결 시 그려지는 풀을 확인 하는 `Initialize` 라고 합니다. 연결 풀에서 가져온 후 다른 풀으로 이동할 수 없습니다. 따라서 호출 등의 초기화 정보를 변경 하는 응용 프로그램에서 작업 수행을 방지 `UnInitialize` 치거나 `QueryInterface` 호출 하기 전에 공급자별 인터페이스용 `Initialize`합니다. 또한 DBPROMPT_NOPROMPT 이외의 프롬프트 값으로 설정 된 연결 풀링 되지 않습니다. 그러나 프롬프트를 통해 설정 되는 연결에서 검색 초기화 문자열 동일한 데이터 소스에 추가 풀링된 연결에 사용할 수 있습니다.

일부 공급자는 각 세션에 대 한 별도 연결을 확인 해야 합니다. 있을 경우 이러한 추가 연결이 분산 트랜잭션에 별도로 등록 해야 합니다. OLE DB 캐시 서비스 및 데이터 원본 마다 단일 세션을 다시 사용 하지만 경우에 단일 데이터 원본에서 한 번에 둘 이상의 세션을 요청 하는 응용 프로그램, 공급자 수 추가 연결을 설정 하 고 추가 트랜잭션 인 리스트 먼 트를 수행 하는 풀링된 되지 않습니다. 이 단일 데이터 원본에서 여러 세션을 만드는 보다 풀링된 환경의 각 세션에 대 한 별도 데이터 원본을 만들려면 더 효율적입니다.

마지막으로, ADO 자동으로 사용 하므로 OLE DB 서비스에 연결 하려면 ADO를 사용 하 고 풀링 및 인 리스트 먼 트 자동으로 수행 합니다.

## <a name="see-also"></a>참고자료

[OLE DB 리소스 풀링 및 서비스](../../data/oledb/ole-db-resource-pooling-and-services.md)