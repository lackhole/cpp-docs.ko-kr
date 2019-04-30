---
title: 미리 정의된 기호 ID
ms.date: 02/14/2019
helpviewer_keywords:
- symbols [C++], predefined IDs
- predefined symbol IDs
ms.assetid: 91a5d610-1a04-47e8-b8a4-63ad650a90df
ms.openlocfilehash: 5acaf9d470ce3d1cccad65bc8235cacfd7a56427
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62362298"
---
# <a name="predefined-symbol-ids"></a>미리 정의된 기호 ID

새 프로젝트를 시작하면 프로젝트 형식에 따라 일부 기호 ID가 바로 사용할 수 있도록 미리 정의되어 있습니다. 이러한 기호 ID는 다양한 라이브러리와 MFC 등의 프로젝트 형식을 지원합니다. 이 ID는 응용 프로그램에 대체로 포함되는 일반 작업 또는 마우스나 프린터와 같은 하드웨어 항목의 작업 등을 나타냅니다.

이러한 기호 ID는 리소스 작업을 할 때 중요해집니다. 액셀러레이터 키 테이블을 편집 하 고 그 중 일부가 이미 가상 키와 연결 하는 경우 사용할 수 있습니다. 통해 사용할 하기도 합니다 [속성 창](/visualstudio/ide/reference/properties-window)합니다. 미리 정의 된 기호 Id 중 하나를 새 리소스에 할당할 수 있습니다 또는 및 ID는 해당 키 조합과 자동으로 연결 하는 기호를 사용 하 여 관련 기능에 액셀러레이터 키를 할당할 수 있습니다.

라이브러리는 미리 정의 된 프로젝트의 일부로 표시 되는 기호:

- [미리 정의된 ATL 기호](../windows/atl-predefined-symbols.md)

- [미리 정의된 MFC 기호](../windows/mfc-predefined-symbols.md)

- [미리 정의된 Win32 기호](../windows/win32-predefined-symbols.md)

> [!NOTE]
> 미리 정의된 기호는 항상 읽기 전용입니다.

## <a name="requirements"></a>요구 사항

Win32, MFC 또는 ATL

## <a name="see-also"></a>참고자료

[리소스 식별자(기호)](../windows/symbols-resource-identifiers.md)<br/>
[방법: 기호 만들기](../windows/creating-new-symbols.md)<br/>
[방법: 기호 관리](../windows/changing-a-symbol-or-symbol-name-id.md)<br/>