---
title: OLE DB 공급자 만들기
ms.date: 10/13/2018
helpviewer_keywords:
- OLE DB providers, creating
- OLE DB provider templates, creating providers
ms.assetid: f73017c3-c89f-41a6-a306-ea992cf6092c
ms.openlocfilehash: 3e46e87b0d5d538a0f9fd7e231debfef3fa95210
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59036116"
---
# <a name="creating-an-ole-db-provider"></a>OLE DB 공급자 만들기

OLE DB 공급자를 만들려면 마법사를 사용 하 여 ATL COM 프로젝트를 만들고 공급자를 다음 OLE DB 템플릿을 사용 하 여 파일을 수정 하는 것이 좋습니다. 공급자를 사용자 지정할 때에 필요 없는 속성 주석 수 있으며 선택적 인터페이스를 추가할 수 있습니다.

기본 단계는 다음과 같습니다.

1. 사용 합니다 **ATL 프로젝트 마법사** 기본 프로젝트 파일을 만들려면 및 **ATL OLEDB 공급자 마법사** 공급자를 만들려면 (선택 **ATL OLEDB 공급자** 합니다 에서**설치 됨** > **Visual c + +** > **ATL** 폴더에 **새 항목 추가**).

   > [!NOTE]
   > 프로젝트에 MFC 지원을 추가 하기 전에 포함 해야 합니다는 **ATL OLEDB 공급자**합니다.

1. 코드를 수정 합니다 `Execute` 의 메서드 [CCustomRowset(CustomRS.h)](cmyproviderrowset-myproviderrs-h.md)합니다. 예를 들어 참조 [OLE DB 공급자로 문자열 읽어들이기](../../data/oledb/reading-strings-into-the-ole-db-provider.md)합니다.

1. 맵 속성 편집 [CustomDS.h](cmyprovidersource-myproviderds-h.md)를 [CustomSess.h](cmyprovidersession-myprovidersess-h.md), 및 [CustomRS.h](cmyproviderrowset-myproviderrs-h.md)합니다. 마법사는 공급자가 구현 하는 모든 속성을 포함 하는 속성 맵을 만듭니다. 속성 맵을 진행 하 고 제거 또는 공급자에 게 지 원하는 데 필요 없는 속성 주석입니다.

1. 에 있는 PROVIDER_COLUMN_MAP를 업데이트할 [CCustomRowset(CustomRS.h)](cmyproviderrowset-myproviderrs-h.md)합니다. 예를 들어 참조 [OLE DB 공급자에 문자열 저장](../../data/oledb/storing-strings-in-the-ole-db-provider.md)합니다.

1. 공급자를 테스트할 준비가 되었을 때 공급자 열거 목록에서 공급자를 찾으려고 시도 하 여 테스트할 수 있습니다. 공급자를 찾는 열거형에는 테스트 코드의 예제를 참조 하세요. 합니다 [CATDB](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/OLEDB/Consumer/catdb) 및 [DBVIEWER](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/OLEDB/Consumer/dbviewer) 샘플 또는에서 예제 [단순 소비자 구현](../../data/oledb/implementing-a-simple-consumer.md)합니다.

1. 원하는 추가 인터페이스를 추가 합니다. 예를 들어 참조 [간단한 읽기 전용 공급자의 기능 향상](../../data/oledb/enhancing-the-simple-read-only-provider.md)합니다.

   > [!NOTE]
   > 기본적으로 마법사는 OLE DB 수준 0과 호환 되는 코드를 생성 합니다. 응용 프로그램 수준 0 규격 유지 되도록 코드에서 마법사에서 생성 된 인터페이스 중 하나를 제거 하지 마십시오.

## <a name="see-also"></a>참고자료

[CatDB 샘플: 데이터 원본 스키마 브라우저](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/OLEDB/Consumer/catdb)<br/>
[DBViewer 샘플: 데이터베이스 브라우저](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/OLEDB/Consumer/dbviewer)
