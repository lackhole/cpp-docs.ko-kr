---
title: MMWORD
ms.date: 08/30/2018
f1_keywords:
- MMWORD
helpviewer_keywords:
- MMWORD directive
ms.assetid: b4c5a104-9078-4fb4-afc3-d1e63abe562a
ms.openlocfilehash: e4ebaa9d47a569bc9cf7d843d3ddb54ca5d713a0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62176865"
---
# <a name="mmword"></a>MMWORD

MMX와 SSE (XMM) 지침을 사용 하 여 64 비트 멀티미디어 피연산자에 사용 됩니다.

## <a name="syntax"></a>구문

> MMWORD

## <a name="remarks"></a>설명

`MMWORD` 형식이입니다.  MMWORD MASM에 추가 되 고, 이전와 동일한 기능 구현할 수도 있습니다.

```asm
    mov mm0, qword ptr [ebx]
```

64 비트 피연산자에서 두 지침이 작동 하는 동안 `QWORD` 64 비트 부호 없는 정수 형식입니다. 및 `MMWORD` 64 비트 멀티미디어 값의 형식입니다.

`MMWORD` 동일한 형식으로 표시 하기 위해 [__m64](../../cpp/m64.md)합니다.

## <a name="example"></a>예제

```asm
    movq     mm0, mmword ptr [ebx]
```