---
title: 'CFixedStringT: 사용자 지정 문자열 관리자의 예'
ms.date: 11/04/2016
helpviewer_keywords:
- CFixedStringT class, using a custom string manager
ms.assetid: 1cf11fd7-51b8-4b94-87af-02bc25f47dd6
ms.openlocfilehash: 2b6da5d4166b220ef63500d0154ab32dc72b40f4
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57740709"
---
# <a name="cfixedstringt-example-of-a-custom-string-manager"></a>CFixedStringT: 사용자 지정 문자열 관리자의 예

ATL 라이브러리 구현 클래스에서 사용 하는 사용자 지정 문자열 관리자의 예로 [CFixedStringT](../atl-mfc-shared/reference/cfixedstringt-class.md)라는 **CFixedStringMgr**합니다. `CFixedStringT` 파생 됩니다 [CStringT](../atl-mfc-shared/reference/cstringt-class.md) 의 일부로 해당 문자 데이터를 할당 하는 문자열을 구현 하는 `CFixedStringT` 문자열을 사용 하면 지정한 길이 보다 작으면으로 개체 자체를 `t_nChars` 의템플릿매개변수`CFixedStringT`. 이 방법을 사용 하 여 문자열 필요는 없습니다 힙 전혀 문자열의 길이가 고정된 버퍼의 크기 이상으로 증가 하지 않으면. 때문에 `CFixedStringT` 는 항상 사용 하 여 문자열 데이터를 할당할 힙을 사용할 수 없으므로 `CAtlStringMgr` 해당 문자열 관리자. 사용자 지정 문자열 관리자를 사용 하 여 (`CFixedStringMgr`)를 구현 합니다 [IAtlStringMgr](../atl-mfc-shared/reference/iatlstringmgr-class.md) 인터페이스입니다. 이 인터페이스에 설명 되어 [사용자 지정 문자열 관리자 구현 (고급 방법)](../atl-mfc-shared/implementation-of-a-custom-string-manager-advanced-method.md)합니다.

에 대 한 생성자 `CFixedStringMgr` 세 매개 변수를 사용 합니다.

- *pData:* 고정된 포인터로 `CStringData` 사용할 구조입니다.

- *nChars:* 최대 문자 수는 `CStringData` 구조를 포함할 수 있습니다.

- *pMgr:* 에 대 한 포인터를 `IAtlStringMgr` 인터페이스의 "백업 문자열 관리자"입니다.

값을 저장 하는 생성자 *pData* 하 고 *pMgr* 는 각 멤버 변수에 (`m_pData` 및 `m_pMgr`). 고정된 버퍼와의 참조 횟수를-1의 최대 크기와 같은 사용 가능한 길이 0으로 버퍼의 길이 설정 합니다. 참조 개수 값을 나타내는 버퍼 잠겨의이 인스턴스를 사용 하 여 `CFixedStringMgr` 문자열 관리자입니다.

다른 것을 금지 버퍼 됨으로 잠긴 `CStringT` 버퍼에 대 한 공유 참조를 보유 하는 인스턴스에서 합니다. 다른 `CStringT` 인스턴스 수에 포함 된 버퍼에 대 한 버퍼를 공유 하도록 허용 된 `CFixedStringT` 다른 문자열 버퍼를 사용한 계속 하는 동안 삭제 됩니다.

`CFixedStringMgr` 전체 구현 된 `IAtlStringMgr` 인터페이스입니다. 각 메서드의 구현은 개별적으로 설명 되어 있습니다.

## <a name="implementation-of-cfixedstringmgrallocate"></a>CFixedStringMgr::Allocate 구현

구현의 `CFixedStringMgr::Allocate` 문자열의 요청된 된 크기는 고정된 버퍼의 크기 보다 작거나 같은 경우 첫 번째 확인 (에 저장 된 `m_pData` 멤버). 고정된 버퍼 충분히 큰 경우 `CFixedStringMgr` 길이가 0 인 고정된 버퍼를 잠급니다. 문자열 길이 고정된 버퍼의 크기 이상으로 증가 하지으로 `CStringT` 버퍼를 다시 할당 해야 합니다.

문자열의 요청 된 크기가 고정 된 버퍼 보다 큰 경우 `CFixedStringMgr` 문자열 백업 관리자에 게 요청을 전달 합니다. 백업 문자열 관리자 힙에서 버퍼를 할당으로 간주 됩니다. 그러나이 버퍼를 반환 하기 전에 `CFixedStringMgr` 버퍼를 잠그고 버퍼의 문자열 manager 포인터에 대 한 포인터를 사용 하 여 대체는 `CFixedStringMgr` 개체입니다. 재할당 하거나 하 여 버퍼를 해제 하려고 시도 하는 것이 이렇게 `CStringT` 호출 `CFixedStringMgr`합니다.

## <a name="implementation-of-cfixedstringmgrreallocate"></a>CFixedStringMgr::ReAllocate 구현

구현의 `CFixedStringMgr::ReAllocate` 구현에 매우 비슷합니다 `Allocate`합니다.

다시 할당 되 고 버퍼가 고정된 버퍼를 요청된 된 버퍼 크기는 고정된 버퍼 보다 작은 경우 할당이 없습니다 이루어집니다. 그러나 다시 할당 되 고 버퍼 고정된 버퍼 없으면 백업 관리자를 사용 하 여 할당 버퍼 이어야 합니다. 이 경우 백업 관리자는 버퍼를 할당할 사용 됩니다.

다시 할당 되 고 버퍼가 고정된 버퍼를 고정된 버퍼에 맞도록 새 버퍼 크기가 너무 큽니다. `CFixedStringMgr` 백업 관리자를 사용 하 여 새 버퍼를 할당 합니다. 고정된 버퍼의 내용은 새 버퍼에 복사 됩니다.

## <a name="implementation-of-cfixedstringmgrfree"></a>CFixedStringMgr::Free 구현

구현의 `CFixedStringMgr::Free` 와 동일한 패턴을 따릅니다 `Allocate` 고 `ReAllocate`입니다. 해제 되 고 버퍼가 고정된 버퍼 길이가 0 인 잠금된 버퍼에 메서드를 설정 합니다. 백업 관리자를 사용 하 여 해제 중인 버퍼 할당 하는 경우 `CFixedStringMgr` 백업 관리자를 사용 하 여 해제 합니다.

## <a name="implementation-of-cfixedstringmgrclone"></a>CFixedStringMgr::Clone 구현

구현의 `CFixedStringMgr::Clone` 항상 백업 관리자에 대 한 포인터를 반환 하지 않고 `CFixedStringMgr` 자체입니다. 이 경우에 발생의 모든 인스턴스 `CFixedStringMgr` 의 단일 인스턴스를 사용 하 여 연결할 수 있습니다만 `CStringT`합니다. 다른 인스턴스에 `CStringT` 관리자를 복제 하는 동안 가져와야 백업 관리자를 대신 합니다. 이 백업 관리자 공유를 지원 하기 때문입니다.

## <a name="implementation-of-cfixedstringmgrgetnilstring"></a>CFixedStringMgr::GetNilString 구현

구현의 `CFixedStringMgr::GetNilString` 고정된 버퍼를 반환 합니다. 일대일 대응 되는지를 때문 `CFixedStringMgr` 하 고 `CStringT`, 지정된 된 인스턴스에 `CStringT` 한 번에 둘 이상의 버퍼를 사용 하지 않습니다. 따라서 nil 문자열 및 실제 문자열 버퍼 되지 동시에 필요 합니다.

고정된 버퍼 사용에서 없을 때마다 `CFixedStringMgr` 길이가 0 인 초기화 되어 있다고을 확인 합니다. 이 옵션을 사용 하면 nil 문자열로 사용할 수 있도록 합니다. 추가 보너스로 `nAllocLength` 고정된 버퍼의 멤버는 항상 고정된 버퍼의 전체 크기로 설정 됩니다. 따라서 `CStringT` 호출 하지 않고 문자열을 증가할 수 있습니다 [IAtlStringMgr::Reallocate](../atl-mfc-shared/reference/iatlstringmgr-class.md#reallocate)nil 문자열도 합니다.

## <a name="requirements"></a>요구 사항

**헤더:** cstringt.h

## <a name="see-also"></a>참고자료

[CStringT를 사용한 메모리 관리](../atl-mfc-shared/memory-management-with-cstringt.md)
