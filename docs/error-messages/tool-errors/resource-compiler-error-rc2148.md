---
title: 리소스 컴파일러 오류 RC2148
ms.date: 11/04/2016
f1_keywords:
- RC2148
helpviewer_keywords:
- RC2148
ms.assetid: 0290065c-35d3-4815-80c5-40bf7132ae1d
ms.openlocfilehash: 6d9946c20705fa14046823104455c2819fac353f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62173212"
---
# <a name="resource-compiler-error-rc2148"></a>리소스 컴파일러 오류 RC2148

너무 많은 하위 언어 ID

보조 언어 ID 값이 범위를 벗어났습니다.

**LANGUAGE** 문에서는 다음 구문을 사용해야 합니다.

**LANGUAGE** *primary_language_ID*,*secondary_language_ID*

유효한 보조 언어 Id로 정의 됩니다 **SUBLANG_** WINNT.h 파일에는 상수입니다.