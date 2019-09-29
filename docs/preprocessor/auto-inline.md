---
title: auto_inline pragma
ms.date: 08/29/2019
f1_keywords:
- auto_inline_CPP
- vc-pragma.auto_inline
helpviewer_keywords:
- pragmas, auto_inline
- auto_inline pragma
ms.assetid: f7624cd1-be76-429a-881c-65c9040acf43
ms.openlocfilehash: 59cda8cb73196215318c9570a5c067786284afaa
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70216308"
---
# <a name="auto_inline-pragma"></a>auto_inline pragma

**auto_inline** pragma가 **off**로 지정된 범위 내의 함수는 인라인 자동화가 이루어지지 않도록 인라인 확장의 후보에서 제외시킵니다.

## <a name="syntax"></a>구문

> **#pragma auto_inline (** [{ **on** | **off** }] **)**

## <a name="remarks"></a>설명

**auto_inline** pragma를 사용하려면 함수 정의 내부가 아닌 앞과 뒤에 배치합니다. pragma는 pragma가 표시된 후 첫 번째 함수 정의가 표시되는 즉시 적용됩니다.

## <a name="see-also"></a>참고자료

[Pragma 지시문 및 __pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
