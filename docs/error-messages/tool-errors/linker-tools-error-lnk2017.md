---
title: 링커 도구 오류 LNK2017
ms.date: 11/04/2016
f1_keywords:
- LNK2017
helpviewer_keywords:
- LNK2017
ms.assetid: f7c21733-b0fb-4888-a295-9b453ba6ee77
ms.openlocfilehash: ce5332c2812740ef0b8c7d8e9c64a095d20a4e2b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62299058"
---
# <a name="linker-tools-error-lnk2017"></a>링커 도구 오류 LNK2017

'세그먼트' /largeaddressaware: no 없는 잘못 된 'symbol' 재배치

32 비트 주소를 사용 하 여 64 비트 이미지를 작성 하려고 합니다. 이렇게 하려면 다음을 수행 해야 합니다.

- 고정된 로드 주소를 사용 합니다.

- 이미지를 3GB로 제한 합니다.

- 지정할 [/largeaddressaware: no](../../build/reference/largeaddressaware-handle-large-addresses.md)합니다.