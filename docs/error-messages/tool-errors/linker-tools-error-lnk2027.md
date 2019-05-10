---
title: 링커 도구 오류 LNK2027
ms.date: 11/04/2016
f1_keywords:
- LNK2027
helpviewer_keywords:
- LNK2027
ms.assetid: e2f857a8-8e8a-4697-bbff-12ccb84a35c1
ms.openlocfilehash: e74912780bab3056ead36ae3705f0910805228e9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62299012"
---
# <a name="linker-tools-error-lnk2027"></a>링커 도구 오류 LNK2027

확인 되지 않은 모듈 참조 ' module'

링커로 전달 하는 파일을 모두 지정 된 모듈에 대 한 종속 **/ASSEMBLYMODULE** 링커에 직접 전달 합니다.

LNK2027를 해결 하려면 다음 중 하나를 수행 합니다.

- 전달 하지 마십시오 링커에 파일 모듈 종속성입니다.

- 사용 하 여 모듈을 지정할 **/ASSEMBLYMODULE**합니다.

- 모듈이 안전한 .netmodule인 경우 모듈을 링커에 직접 전달합니다.

자세한 내용은 [/ASSEMBLYMODULE (MSIL 모듈을 어셈블리에 추가)](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md) 하 고 [링커 입력으로.netmodule 파일](../../build/reference/netmodule-files-as-linker-input.md)합니다.