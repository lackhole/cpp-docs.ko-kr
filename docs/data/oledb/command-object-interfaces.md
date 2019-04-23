---
title: 명령 개체 인터페이스
ms.date: 10/24/2018
helpviewer_keywords:
- command object interfaces [C++]
- command objects [OLE DB]
- OLE DB [C++], command object interfaces
ms.assetid: dacff5ae-252c-4f20-9ad7-4e602cc48536
ms.openlocfilehash: 755c44cf8d0cb5bf5066197bfd0ead3e0f25e1f9
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59032403"
---
# <a name="command-object-interfaces"></a>명령 개체 인터페이스

명령 개체는 `IAccessor` 인터페이스를 사용하여 매개 변수 바인딩을 지정합니다. 소비자는 `IAccessor::CreateAccessor`를 호출하고 여기에 `DBBINDING` 구조의 배열을 전달합니다. `DBBINDING`에는 열 바인딩에 대한 정보(형식, 길이 등)가 있습니다. 공급자가 이 구조를 받은 다음 데이터 전송 방법과 변환의 필요 여부를 결정합니다.

`ICommandText` 인터페이스는 텍스트 명령을 지정하는 방법을 제공합니다. `ICommandProperties` 인터페이스는 모든 명령 속성을 처리합니다.

## <a name="see-also"></a>참고자료

[OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
