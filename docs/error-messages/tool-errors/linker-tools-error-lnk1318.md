---
title: 링커 도구 오류 LNK1318
ms.date: 05/29/2018
f1_keywords:
- LNK1318
helpviewer_keywords:
- LNK1318
ms.openlocfilehash: 8ed6489a27d4c0e117f7f18281ff188f40936e0a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62160993"
---
# <a name="linker-tools-error-lnk1318"></a>링커 도구 오류 LNK1318

> 예기치 않은 PDB 오류; *일으킬* '*세부 정보*'

링커는 열기, 읽기 및 PDB 파일에 쓸 때 예기치 않은 오류가 발생 했습니다.

이 오류 메시지는 일반적이 지 않은 문제 PDB 파일에 대해 생성 됩니다. *발생할* 하 고 *세부 정보* 오류가 발생 하는 경우 링커에 제공 되는 정보를 나타냅니다. 이 PDB 파일을 사용 하 여 처리 별도 자세한 오류 메시지가 있을 때 일반적인 오류와 매우 유용할 수 하지 않을 수 있습니다.

없기 때문에 오류 소스를 일반적인 없는 제네릭 조언을이 문제를 확인 하는 데 사용할 수 있습니다.

- 빌드 디렉터리를 정리 작업을 수행 하 고 솔루션의 전체 빌드를 수행 합니다.

- 컴퓨터를 다시 부팅 또는 mspdbsrv.exe 이탈 되거나 응답이 없는 프로세스에 대 한 확인 하 고 작업 관리자의 종료 합니다.

- 프로젝트 디렉터리에서 바이러스 백신 검사를 해제 합니다.

- 사용 된 [/Zf](../../build/reference/zf.md) 컴파일러 옵션을 사용 하는 경우 [/MP](../../build/reference/mp-build-with-multiple-processes.md) MSBuild 또는 다른 병렬 빌드 프로세스입니다.

- 64 비트 호스트 된 도구 집합을 사용 하 여 빌드를 시도 합니다.

- 필요한 경우 병렬 링크 문제를 완화 하기 위해 연결을 serialize 합니다. Mspdbsrv.exe 링크의 한 인스턴스에서 시작 되 고 링크의 다른 인스턴스는 완료 전에 종료 되는 경우이 오류가 발생할 수 있습니다 사용 합니다. 이 문제가 해결 단점은 프로젝트 빌드를 완료 하려면 상당히 오래 걸릴 수 있습니다.