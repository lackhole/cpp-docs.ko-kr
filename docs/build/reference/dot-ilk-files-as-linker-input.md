---
title: 링커 입력 파일로 사용하는 .Ilk 파일
ms.date: 11/04/2016
helpviewer_keywords:
- ILK files
- .ilk files
ms.assetid: 7324c104-9e5d-423d-b268-b59f92607bf2
ms.openlocfilehash: 252c1cd6e17346954fce7ebf16134246da76ba57
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57808471"
---
# <a name="ilk-files-as-linker-input"></a>링커 입력 파일로 사용하는 .Ilk 파일

증분 방식으로 연결 하는 경우 링크의 첫 번째 증분 링크 중에 만든.ilk 상태 파일을 업데이트 합니다. 이 파일은.exe 파일 또는.dll 파일과 동일한 기본 이름을 있고 확장.ilk 합니다. 후속 증분 링크 하는 동안 링크.ilk 파일을 업데이트 합니다. .Ilk 파일이 없는 경우 링크는 전체 링크를 수행 하 고 새.ilk 파일을 만듭니다. .Ilk 파일에 사용할 수 없는 경우 비증분 링크를 수행 합니다. 증분 링크에 대 한 자세한 내용은 참조는 [증분 링크 (/incremental)](incremental-link-incrementally.md) 옵션입니다.

## <a name="see-also"></a>참고자료

[LINK 입력 파일](link-input-files.md)<br/>
[MSVC 링커 옵션](linker-options.md)
