---
title: 컴파일러 오류 C3552
ms.date: 11/04/2016
f1_keywords:
- C3552
helpviewer_keywords:
- C3552
ms.assetid: 83401524-1bf1-44c0-8aca-a6eb35c4224c
ms.openlocfilehash: 27c4707097f43266a3be57ad6dc9591ab6f34e97
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62375940"
---
# <a name="compiler-error-c3552"></a>컴파일러 오류 C3552

'typename': 컴파일하면 지정되는 반환 형식은 'auto'를 포함할 수 없습니다.

`auto` 키워드를 함수 반환 형식에 대한 자리 표시자로 사용하는 경우 컴파일하면 지정되는 반환 형식을 제공해야 합니다. 그러나 다른 `auto` 키워드를 사용하여 컴파일하면 지정되는 반환 형식을 지정할 수는 없습니다. 예를 들어 다음 코드 조각은 C3552 오류를 생성합니다.

`auto myFunction->auto; // C3552`