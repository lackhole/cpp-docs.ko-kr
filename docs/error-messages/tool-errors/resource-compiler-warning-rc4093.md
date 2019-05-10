---
title: 리소스 컴파일러 경고 RC4093
ms.date: 11/04/2016
f1_keywords:
- RC4093
helpviewer_keywords:
- RC4093
ms.assetid: 3c61b4a4-b418-465b-a4fd-cb1ff0adb8dd
ms.openlocfilehash: 23bf436e6e8338f89bc576564181c84715028332
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62346212"
---
# <a name="resource-compiler-warning-rc4093"></a>리소스 컴파일러 경고 RC4093

비활성 코드의 문자 상수에서 이스케이프 되지 않은 줄 바꿈

상수 식의는 `#if`, `#elif`, **#ifdef**, 또는 **#ifndef** 비활성 전처리기 지시문을 0으로는 코드를 만드는 계산을 따릅니다. 비활성 코드에 내에서 줄 바꿈 문자는 단일 또는 이중 따옴표로 묶어서 표시 되었습니다.

다음 큰따옴표까지 모든 텍스트 문자 상수 내 것으로 간주 되었습니다.