---
title: 공급자 만들기
ms.date: 10/15/2018
helpviewer_keywords:
- OLE DB providers, creating
ms.assetid: 2506ba8f-010d-4231-aac1-387432f7b6b9
ms.openlocfilehash: 6258b5247e4d9d027e0f03bc133dff1a059665bd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62361868"
---
# <a name="creating-the-provider"></a>공급자 만들기

## <a name="to-create-an-ole-db-provider-with-the-atl-ole-db-provider-wizard"></a>ATL OLE DB 공급자 마법사를 사용하여 OLE DB 공급자를 만들려면

1. 프로젝트를 마우스 오른쪽 단추로 클릭합니다.

1. 바로 가기 메뉴에서 **추가**를 클릭한 다음 **클래스 추가**를 클릭합니다.

1. **클래스 추가 대화 상자**에서 **설치됨** > **Visual C++** > **ATL**, **ATL OLEDB 공급자** 아이콘을 선택하고 **열기**를 클릭합니다.

1. **ATL OLE DB 공급자 마법사**의 **약식 이름** 상자에 공급자의 약식 이름을 입력합니다. 다음 항목에서는 약식 이름을 사용하지만 다른 이름을 사용해도 됩니다. 입력한 이름에 따라 다른 이름 상자가 채워집니다.

1. 필요하면 다른 이름 상자를 편집합니다. 개체 이름과 파일 이름뿐만 아니라 다음 항목을 편집할 수 있습니다.

   - **Coclass**: COM 공급자를 사용 하는 이름입니다.

   - **ProgID**: 프로그래밍 방식 식별자를 GUID 대신 사용할 수 있는 텍스트 문자열입니다.

   - **버전**: ProgID와 Coclass 버전별 프로그래밍 방식으로 ID를 생성 하는 데 사용

1. **마침**을 클릭합니다.

## <a name="see-also"></a>참고자료

[OLE DB 공급자 만들기](../../data/oledb/creating-an-ole-db-provider.md)
