---
title: 링커 도구 오류 LNK1140
ms.date: 11/04/2016
f1_keywords:
- LNK1140
helpviewer_keywords:
- LNK1140
ms.assetid: 468d7651-a7cd-47b9-aead-5bb2fab56121
ms.openlocfilehash: 48c735f29918c4d1caeb15123f7376276d116fb4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62255068"
---
# <a name="linker-tools-error-lnk1140"></a>링커 도구 오류 LNK1140

프로그램 데이터베이스에 대 한 너무 많은 모듈 링크 /PDB: NONE

프로젝트에 4,096 개가 넘는 모듈이 있습니다.

### <a name="to-fix-by-using-the-following-possible-solutions"></a>아래의 해결 방법 따라 수정합니다.

1. 사용 하 여 다시 연결 [/PDB: NONE](../../build/reference/pdb-use-program-database.md)합니다.

1. 정보를 디버깅 하지 않고 일부 모듈을 컴파일하십시오.

1. 모듈의 수를 줄입니다.