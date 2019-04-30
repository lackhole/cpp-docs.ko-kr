---
title: 사용자 지정 문자열 관리자 구현 (고급 방법)
ms.date: 11/04/2016
helpviewer_keywords:
- IAtlStringMgr class, using
ms.assetid: 64ab7da9-47c1-4c4a-9cd7-4cc37e7f3f57
ms.openlocfilehash: 3854ffe205aa8e6cb9cfb800b9aa1473094fffaf
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62235501"
---
# <a name="implementation-of-a-custom-string-manager-advanced-method"></a>사용자 지정 문자열 관리자 구현 (고급 방법)

특수 한 경우에는 힙 메모리를 할당 하는 것 이상의 변하지는 사용자 지정 문자열 관리자를 구현 하는 것이 좋습니다. 이런 경우 수동으로 구현 해야 합니다 [IAtlStringMgr](../atl-mfc-shared/reference/iatlstringmgr-class.md) 에 사용자 지정 문자열 관리자 인터페이스입니다.

이렇게 하려면 먼저 알아야 할 것 어떻게 [CStringT](../atl-mfc-shared/reference/cstringt-class.md) 해당 인터페이스를 사용 하 여 해당 문자열 데이터를 관리 합니다. 모든 인스턴스 `CStringT` 에 대 한 포인터에는 [CStringData](../atl-mfc-shared/reference/cstringdata-class.md) 구조입니다. 이 변수-길이 구조 문자열에 대 한 실제 문자는 데이터 뿐만 아니라 문자열 (예: 길이)에 대 한 중요 한 정보를 포함합니다. 모든 사용자 지정 문자열 관리자는 할당 하 고 요청 시 이러한 구조를 해제 하는 일을 담당 `CStringT`합니다.

`CStringData` 구조체는 4 개의 필드를 구성 합니다.

- [pStringMgr](../atl-mfc-shared/reference/cstringdata-class.md#pstringmgr) 이 필드를 가리키는 `IAtlStringMgr` 이 문자열 데이터를 관리 하는 데 사용 되는 인터페이스입니다. 때 `CStringT` 재할당 하거나 재할당 또는 전달이 인터페이스의 사용 가능한 메서드를 호출 하는 문자열 버퍼를 해제 해야 하는 `CStringData` 매개 변수로 구조입니다. 할당 하는 경우는 `CStringData` 구조 문자열 상사가 사용자의 사용자 지정 문자열 관리자를 가리키도록이 필드를 설정 해야 합니다.

- [nDataLength](../atl-mfc-shared/reference/cstringdata-class.md#ndatalength) 이 필드는 종료 null을 제외 하 고 버퍼에 저장 된 문자열 길이의 현재 논리를 포함 합니다. `CStringT` 문자열의 길이가 변경 되 면이 필드를 업데이트 합니다. 할당 하는 경우는 `CStringData` 구조 관리자에 게 문자열을 0으로이 필드를 설정 해야 합니다. 다시 할당 하는 경우는 `CStringData` 구조를 사용자 지정 문자열 관리자 변경 하지 않고이 필드를 유지 해야 합니다.

- [nAllocLength](../atl-mfc-shared/reference/cstringdata-class.md#nalloclength) 이 필드에이 다시 할당 하지 않고이 문자열 버퍼에 저장할 수 있는 문자 (종결 null 제외)의 최대 수를 포함 합니다. 때마다 `CStringT` 논리 문자열 길이 늘립니다 해야 하는 경우 먼저이 필드를 버퍼에 공간이 충분 한지 확인 합니다. 확인이 실패 하면, `CStringT` 버퍼를 할당할 사용자 지정 문자열 관리자를 호출 합니다. 할당 또는 다시 할당 하는 경우는 `CStringData` 구조를 설정 해야이 필드를 하나 이상에서 요청 된 문자의 수를 *nChars* 매개 변수를 [IAtlStringMgr::Allocate](../atl-mfc-shared/reference/iatlstringmgr-class.md#allocate) 또는[IAtlStringMgr::Reallocate](../atl-mfc-shared/reference/iatlstringmgr-class.md#reallocate)합니다. 요청 된 수보다 버퍼에 더 많은 공간이 있으면이 값을 실제 사용 가능한 공간의 크기를 반영 하도록 설정할 수 있습니다. 따라서 `CStringT` 버퍼에 할당할 문자열 관리자를 다시 호출 되기 전에 전체 입력 문자열을 증가 공간을 할당 합니다.

- [nRefs](../atl-mfc-shared/reference/cstringdata-class.md#nrefs) 이 필드는 문자열 버퍼의 현재 참조 횟수를 포함 합니다. 값이 하나 다음의 단일 인스턴스 `CStringT` 버퍼를 사용 하는 합니다. 또한 인스턴스 읽기 및 버퍼의 내용을 수정할 수 있습니다. 값이 1 보다 큰 경우의 여러 인스턴스 `CStringT` 버퍼를 사용할 수 있습니다. 문자 버퍼에서 공유 되므로 `CStringT` 인스턴스 버퍼의 내용을 읽을 수만 있습니다. 콘텐츠를 수정 하려면 `CStringT` 먼저 버퍼의 복사본을 만듭니다. 값이 음수, 하나의 인스턴스만 `CStringT` 버퍼를 사용 하는 합니다. 이 경우 버퍼에는 것으로 간주 됩니다 잠겨 있습니다. 경우는 `CStringT` 인스턴스에서 사용 하 고 잠긴된 버퍼의 다른 인스턴스가 없는 `CStringT` 버퍼를 공유할 수 있습니다. 대신 이러한 인스턴스는 콘텐츠를 조작 하기 전에 버퍼의 복사본을 만듭니다. 또한 합니다 `CStringT` 잠긴된 버퍼를 사용 하 여 인스턴스는 다른 버퍼를 공유 하지 `CStringT` 할당 된 인스턴스. 이 경우에 `CStringT` 인스턴스 잠긴된 버퍼에는 다른 문자열을 복사 합니다.

   할당 하는 경우는 `CStringData` 구조를 버퍼에 허용 되는 공유 유형을 반영 하도록이 필드를 설정 해야 합니다. 대부분의 구현에 대 한 하나에이 값을 설정 합니다. 따라서 일반적인 쓰기 시 복사 공유 동작 합니다. 그러나 문자열 상사가 문자열 버퍼를 공유 하는 것을 지원 하지 않으면,이 필드를 잠긴 상태로 설정 합니다. 이렇게 하면 `CStringT` 에이 버퍼를 사용 하 여 인스턴스의 `CStringT` 는 할당 된 합니다.

## <a name="see-also"></a>참고자료

[CStringT를 사용한 메모리 관리](../atl-mfc-shared/memory-management-with-cstringt.md)
