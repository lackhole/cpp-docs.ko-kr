---
title: 컴파일러 오류 C2241
ms.date: 11/04/2016
f1_keywords:
- C2241
helpviewer_keywords:
- C2241
ms.assetid: 2f4e2c2c-b95c-4afe-bbe0-4214cd39d140
ms.openlocfilehash: 88f25931d84fe3884ebecbc97b9ddd73390bacc2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62388971"
---
# <a name="compiler-error-c2241"></a>컴파일러 오류 C2241

'identifier': 멤버 액세스가 제한됩니다.

코드가 전용 또는 보호된 멤버에 액세스하려고 합니다.

### <a name="to-fix-by-using-the-following-possible-solutions"></a>다음 해결 방법을 사용하여 수정하려면

1. 멤버의 액세스 수준을 변경합니다.

1. 멤버를 액세스하는 함수의 `friend` 로 선언합니다.