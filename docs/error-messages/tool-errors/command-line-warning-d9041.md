---
title: 명령줄 경고 D9041
ms.date: 11/04/2016
f1_keywords:
- D9041
helpviewer_keywords:
- D9041
ms.assetid: ada8815f-4246-4e25-b57d-a7f16fa107cc
ms.openlocfilehash: 2311c61c4d661d58302308f06b08971f94cdacab
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57816310"
---
# <a name="command-line-warning-d9041"></a>명령줄 경고 D9041

에 대 한 잘못 된 값 'value' '/option'; 'value'; 가정합니다. 추가 ' /analyze '이 경고를 지정 하는 경우 명령줄 옵션

코드 분석 경고 번호가 추가 되었습니다 합니다 **/wd**를 **/we**를 **/wo**, 또는 **/wl** 합니다 도지정하지않고명령줄옵션 **/analyze** 명령줄 옵션입니다. 추가 하거나이 오류를 해결 하려면 합니다 **/analyze** 명령줄 옵션 또는 적절 한 잘못 된 경고 번호를 제거할 **/w** 명령줄 옵션입니다.

## <a name="example"></a>예제

다음 명령줄 예제에서는 경고 D9041 오류가 생성 됩니다.

```
cl /EHsc /LD /wd6001 filename.cpp
```

경고를 해결 하려면 다음을 추가 합니다 **/analyze** 명령줄 옵션입니다. 하는 경우 **/analyze** 는에서 잘못 된 경고 번호를 제거 하는 컴파일러의 버전에 지원 되지 않습니다 합니다 **/wd** 옵션입니다.

## <a name="see-also"></a>참고 항목

[명령줄 오류(D8000 ~ D9999)](../../error-messages/tool-errors/command-line-errors-d8000-through-d9999.md)<br/>
[MSVC 컴파일러 옵션](../../build/reference/compiler-options.md)