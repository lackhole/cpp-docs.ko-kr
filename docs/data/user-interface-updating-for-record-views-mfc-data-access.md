---
title: 레코드 뷰의 사용자 인터페이스 업데이트  (MFC Data Access)
ms.date: 11/04/2016
helpviewer_keywords:
- user interfaces, updating
- menus, updating as context changes
- record views, user interface
ms.assetid: 2c7914b6-2dc3-40c3-b2f2-8371da2a4063
ms.openlocfilehash: de94b28e713459edfd63aff832caecc7ea49ca33
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62152646"
---
# <a name="user-interface-updating-for-record-views--mfc-data-access"></a>레코드 뷰의 사용자 인터페이스 업데이트  (MFC Data Access)

`CRecordView` 탐색 명령에 대 한 기본 사용자 인터페이스 업데이트 처리기를 제공합니다. 이러한 처리기는 사용자 인터페이스 개체(메뉴 항목 및 도구 모음 단추)를 자동으로 시용하거나 사용하지 않도록 설정합니다. 표준 메뉴를 제공 하는 응용 프로그램 마법사를 선택 하는 경우는 **도킹 가능한 도구 모음** 옵션을 명령에 대 한 도구 모음 단추 집합을 합니다. `CRecordView`를 사용하여 레코드 뷰 클래스를 만드는 경우 응용 프로그램에 비슷한 사용자 인터페이스 개체를 추가할 수 있습니다.

### <a name="to-create-menu-resources-with-the-menu-editor"></a>메뉴 편집기를 사용하여 메뉴 리소스를 만들려면

1. 사용에 대 한 정보를 참조 하는 [메뉴 편집기](../windows/menu-editor.md)를 같은 명령 4를 사용 하 여 메뉴를 만듭니다.

#### <a name="to-create-toolbar-buttons-with-the-graphics-editor"></a>그래픽 편집기를 사용하여 도구 모음 단추를 만들려면

1. 사용에 대 한 정보를 참조 하는 [도구 모음 편집기](../windows/toolbar-editor.md), 도구 모음 리소스를 편집 해 레코드 탐색 명령에 대 한 도구 모음 단추를 추가 합니다.

## <a name="see-also"></a>참고자료

[레코드 뷰에서의 탐색 지원](../data/supporting-navigation-in-a-record-view-mfc-data-access.md)<br/>
[레코드 뷰 사용](../data/using-a-record-view-mfc-data-access.md)