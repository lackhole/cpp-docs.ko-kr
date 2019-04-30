---
title: 공급자에 인터페이스 추가
ms.date: 10/29/2018
helpviewer_keywords:
- OLE DB provider templates, object interfaces
ms.assetid: b0fc7cf8-428a-4584-9d64-ce9074d0eb66
ms.openlocfilehash: c0452ca74509b65de3787af93bff41b3cb399c99
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62384974"
---
# <a name="adding-an-interface-to-your-provider"></a>공급자에 인터페이스 추가

인터페이스를 추가 하려는 개체는 확인 (데이터 원본, 행 집합, 명령 또는 세션 개체에 의해 생성 되는 일반적으로 **OLE DB 공급자 마법사**). 인터페이스를 추가 해야 하는 개체는 공급자에 게 현재 지원 하지 않습니다 하는 것입니다. 이 경우 실행를 **ATL OLE DB 공급자 마법사** 개체를 만들려고 합니다. 프로젝트를 마우스 오른쪽 단추로 클릭 **클래스 뷰**, 클릭 **추가** > **새 항목** 메뉴에서 선택 **설치 된**  >  **시각적 C++**   >  **ATL**를 클릭 하 고 **ATL OLEDB 공급자**. 인터페이스 코드를 별도 디렉터리에 저장 한 다음 공급자 프로젝트에 파일을 복사 하려는 경우

인터페이스를 지 원하는 새 클래스를 만든 경우 해당 클래스에서 상속 된 개체를 확인 합니다. 예를 들어, 클래스를 추가할 수 있습니다 `IRowsetIndexImpl` 행 집합 개체:

```cpp
template <class Creator>
class CCustomRowset :
    public CRowsetImpl< CCustomRowset<Creator>, CCustomWindowsFile, Creator>,
    public IRowsetIndexImpl< ... >
```

COM_INTERFACE_ENTRY 매크로 사용 하는 개체에서 COM_MAP에 인터페이스를 추가 합니다. 맵이 있는 경우 하나 만듭니다. 예를 들어:

```cpp
BEGIN_COM_MAP(CCustomRowset)
     COM_INTERFACE_ENTRY(IRowsetIndex)
END_COM_MAP()
```

행 집합 개체에 대 한 부모의 맵을 연결 개체는 부모 클래스에 위임할 수 있도록 개체입니다. 이 예제에서는 맵에 COM_INTERFACE_ENTRY_CHAIN 매크로 추가 합니다.

```cpp
BEGIN_COM_MAP(CCustomRowset)
     COM_INTERFACE_ENTRY(IRowsetIndex)
     COM_INTERFACE_ENTRY_CHAIN(CRowsetImpl)
END_COM_MAP()
```

## <a name="see-also"></a>참고자료

[OLE DB 공급자 템플릿을 사용하여 작업](../../data/oledb/working-with-ole-db-provider-templates.md)