---
title: 다른 테이블의 행에 대 한 참조를 포함 하는 경우 열 업데이트
ms.date: 10/24/2018
helpviewer_keywords:
- rowsets, column updates
ms.assetid: abb5db69-055d-431f-b12d-ad2940a661ba
ms.openlocfilehash: 46de5f54a3ec6525f779a6b55a700429a2a84fef
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59039217"
---
# <a name="updating-a-column-when-another-table-contains-a-reference-to-the-row"></a>다른 테이블에 행에 대한 참조가 들어 있는 경우의 열 업데이트

일부 공급자는 행에서 변경된 열을 감지할 수 있지만, 대부분의 공급자는 그렇게 하지 못합니다. 따라서, 업데이트하려는 행에 대한 참조가 있는 경우, 열을 업데이트하면 오류가 발생할 수 있습니다. 이 문제를 해결하려면, 변경하려는 열만 들어 있는 개별 접근자를 만드십시오. 해당 접근자의 번호를 `SetData`에 전달하십시오.

## <a name="see-also"></a>참고자료

[접근자 사용](../../data/oledb/using-accessors.md)