---
title: 링커 도구 경고 LNK4037
ms.date: 10/04/2017
f1_keywords:
- LNK4037
helpviewer_keywords:
- LNK4037
ms.assetid: 9ba02fd3-b04f-4679-bab9-26fa82cf09bb
ms.openlocfilehash: 9a8121617e622fc12efe5bd26aac23faf2530f24
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62410306"
---
# <a name="linker-tools-warning-lnk4037"></a>링커 도구 경고 LNK4037

>'*기호*'가 없습니다; 무시 됩니다

데코 레이트 된 이름을 *기호* 를 사용 하 여 정렬할 수 없습니다는 [/order](../../build/reference/order-put-functions-in-order.md) 옵션 프로그램에서 찾을 수 없습니다. 사양을 확인 *기호* 순서 응답 파일에 있습니다. 자세한 내용은 참조는 [/ORDER (함수에 순서 지정)](../../build/reference/order-put-functions-in-order.md) 링커 옵션입니다.

> [!NOTE]
> 링크 정적 함수 이름은 공용 기호 이름이 없기 때문에 정적 함수를 주문할 수 없습니다. 때 **/order** 지정 정적 순서 지시 파일의 각 기호에 대 한이 링커 경고는 생성 되었거나 찾을 수 없습니다.