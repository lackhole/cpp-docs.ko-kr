---
title: 심각한 오류 C1126
ms.date: 11/04/2016
f1_keywords:
- C1126
helpviewer_keywords:
- C1126
ms.assetid: f22b26a6-8ad7-47cf-a237-196c8ea60aca
ms.openlocfilehash: 3f4d152163d3b21ddf99644c34e63f35ca15e6e9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62230014"
---
# <a name="fatal-error-c1126"></a>심각한 오류 C1126

'identifier': 자동 할당 크기를 초과 했습니다.

함수 (및 제한 된 용량의 스왑 가능 함수에 대 한 추가 20 바이트와 같은 컴파일러에 의해 사용 된 공간)의 로컬 변수에 할당 된 공간 제한을 초과 합니다.

이 오류를 해결 하려면 사용 하 여 `malloc` 또는 `new` 많은 양의 데이터를 할당 합니다.