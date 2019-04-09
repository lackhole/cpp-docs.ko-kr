---
title: 단순 소비자 만들기
ms.date: 11/06/2018
helpviewer_keywords:
- OLE DB consumers, creating
ms.assetid: ae32d657-72ea-4db8-9839-75cb5cff68ae
ms.openlocfilehash: 060a39a8436ff73900ebfaea7d1c882b9862ee7e
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59025139"
---
# <a name="creating-a-simple-consumer"></a>단순 소비자 만들기

사용 합니다 **ATL 프로젝트 마법사** 및 **ATL OLE DB 소비자 마법사** OLE DB 템플릿 소비자를 생성 합니다.

## <a name="to-create-a-console-application-for-an-ole-db-consumer"></a>OLE DB 소비자에 대 한 콘솔 응용 프로그램을 만들려면

1. **파일** 메뉴에서 **새로 만들기**를 클릭한 다음 **프로젝트**를 클릭합니다.

   **새 프로젝트** 대화 상자가 나타납니다.

1. 에 **프로젝트 형식** 창 클릭 합니다 **설치 됨** > **Visual c + +** > **Windows Desktop** 폴더 클릭 하 고는 **Windows 데스크톱 마법사** 아이콘에는 **템플릿** 창입니다. 에 **이름을** 상자에 예를 들어 프로젝트의 이름을 입력 합니다 *MyCons*합니다.

1. **확인**을 클릭합니다.

   합니다 **Windows 데스크톱 프로젝트** 마법사가 나타납니다.

1. 에 **응용 프로그램 설정** 페이지에서 **콘솔 응용 프로그램**를 선택한 후 **ATL에 대 한 공용 헤더 파일을 추가**합니다.

1. 클릭 **확인** 마법사를 닫고 프로젝트를 생성 합니다.

다음을 사용 하 여 합니다 **ATL OLE DB 소비자 마법사** OLE DB 소비자 개체를 추가 합니다.

## <a name="to-create-a-consumer-with-the-atl-ole-db-consumer-wizard"></a>ATL OLE DB 소비자 마법사를 사용 하 여 소비자를 만들려면

1. **솔루션 탐색기**에서 `MyCons` 프로젝트를 마우스 오른쪽 버튼으로 클릭합니다.

1. 바로 가기 메뉴에서 클릭 **추가**를 클릭 하 고 **새 항목**합니다.

   **새 항목 추가** 대화 상자가 나타납니다.

1. 에 **범주** 창 클릭 **설치 됨** > **Visual c + +** > **ATL**를 클릭 합니다 **ATL OLEDB 소비자** 아이콘에는 **템플릿** 창과 클릭 **추가**합니다.

   합니다 **ATL OLEDB 소비자 마법사** 나타납니다.

1. 클릭 합니다 **데이터 원본** 단추입니다.

   합니다 **데이터 연결 속성** 대화 상자가 나타납니다.

1. 에 **데이터 연결 속성** 대화 상자에서 다음을 수행 합니다.

   1. 에 **공급자** 탭에서 OLE DB 공급자를 지정 합니다.

   1. 에 **연결** 탭에서 서버의 데이터 원본 및 데이터베이스에 대 한 암호, 서버 이름 및 로그온 ID 등 필요한 정보를 지정 합니다.

      > [!NOTE]
      > 보안 문제가 합니다 **암호 저장 허용** 의 기능을 **데이터 연결 속성** 대화 상자. **서버에 로그온 정보 입력**, 두 개의 라디오 단추가 있습니다. **사용 하 여 Windows NT 통합 보안** 하 고 **특정 사용자 이름 및 암호를 사용 하 여**입니다.

      > [!NOTE]
      > 선택 하는 경우 **특정 사용자 이름 및 암호를 사용 하 여**, 암호를 저장할 수 있습니다 (사용 하 여 합니다 **암호 저장 허용** 확인란) 하지만이 옵션은 안전 하지 않습니다. 선택 하는 것이 좋습니다 **사용 하 여 Windows NT 통합 보안**;이 옵션 Windows NT를 사용 하 여 id를 확인 합니다.

      > [!NOTE]
      > 암호에 대 한 사용자에 게 프롬프트 또는 암호를 보호 하는 보안 메커니즘을 사용 하 여 위치에 저장 하려면 중간 계층 응용 프로그램을 사용 해야 Windows NT 통합 보안을 사용 하지 못하면 (대신 소스 코드에서).

   1. 공급자와 다른 설정을 선택한 후 클릭 **연결 테스트** 이전 대화 상자 페이지에서 선택한 내용을 확인 합니다. 경우는 **결과** 보고서 상자 `Test connection succeeded`, 클릭 **확인** 데이터 링크를 만듭니다.

   합니다 **데이터베이스 개체 선택** 대화 상자가 나타납니다.

1. 트리 컨트롤을 사용 하 여 테이블, 뷰 또는 저장된 프로시저를 선택 합니다. 예를 들어 선택 합니다 `Products` 에서 테이블을 `Northwind` 데이터베이스입니다.

1. **확인**을 클릭합니다. 이 반환 하는 **ATL OLE DB 소비자 마법사**합니다.

1. 마법사 완료의 이름을 `Class` 하 고 **.h 파일** 또는 저장 프로시저 선택한 테이블, 뷰 이름에 따라 합니다. 원하는 경우이 이름을 편집할 수 있습니다.

1. 선택을 취소 합니다 **특성 사용** 마법사를 사용 하 여 소비자 코드를 만들 수 있도록 확인란 [OLE DB 템플릿 클래스](../../data/oledb/ole-db-consumer-templates-reference.md) 기본값 대신 [OLE DB 소비자 특성](../../windows/ole-db-consumer-attributes.md)합니다.

1. 아래 **형식**를 선택 **명령**입니다.

   만들어집니다를 [CCommand](../../data/oledb/ccommand-class.md)-선택 하는 경우 소비자 기반 **명령** 또는 [CTable](../../data/oledb/ctable-class.md)-선택 하는 경우 소비자 기반 **테이블**합니다. 테이블이 나 명령 클래스는 선택한 개체를 따서 명명 된 있지만 이름을 편집할 수 있습니다.

1. 아래 **지원**를 유지 합니다 **변경**, **삽입**, 및 **삭제** 상자 선택이 취소.

   선택 된 **변경**, **삽입**, 및 **삭제** 변경, 삽입 및 삭제 된 행 집합의 레코드에 있는 확인란입니다. 저장소 데이터에 데이터를 작성 하는 방법에 대 한 자세한 내용은 참조 하십시오 [행 집합 업데이트](../../data/oledb/updating-rowsets.md)합니다.

1. 클릭 **완료** 여 소비자를 만듭니다.

에 표시 된 대로 마법사를 명령 클래스 및 사용자 레코드 클래스를 생성 [소비자 마법사 생성 클래스](../../data/oledb/consumer-wizard-generated-classes.md)합니다. 명령 클래스 이름에 입력 해야 합니다.는 `Class` 마법사에서 상자 (여기서 `CProducts`), 사용자 레코드 클래스 형식의 이름을 갖습니다 "*ClassName*접근자" (이 예제의 경우 `CProductsAccessor`).

> [!NOTE]
> 마법사에 다음 줄을 배치 `Products.h`:

```cpp
#error Security Issue: The connection string may contain a password
```

> [!NOTE]
> 이 줄 소비자 응용 프로그램이 컴파일되지 않도록 방지 하 고 하드 코드 된 암호에 대 한 연결 문자열에 체크 인할 수를 표시 합니다. 연결 문자열을 확인 한 후이 코드 줄을 제거할 수 있습니다.

## <a name="see-also"></a>참고자료

[마법사를 사용하여 OLE DB 소비자 만들기](../../data/oledb/creating-an-ole-db-consumer-using-a-wizard.md)
