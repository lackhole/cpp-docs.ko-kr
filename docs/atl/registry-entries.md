---
title: 레지스트리 항목 (ATL)
ms.date: 11/04/2016
helpviewer_keywords:
- registry, ATL services entries
- registry, application IDs
ms.assetid: 881989b7-61bb-459a-a13e-3bfcb33e184e
ms.openlocfilehash: 7a89bc5d510d493f557b7ea74b8eabe5dfd87ac1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62196757"
---
# <a name="registry-entries"></a>레지스트리 항목

DCOM 레지스트리에서 중앙 집중화 된 위치에 하나 이상의 DCOM 개체에 대 한 구성 옵션을 그룹화 하는 응용 프로그램 id (Appid)를 개념을 도입 했습니다. 개체의 CLSID 값 이라는 AppID에 해당 값을 지정 하 여 AppID를 지정 합니다.

기본적으로 ATL에서 생성 된 서비스를 GUID와의 CLSID는 AppID에 대해 사용합니다. 아래 `HKEY_CLASSES_ROOT\AppID`, DCOM 관련 항목을 지정할 수 있습니다. 처음에 두 개의 항목이 있습니다.

- `LocalService`를 서비스의 이름에는 값을 사용 하 여 합니다. 이 값이 있는 경우 대신 사용 됩니다는 `LocalServer32` CLSID 아래에 있는 키입니다.

- `ServiceParameters`를 값과 같은 `-Service`합니다. 이 값이 시작 될 때 서비스에 전달 되는 매개 변수를 지정 합니다. 이러한 매개 변수는 서비스에 전달 되는 참고 `ServiceMain` 작동 하지 `WinMain`합니다.

DCOM 서비스에서 다른 키를 만들려면 해야 `HKEY_CLASSES_ROOT\AppID`합니다. 이 키가 exe 파일의 이름으로와 같고 AppID 항목 다시 가리키는 AppID 값을 포함 하는 대로 상호 참조를 역할도 합니다.

## <a name="see-also"></a>참고자료

[서비스](../atl/atl-services.md)
