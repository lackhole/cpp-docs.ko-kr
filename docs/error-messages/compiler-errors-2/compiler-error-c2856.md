---
title: 컴파일러 오류 C2856
ms.date: 11/04/2016
f1_keywords:
- C2856
helpviewer_keywords:
- C2856
ms.assetid: fe616c51-124e-49e3-9dd8-883ec1660680
ms.openlocfilehash: 1e515f250c8ab9d1008ded91b99176f1d86d7cd1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62406849"
---
# <a name="compiler-error-c2856"></a>컴파일러 오류 C2856

\#pragma hdrstop #if 블록 내 여야 합니다.

`hdrstop` 조건부 컴파일 블록의 본문 안에 pragma를 배치할 수 없습니다.

이동 합니다 `#pragma hdrstop` 영역에 포함 되지 않은 문을 `#if/#endif` 블록입니다.