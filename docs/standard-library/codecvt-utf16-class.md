---
title: codecvt_utf16
ms.date: 11/04/2016
f1_keywords:
- codecvt/std::codecvt_utf16
helpviewer_keywords:
- codecvt_utf16 class
ms.assetid: a9897f98-f84d-4db6-90ad-858b2727570c
ms.openlocfilehash: 18b95884bb673305398739968ef2530e8c4778d1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62405224"
---
# <a name="codecvtutf16"></a>codecvt_utf16

UCS-2 또는 UCS-4로 인코드된 와이드 문자와 UTF-16LE 또는 UTF-16BE로 인코드된 바이트 스트림 간에 변환되는 [로캘](../standard-library/locale-class.md) 패싯을 나타냅니다.

```cpp
template<class Elem, unsigned long Maxcode = 0x10ffff, codecvt_mode Mode = (codecvt_mode)0>
class codecvt_utf16 : public std::codecvt<Elem, char, StateType>
```

## <a name="parameters"></a>매개 변수

*Elem*<br/>
와이드 문자 요소 형식입니다.

*Maxcode*<br/>
로캘 패싯에 대한 최대 문자 수입니다.

*모드*<br/>
로캘 패싯에 대한 구성 정보입니다.

## <a name="remarks"></a>설명

이 템플릿 클래스는 UCS-2 또는 UCS-4로 인코드된 와이드 문자와 UTF-16LE(Mode 및 little_endian인 경우) 또는 UTF-16BE(그 외의 경우)로 인코드된 바이트 스트림 간에 변환됩니다.

바이트 스트림은 이진 파일에 작성해야 하며, 텍스트 파일에 작성하는 경우 손상될 수 있습니다.

## <a name="requirements"></a>요구 사항

헤더: \<codecvt >

Namespace: std