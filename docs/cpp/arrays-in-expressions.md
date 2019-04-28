---
title: 식의 배열
ms.date: 11/04/2016
helpviewer_keywords:
- expressions [C++], arrays in
- arrays [C++], in expressions
ms.assetid: 6e5a795b-d6bd-4e39-b313-6a20d47c4d4b
ms.openlocfilehash: 0f2ef43c2a5bc4f8a44378c21d6d53b14f07ea07
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62184382"
---
# <a name="arrays-in-expressions"></a>식의 배열

배열 형식의 식별자가 `sizeof`, address-of(**&**) 또는 참조의 초기화 이외의 식에 나타나는 경우 첫 번째 배열 요소에 대한 포인터로 변환됩니다. 예를 들면 다음과 같습니다.

```cpp
char szError1[] = "Error: Disk drive not ready.";
char *psz = szError1;
```

`psz` 포인터는 `szError1` 배열의 첫 번째 요소를 가리킵니다. 포인터와 달리 배열은 수정할 수 있는 l-value가 아닙니다. 따라서 다음 대입은 올바르지 않습니다.

```cpp
szError1 = psz;
```

## <a name="see-also"></a>참고 항목

[배열(C++)](../cpp/arrays-cpp.md)