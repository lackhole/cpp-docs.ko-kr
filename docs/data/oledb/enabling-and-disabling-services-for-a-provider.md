---
title: 공급자 서비스 사용 및 사용 안 함
ms.date: 10/29/2018
helpviewer_keywords:
- OLE DB services [OLE DB], enabling and disabling
- service providers [OLE DB]
ms.assetid: 3deac1bb-f660-407a-92ef-95e139e280c0
ms.openlocfilehash: d91f08accf1a8be69f63d6bbcaa4c620d68c1077
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59033033"
---
# <a name="enabling-and-disabling-services-for-a-provider"></a>공급자 서비스 사용 및 사용 안 함

기본적으로 단일 공급자에 액세스하는 모든 응용 프로그램에 대해 개별 OLE DB 서비스를 사용하거나 사용하지 않을 수 있습니다. 공급자의 CLSID에 다음 표에서와 같이 서비스 사용 또는 사용하지 않음을 지정하는 DWORD 값을 지정하여 OLEDB_SERVICES 레지스트리 항목을 추가하면 됩니다.

|기본 서비스를 사용 하도록 설정|키워드 값|
|------------------------------|-------------------|
|모든 서비스 (기본값)|0xffffffff|
|Pooling과 AutoEnlistment를 제외한 모든 서비스|0xfffffffe|
|Client Cursor를 제외한 모든 서비스|0xfffffffb|
|Pooling, AutoEnlistment, Client Cursor를 제외한 모든 서비스|0xfffffff0|
|서비스 사용 안 함|0x00000000|
|집계 없음, 모든 서비스 사용 안 함|\<누락 된 키 >|

## <a name="see-also"></a>참고자료

[OLE DB 서비스 사용 및 사용 안 함](../../data/oledb/enabling-and-disabling-ole-db-services.md)