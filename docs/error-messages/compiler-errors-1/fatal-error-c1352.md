---
title: 심각한 오류 C1352
ms.date: 11/04/2016
f1_keywords:
- C1352
helpviewer_keywords:
- C1352
ms.assetid: d044e8b0-b6ef-4d57-8eb5-6254071be707
ms.openlocfilehash: fbba87cea05d666d6dc3a385ca1fe52e143fdb5a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62329727"
---
# <a name="fatal-error-c1352"></a>심각한 오류 C1352

'file' 모듈의 'function' 함수에 잘못되었거나 손상된 MSIL이 있습니다.

.netmodule이 컴파일러에 전달되었지만 컴파일러가 파일에서 손상된 부분을 발견했습니다.  .netmodule을 생성한 사람에게 조사하도록 요청하세요.

컴파일러는 .netmodule 파일에서 모든 유형의 손상을 확인하지 않습니다.  그러나 함수의 모든 제어 경로에 return 문이 포함되어 있는지 확인합니다.

자세한 내용은 [링커 입력 파일로 사용하는 .netmodule 파일](../../build/reference/netmodule-files-as-linker-input.md)을 참조하세요.