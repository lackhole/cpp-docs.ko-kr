---
title: codecvt_utf16
ms.date: 11/04/2016
f1_keywords:
- codecvt/std::codecvt_utf16
helpviewer_keywords:
- codecvt_utf16 class
ms.assetid: a9897f98-f84d-4db6-90ad-858b2727570c
ms.openlocfilehash: ca66a3273567a8d30a982211a6e977c129b00f5f
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68459718"
---
# <a name="codecvtutf16"></a>codecvt_utf16

UCS-2 또는 UCS-4로 인코드된 와이드 문자와 UTF-16LE 또는 UTF-16BE로 인코드된 바이트 스트림 간에 변환되는 [로캘](../standard-library/locale-class.md) 패싯을 나타냅니다.

```cpp
template<class Elem, unsigned long Maxcode = 0x10ffff, codecvt_mode Mode = (codecvt_mode)0>
class codecvt_utf16 : public std::codecvt<Elem, char, StateType>
```

## <a name="parameters"></a>매개 변수

*E*\
와이드 문자 요소 형식입니다.

*Maxcode*\
로캘 패싯에 대한 최대 문자 수입니다.

*모드가*\
로캘 패싯에 대한 구성 정보입니다.

## <a name="remarks"></a>설명

이 템플릿 클래스는 UCS-2 또는 UCS-4로 인코드된 와이드 문자와 UTF-16LE(Mode 및 little_endian인 경우) 또는 UTF-16BE(그 외의 경우)로 인코드된 바이트 스트림 간에 변환됩니다.

바이트 스트림은 이진 파일에 작성해야 하며, 텍스트 파일에 작성하는 경우 손상될 수 있습니다.

## <a name="requirements"></a>요구 사항

헤더: \<codecvt >

네임 스페이스: std