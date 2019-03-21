---
title: .Sbr 파일 만들기
ms.date: 11/04/2016
helpviewer_keywords:
- SBR files
- BSCMAKE, input files
- .sbr files
- source browser files
- local symbols in browse information
- symbols
ms.assetid: bdb4b93c-a88a-441a-84fd-01087d03be25
ms.openlocfilehash: 75c3b926a605de66c876e9350218807031cd9a43
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57810408"
---
# <a name="creating-an-sbr-file"></a>.Sbr 파일 만들기

BSCMAKE에 대 한 입력된 파일은.sbr 파일입니다. 컴파일러는.sbr 파일을 컴파일하는 각 개체 파일 (.obj)을 만듭니다. 빌드하거나 찾아보기 정보 파일을 업데이트 하는 경우 프로젝트에 대 한 모든.sbr 파일이 디스크에 있어야 합니다.

지정 가능한 모든 정보를 사용 하 여.sbr 파일을 만들려면 [/FR](fr-fr-create-dot-sbr-file.md)합니다.

로컬 기호를 포함 하지 않는.sbr 파일을 만들려면 지정 [/Fr](fr-fr-create-dot-sbr-file.md)합니다. .Sbr 파일에 로컬 기호는 포함 하는 경우 생략할 수 있습니다 여전히.bsc 파일에서 BSCMAKE의를 사용 하 여 [/El 옵션](bscmake-options.md)`.`

전체 컴파일을 수행 하지 않고.sbr 파일을 만들 수 있습니다. 예를 들어, 구문 검사를 수행 하 고 여전히 /FR 또는 /Fr. 지정 하면.sbr 파일을 생성 하도록 컴파일러에 /Zs 수를 지정할 수 있습니다.

빌드 프로세스.sbr 파일을 참조 하지 않는 정의 제거 하려면 먼저 압축 되는 경우 더 효율적일 수 있습니다. 컴파일러는 자동으로.sbr 파일을 압축합니다.

## <a name="see-also"></a>참고자료

[.Bsc 파일 빌드](building-a-dot-bsc-file.md)
