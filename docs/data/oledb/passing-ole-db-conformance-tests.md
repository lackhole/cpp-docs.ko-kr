---
title: OLE DB 적합성 테스트 통과
ms.date: 11/04/2016
helpviewer_keywords:
- testing, OLE DB providers
- testing providers
- conformance testing
- conformance testing [OLE DB]
- OLE DB providers, testing
ms.assetid: d1a4f147-2edd-476c-b452-0e6a0ac09891
ms.openlocfilehash: 9f78b16bc30651560137a39286460a8e5ceccd40
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59036999"
---
# <a name="passing-ole-db-conformance-tests"></a>OLE DB 적합성 테스트 통과

Data Access SDK에는 공급자를 일관 되 게 하려면 OLE DB 적합성 테스트 집합을 제공 합니다. 테스트는 공급자의 모든 측면을 확인 하 고 공급자 함수를 예상 하는 적절 한 보증을 제공 합니다. Microsoft Data Access SDK에 OLE DB 적합성 테스트를 찾을 수 있습니다. 이 섹션에서는 적합성 테스트 통과 위해 수행 해야 할 작업에 중점을 둡니다. OLE DB 적합성 테스트를 실행 하는 방법에 대 한 내용은 SDK를 참조 하세요.

## <a name="running-the-conformance-tests"></a>규칙 테스트 실행

시각적 개체의 C++ 6.0에서는 OLE DB 공급자 템플릿 다양 한 값과 속성을 확인할 수 있도록 함수를 후크를 추가 합니다. 이러한 함수 중 대부분은 규칙 테스트에 대 한 응답에 추가 되었습니다.

> [!NOTE]
> OLE DB 적합성 테스트 통과를 공급자에 대해 여러 유효성 검사 함수를 추가 해야 합니다.

이 공급자에는 두 가지 유효성 검사 루틴에 필요합니다. 첫 번째 루틴 `CRowsetImpl::ValidateCommandID`, 행 집합 클래스의 일부입니다. 행 집합을 만드는 동안 공급자 템플릿에 의해 호출 됩니다. 샘플이이 루틴을 사용 하 여 알릴 소비자는 인덱스를 지원 하지 않습니다. 첫 번째 호출 하는 것 `CRowsetImpl::ValidateCommandID` (공급자를 사용 하는 참고 합니다 `_RowsetBaseClass` 의 인터페이스 맵에 추가 하는 typedef `CCustomRowset` 에서 [공급자의 책갈피 지원](../../data/oledb/provider-support-for-bookmarks.md)템플릿의 해당 긴 줄을 입력 하지 않아도 되므로 인수)입니다. 인덱스 매개 변수 (이 나타내는 바로 여기 인덱스를 사용 하는 소비자가) NULL이 아닌 경우에 어 DB_E_NOINDEX를 반환 합니다. 명령 Id에 대 한 자세한 내용은 OLE DB 사양을 참조 하 고 검색할 `IOpenRowset::OpenRowset`합니다.

다음 코드는는 `ValidateCommandID` 유효성 검사 과정:

```cpp
/////////////////////////////////////////////////////////////////////
// CustomRS.H
// Class: CCustomRowset

HRESULT ValidateCommandID(DBID* pTableID, DBID* pIndexID)
{
   HRESULT hr = _RowsetBaseClass::ValidateCommandID(pTableID, pIndexID);
   if (hr != S_OK)
      return hr;

   if (pIndexID != NULL)
      return DB_E_NOINDEX;    // Doesn't support indexes

   return S_OK;
}
```

공급자 템플릿 호출의 `OnPropertyChanged` DBPROPSET_ROWSET 그룹의 속성을 누군가 변경 될 때마다 메서드. 적절 한 개체에 추가할 다른 그룹에 대 한 속성을 처리 하려는 경우 (즉, DBPROPSET_SESSION 검사 진행을 `CCustomSession` 클래스).

먼저 코드 속성에 다른 연결 되었는지 여부를 확인 합니다. 속성에 연결 될 경우 DBPROP_BOOKMARKS 속성을 설정 `True`합니다. OLE DB 사양의 부록 C는 속성에 대 한 정보를 포함합니다. 이 정보 또한 알려 속성에 다른 연결 되었는지 여부입니다.

추가할 수도 있습니다는 `IsValidValue` 일상적인 코드입니다. 템플릿 호출 `IsValidValue` 속성을 설정 하려고 할 때입니다. 속성 값을 설정 하는 경우 추가 처리가 필요한 경우이 메서드를 재정의 됩니다. 각 속성 집합에 대해 이러한 메서드 중 하나가 있습니다.

## <a name="see-also"></a>참고자료

[고급 공급자 기술](../../data/oledb/advanced-provider-techniques.md)