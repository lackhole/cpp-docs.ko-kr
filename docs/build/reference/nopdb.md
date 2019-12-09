---
title: /NOPDB
description: /NOPDB 옵션은 기호 정보에 대 한 PDB 파일의 로드 및 검색에서 DUMPBIN을 유지 합니다.
ms.date: 12/04/2019
f1_keywords:
- /NOPDB
helpviewer_keywords:
- /NOPDB dumpbin option
- /NOPDB
ms.openlocfilehash: 7b0c01e59b52bcec6ddf09416dd6aac9999527a6
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74856971"
---
# <a name="nopdb"></a>/NOPDB

기호 정보에 대 한 PDB (프로그램 데이터베이스) 파일을 로드 하 고 검색 하지 않도록 DUMPBIN에 지시 합니다.

## <a name="syntax"></a>구문

> **/NOPDB**

## <a name="remarks"></a>주의

기본적으로 DUMPBIN은 대상 실행 파일의 PDB 파일을 로드 하려고 합니다. DUMPBIN은이 정보를 사용 하 여 주소를 기호 이름에 일치 시킵니다. PDB 파일이 크거나 원격 서버에서 로드 되어야 하는 경우 프로세스에 시간이 오래 걸릴 수 있습니다. **/Nopdb** 옵션은이 단계를 건너뛰도록 DUMPBIN에 지시 합니다. 실행 파일에서 사용할 수 있는 주소 및 기호 정보만 인쇄 합니다.

### <a name="to-set-the-nopdb-linker-option-in-visual-studio"></a>Visual Studio에서/NOPDB 링커 옵션을 설정 하려면

1. 프로젝트에 대한 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. **구성 속성** > **링커** > **명령줄** 속성 페이지를 선택합니다.

1. **추가 옵션** 상자에 **/nopdb** 옵션을 추가 합니다. **확인**이나 **적용**을 선택하여 변경 내용을 저장합니다.

### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면

- 이 옵션에는 프로그래밍 방식으로 해당 하는 항목이 없습니다.

## <a name="see-also"></a>참조

[DUMPBIN 명령줄](dumpbin-command-line.md)\
[DUMPBIN 옵션](dumpbin-options.md)\
[DUMPBIN 참조](dumpbin-reference.md)
