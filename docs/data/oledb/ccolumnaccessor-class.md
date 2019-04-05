---
title: CColumnAccessor 클래스
ms.date: 11/04/2016
f1_keywords:
- CColumnAccessor
- ATL::CColumnAccessor
- ATL.CColumnAccessor
helpviewer_keywords:
- CColumnAccessor class
ms.assetid: 6ce1e67f-6a20-490d-9326-c168b43eee7e
ms.openlocfilehash: 2d65fb047e758f449ed76c954bb4ac0c3623f6dd
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59032130"
---
# <a name="ccolumnaccessor-class"></a>CColumnAccessor 클래스

삽입 된 소비자 코드를 생성합니다.

## <a name="syntax"></a>구문

```cpp
class CColumnAccessor : public CAccessorBase
```

## <a name="remarks"></a>설명

삽입 된 코드에서 모든 열은 별도 접근자로 바인딩됩니다. 이 클래스는 삽입된 된 코드에서 사용 해야 (예를 들어, 발생할 수 있는 것을 디버깅할 때) 하지만 일반적으로 필요가 또는 해당 메서드를 직접 사용 합니다.

`CColumnAccessor` 다른 접근자 클래스 메서드를 기능에 해당 하는 각각 다음 스텁 메서드를 구현 합니다.

- `CColumnAccessor` 생성자입니다. 인스턴스화하고 초기화는 `CColumnAccessor` 개체입니다.

- `CreateAccessor` 바인딩 구조 열에 대 한 메모리를 할당 하 고 열 데이터 멤버를 초기화 합니다.

- `BindColumns` 접근자에 열을 바인딩합니다.

- `SetParameterBuffer` 매개 변수에 대 한 버퍼를 할당합니다.

- `AddParameter` 매개 변수 입력 구조에 매개 변수 항목을 추가합니다.

- `HasOutputColumns` 접근자에 출력 열 여부를 결정 합니다.

- `HasParameters` 접근자에 매개 변수가 있는지 여부를 결정 합니다.

- `BindParameters` 열에 생성된 된 매개 변수를 바인딩합니다.

## <a name="requirements"></a>요구 사항

**헤더:** atldbcli.h

## <a name="see-also"></a>참고자료

[OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB 소비자 템플릿 참조](../../data/oledb/ole-db-consumer-templates-reference.md)