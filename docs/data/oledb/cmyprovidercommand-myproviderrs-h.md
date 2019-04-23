---
title: CCustomCommand (CustomRS.H)
ms.date: 10/22/2018
f1_keywords:
- cmyprovidercommand
- myproviderrs.h
- ccustomcommand
- customrs.h
helpviewer_keywords:
- OLE DB providers, wizard-generated files
- CMyProviderCommand class in MyProviderRS.H
- CCustomCommand class in CustomRS.H
ms.assetid: b30b956e-cc91-4cf5-9fe6-f8b1ce9cc2a5
ms.openlocfilehash: b10d7bccae6fa9b86d072b8e13791f23516b2c63
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59028563"
---
# <a name="ccustomcommand-customrsh"></a>CCustomCommand (CustomRS.H)

`CCustomCommand` 클래스는 공급자 명령 개체에 대 한 구현 합니다. 에 대 한 구현을 제공 합니다 `IAccessor`, `ICommandText`, 및 `ICommandProperties` 인터페이스입니다. `IAccessor` 인터페이스 행 집합에 있는 것과 같습니다. 명령 개체 매개 변수에 대 한 바인딩을 지정 하는 접근자를 사용 합니다. 행 집합 개체 하는 데 사용 출력 열에 대 한 바인딩을 지정 합니다. `ICommandText` 인터페이스는 텍스트 방식으로 명령을 지정 하는 유용한 방법입니다. 이 예제에서는 합니다 `ICommandText` 사용자 지정 코드를 추가 하는 경우 나중에 인터페이스; 또한 재정의 `ICommand::Execute` 메서드. `ICommandProperties` 모든 명령 및 행 집합 개체에 대 한 속성을 처리 하는 인터페이스입니다.

```cpp
// CCustomCommand
class ATL_NO_VTABLE CCustomCommand :
class ATL_NO_VTABLE CCustomCommand :
   public CComObjectRootEx<CComSingleThreadModel>,
   public IAccessorImpl<CCustomCommand>,
   public ICommandTextImpl<CCustomCommand>,
   public ICommandPropertiesImpl<CCustomCommand>,
   public IObjectWithSiteImpl<CCustomCommand>,
   public IConvertTypeImpl<CCustomCommand>,
   public IColumnsInfoImpl<CCustomCommand>
```

`IAccessor` 인터페이스는 명령 및 행 집합에서 사용 되는 모든 바인딩을 관리 합니다. 소비자 호출 `IAccessor::CreateAccessor` 배열을 사용 하 여 `DBBINDING` 구조입니다. 각 `DBBINDING` 구조 열 바인딩 (예: 형식 및 길이) 처리 하는 방법에 대 한 정보가 들어 있습니다. 공급자는 구조를 받고 그런 다음 데이터를 전송 하는 방법 및 변환이 필요한 지 여부를 결정 합니다. `IAccessor` 인터페이스 명령의 모든 매개 변수를 처리 하기에 명령 개체에서 사용 됩니다.

명령 개체의 구현을 제공 `IColumnsInfo`합니다. OLE DB에서 필요 합니다 `IColumnsInfo` 인터페이스입니다. 인터페이스를 소비자를 명령의 매개 변수에 대 한 정보를 검색할 수 있습니다. 행 집합 개체가 사용 하는 `IColumnsInfo` 공급자에 출력 열에 대 한 정보를 반환 하는 인터페이스입니다.

공급자에는 또한 라는 인터페이스가 있습니다 `IObjectWithSite`합니다. `IObjectWithSite` 인터페이스 ATL 2.0에 구현 된와 구현 자가 해당 자식에 자체에 대 한 정보를 전달할 수 있습니다. 명령 개체를 사용 하 여 `IObjectWithSite` 정보를 모든 사용자가 만든 사람에 대 한 행 집합 개체를 생성 합니다.

## <a name="see-also"></a>참고자료

[공급자 마법사가 생성하는 파일](../../data/oledb/provider-wizard-generated-files.md)