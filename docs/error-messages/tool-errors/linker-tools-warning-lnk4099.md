---
title: 링커 도구 경고 LNK4099
ms.date: 11/04/2016
f1_keywords:
- LNK4099
helpviewer_keywords:
- LNK4099
ms.assetid: 358170a4-07cd-43fe-918f-82c32757ffc5
ms.openlocfilehash: dcf4d44c3a0b5b10035af763040c2912afc8c6f7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62310892"
---
# <a name="linker-tools-warning-lnk4099"></a>링커 도구 경고 LNK4099

' 개체/라이브러리 ' 또는 '경로의'; 'filename' PDB은 찾을 수 없습니다. 디버그 정보가 없는 것 처럼 개체를 링크 합니다.

링커는.pdb 파일을 찾을 수 없습니다. 포함 된 디렉터리에 복사 `object/library`합니다.

개체 파일과 관련 된.pdb 파일의 이름을 찾으려면:

1. 개체 파일을 사용 하 여 라이브러리에서 추출 [lib](../../build/reference/lib-reference.md) **/extract:**`objectname`**.obj** `xyz` **.lib**합니다.

1. 사용 하 여.pdb 파일의 경로를 확인 **/section:.debug$ T /rawdata dumpbin** `objectname` **.obj**합니다.

사용 하 여 컴파일할 수 있습니다 [/z7](../../build/reference/z7-zi-zi-debug-information-format.md)pdb를 사용 하거나 제거할 필요가 없도록, 합니다 [디버그](../../build/reference/debug-generate-debug-info.md) 링커 옵션을 연결 하는 개체에 대 한.pdb 파일이 없는 경우.