---
title: /PDBPATH
ms.date: 11/04/2016
f1_keywords:
- /pdbpath
helpviewer_keywords:
- .pdb files, path
- -PDBPATH dumpbin option
- /PDBPATH dumpbin option
- PDBPATH dumpbin option
- PDB files, path
ms.assetid: ccf67dcd-0b23-4250-ad47-06c48acbe82b
ms.openlocfilehash: f29b8e61fbfbdb0f373e3e7510cb3f1fe0b9cc2a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62319852"
---
# <a name="pdbpath"></a>/PDBPATH

```
/PDBPATH[:VERBOSE] filename
```

### <a name="parameters"></a>매개 변수

*filename*<br/>
일치 하는.pdb 파일을 찾을 하려는.dll 또는.exe 파일의 이름입니다.

**:VERBOSE**<br/>
(선택 사항) 여기서 했습니다.pdb 파일을 찾으려고 하는 모든 디렉터리를 보고 합니다.

## <a name="remarks"></a>설명

/PDBPATH 경로 따라 동일한 디버거는.pdb 파일을 검색 및 보고 하는.pdb 파일에 지정 된 파일에 있는 경우는 컴퓨터를 검색 합니다 *filename*합니다.

Visual Studio 디버거를 사용 하는 경우 디버거는 디버깅 하는 파일의 다른 버전에 대 한.pdb 파일을 사용 하는 사실 때문에 문제가 발생할 수 있습니다.

/PDBPATH 다음 경로 따라.pdb 파일에 대 한 검색 됩니다.

- 실행 파일이 있는 위치를 확인 합니다.

- 실행 파일에 작성 된 PDB의 위치를 확인 합니다. 이 일반적으로 위치 이미지가 링크 된 시점에.

- Visual Studio IDE에 구성 된 검색 경로 확인 합니다.

- _NT_SYMBOL_PATH 및 _NT_ALT_SYMBOL_PATH에서 경로 환경 변수를 확인 합니다.

- Windows 디렉터리에서 확인 합니다.

## <a name="see-also"></a>참고자료

[DUMPBIN 옵션](dumpbin-options.md)<br/>
[/PDBALTPATH(대체 PDB 경로 사용)](pdbaltpath-use-alternate-pdb-path.md)
