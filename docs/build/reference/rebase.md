---
title: /다시 지정
ms.date: 11/04/2016
f1_keywords:
- /rebase
helpviewer_keywords:
- base addresses [C++]
- -REBASE editbin option
- REBASE editbin option
- DLLs [C++], linking
- executable files [C++], base address
- /REBASE editbin option [C++]
ms.assetid: 3f89d874-af5c-485b-974b-fd205f6e1a4b
ms.openlocfilehash: 42cbcb911fcd0aa7753d84aae5523d28371b9972
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62319202"
---
# <a name="rebase"></a>/다시 지정

```
/REBASE[:modifiers]
```

## <a name="remarks"></a>설명

이 옵션에 지정된 된 파일에 대 한 기본 주소를 설정합니다. EDITBIN은 64KB까지 반올림 하는 각 파일의 크기에 따라 연속적인 주소 공간에서 새 기본 주소를 할당 합니다. 기본 주소에 대 한 자세한 내용은 참조는 [기본 주소](base-base-address.md) (/ 기본) 링커 옵션입니다.

프로그램 실행 파일과 Dll을 지정 합니다 *파일* 기반 하는 순서로 EDITBIN 명령줄의 인수입니다. 하나 이상의 선택적으로 지정할 수 있습니다 *한정자*각각 쉼표로 구분 (**,**):

|한정자|작업|
|--------------|------------|
|**BASE=**<em>address</em>|파일에 기본 주소 재할당에 대 한 시작 주소를 제공 합니다. 지정할 *주소* 10 진수 또는 C 언어 표기법으로 나타냅니다. BASE를 지정 하지 않은 경우 기본적으로 시작 하는 기본 주소는 0x400000입니다. DOWN이 사용 되는, 기본 지정 해야 하 고 *주소* 기본 주소 범위의 끝을 설정 합니다.|
|**BASEFILE**|COFFBASE 라는 파일을 만듭니다. TXT에 필요한 형식으로 링크의 텍스트 파일/기본 옵션입니다.|
|**DOWN**|끝 주소에서 아래쪽으로 기본 주소를 할당할 EDITBIN 알려 줍니다. 아래 주소 범위의 가장 높은 가능한 주소에 있는 첫 번째 파일을 사용 하 여 지정 된 순서로 파일을 다시 할당 됩니다. 파일의 기준 주소 공간이 충분 하도록 아래쪽에 있는 BASE는 사용 해야 합니다. 지정된 된 파일에 필요한 주소 공간을 확인 하려면 EDITBIN /REBASE를 사용 하 여 파일을 실행 하 고 표시 된 전체 크기를 64KB를 추가 합니다.|

## <a name="see-also"></a>참고자료

[EDITBIN 옵션](editbin-options.md)
