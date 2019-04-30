---
title: NMAKE 심각한 오류 U1051
ms.date: 11/04/2016
f1_keywords:
- U1051
helpviewer_keywords:
- U1051
ms.assetid: fede5cd5-dac3-47b7-b86d-e1acfb78699f
ms.openlocfilehash: ddf1d262fb8dfc6e63b0bf5cc098b7b140539310
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62367202"
---
# <a name="nmake-fatal-error-u1051"></a>NMAKE 심각한 오류 U1051

메모리가 부족 합니다.

NMAKE는 메이크파일 너무 크거나 복잡 한 되었으므로 가상 메모리를 포함 하 여 메모리가 부족 합니다.

### <a name="to-fix-by-using-the-following-possible-solutions"></a>아래의 해결 방법 따라 수정합니다.

1. 디스크 공간을 확보 합니다.

1. Windows NT 페이징 파일이 나 Windows 스왑 파일의 크기를 늘립니다.

1. 메이크파일의 일부만 사용 중인 경우 메이크파일 별도 파일로 분할 하거나 사용 하 여 **! IF** 전처리 지시문 NMAKE 처리 해야 하는 크기를 제한 합니다. **! IF** 지시문에는 **! IF**하십시오 `!IFDEF`, **! IFNDEF**, **! ELSE IF**, **! ELSE** `IFDEF`, 및 **! ELSE** `IFNDEF`합니다.